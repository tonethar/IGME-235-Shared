# Web Apps Lab 7

## Begin with the following code (Save it as web-apps-lab-7.html)
```
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Web Apps Tutorial 7 Exercise</title>
    <style>
        li {
            text-transform: capitalize;
        }
    </style>
    <script>
        "use strict"

        let monsters = [];      // our array of monsters

        /**
         * Our onload Event.
         * 
         */
        window.onload = function () {
            makeSampleMonsters();
            showMonsters();
        }

        /**
         * Create a set of Sample Monsters.
         * 
         */
        function makeSampleMonsters() {
            let monster;

            monster = makeGoomba("John", 20, 30, 100);
            monsters.push(monster);
            monster = makeGoomba("Fred", 30, 100, 150);
            monsters.push(monster);
            monster = makeGoomba("Alice", 40, 150, 200);
            monsters.push(monster);
        }

        /**
         * Function that shows our monsters (just Goombas for now)
         * 
         */
        function showMonsters() {
            let goombaList = document.querySelector("#goombas");

            for (let i = 0; i < monsters.length; i++) {
                let liStr = "";
                let li = document.createElement("li");

                for (let key in monsters[i]) {
                    if (typeof monsters[i][key] !== "function") {
                        liStr += `<b>${key}:</b> ${monsters[i][key]}<br />`;
                    }
                }
                li.innerHTML = liStr;
                goombaList.appendChild(li);
            }
        }

        /**
         * create our base monster object with defaults.
         * 
         */
        function createBaseMonster() {
            return {
                name: "",
                hp: 100,
                speed: 10,
                score: 100,
                status: function () {
                    console.log("name: " + this.name + ", hp: " + this.hp + ", speed: " + this.speed + ", score: " + this.score);
                }
            }
        }

        /**
         * Create a Goomba.
         * 
         */
        function makeGoomba(name, hp, speed, score) {
            let goomba = createBaseMonster();
            goomba.name = name;
            goomba.hp = hp;
            goomba.speed = speed;
            goomba.score = score;
            goomba.takeDamage = function (dmgVal) {
                goomba.hp -= dmgVal;
            }
            goomba.powerUp = powerUp;

            Object.seal(goomba);
            return goomba;
        }

        /**
         * Function that can be used inside a monster object.
         * 
         */
        function powerUp(val) {
            this.speed += val;
            this.hp += val
            this.status();
        };

    </script>
</head>

<body>
    <div id="lineUp">
        <h1>Goombas</h1>
        <ul id="goombas">
        </ul>
    </div>
</body>

</html>
```


1. Begin by getting familiar with the code.  From top to bottom, read the comments and do your best to understand what's going on.
		
	Things to note:
	- The `onload` event handler is getting a function expression directly assigned to it.
	- The `makeSampleMonsters` function is pushing each monster into a previously empty array called `monsters`.  This is creating an array of objects all based on the "base monster"
	- The `showMonsters` function is currently specific to Goombas... It targets a specific HTML list.  However, it reads the entire monsters array.  Notice that it's going through an array of objects with the `[i]` counter, but then it checks each of the properties by `[key]` in those objects by looking at the `typeof` the associated value to make sure it's not a `function` before adding it to the string that's being built.
	- The `createBaseMonster` function creates a baseline monster with some default properties and a `.status()` method (notice how it uses the `this` keyword).  We'll only call it from within our `makeGoomba` function (just below), so it will immediately get other values for these properties as well as a new function or two.
	- The `makeGoomba` function (which could theoretically be specifically tailored to Goomba-creation) just assigns the arguments passed to it their proper object properties.  Then it defines a new `.takeDamage()` method, attaches the powerUp function (defined right below it) as another method, and then `.seals` it up so no further properties can be added.  A complete monster object is returned.
			
2. Open the page in the browser, pop open the console & check out the contents of the `monsters` array.  If you just type `monsters` and press enter, it will return the whole array.  Use the little disclosure triangle to see the full contents of the array.  Notice the properties including the fact that there is a method called status in each object.
		
	-Predict what `monsters[1]["hp"]` would return.  Then test it in the console.

	-Enter `monsters[2].status()` -- Do you understand where this came from?
			
2. Make a function that returns **Boos** instead of **Goombas**. 

	-It should work just like `makeGoomba()`.
			
3. Add some **Boos** to the monster list.
		
	-You can make a new function and call it in the `onload` handler function or you could add more monsters in the `makeSampleMonsters()` function.

4. When you preview your page now, you should get more monsters in your HTML list.
			
	-We want them to appear in their own list

5. Make a new list for Boo's (in the HTML -- make its id **boos**) 
		
6. Update the `showMonsters` function to handle which list to write to. Add an argument that accepts the *element selector* you want to use.
		
	-You should be able to change `showMonsters()` to `showMonsters('#boos')` and have the list of monsters show up in your new list.
	
7. Add **type** to your base monster, then set that **type** to something appropriate in your two monster creation functions.
		
	-**Type** should now be appearing as an additional property in your monster lists.

8. Finally, make it so that the `showMonsters` function can put a specific "type" of monster into the specific element by adding another argument for the **type**.  For example, `showMonsters('Boo', '#boos');` should show only the 'Boo'-type monsters in the list with the id of `boos`.
		
	-*Hint:* before you go iterating through a particular monster's properties, make sure that is the right type first. 

	-Go ahead and call `showMonsters` twice in the `onload` handler function. Once for each type of monster.



When you're finished, save your work for later submission.
