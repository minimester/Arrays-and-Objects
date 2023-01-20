# We Do: Objects and Arrays

Recall that an `Object` is a JavaScript data type that allows us to store related data together in a collection, whereas an `Array` stores values in an indexed list.

## Arrays Exercise

For each of the exercises below, assume you are starting with the following people array.

```js
let people = ["Greg", "Mary", "Devon", "James"];
```

<details><summary>Using a loop, iterate through this array and console.log all of the people.</summary>

```js
for(let i =0; i< people.length; i++){
    console.log(people[i]);
}
```
</details>

<details><summary>Write the command to remove "Greg" from the array.</summary>

```js
people.shift();
```
</details>

<details><summary>Write the command to add "Matt" to the front of the array. </summary>

```js
people.unshift("Matt");
```
</details>

<details><summary>Using a loop, iterate through this array and after console.log-ing "Mary", exit from the loop.</summary>

```js
for(let i =0; i< people.length; i++){
    if(i > 1){
        break;
    }
    console.log(people[i]);
}
```

Or you could find Mary another way: 

```js
for(let i =0; i< people.length; i++){
    if(people[i] === "Mary"){
        break;
    }
    console.log(people[i]);
}
```

</details>

<details><summary>Write the command that gives the indexOf where "Mary" is located.</summary>

```js
people.indexOf("Mary");
```
</details>

<details><summary>Redefine the people variable with the value you started with. Using the splice command, remove "Devon" from the array and add "Elizabeth" and "Artie". Your array should look like this when you are done ["Greg", "Mary", "Elizabeth", "Artie", "James"].</summary>

```js
people.splice(2,1,"Elizabeth", "Artie");
```
</details>

<details><summary>Using the Map method, create a new array where each name that does NOT end in a `y`, gets a `y` added to the end of it and where each name that does end in a `y`, gets the `y` replaced with `iful`.</summary>

The rules are listed below:

- If a name does NOT end in a y, then add on a y to the name:
    - Rufus changes to Rufusy.
- If a name does end in a y, then replace the y with iful:
    - Tony changes to Toniful.

Mutate the original array:

```js
let people = ["Greg", "Mary", "Devon", "James"];
```

Here is a possible solution using a map:

```js
let changeNamePeople = people.map((name)=>{

    if(name[name.length-1] ==='y'){
        return name.substring(0, name.length - 1)+'iful';
    } else{
        return name+'y';
    }
})

// ['Gregy', 'Mariful', 'Devony', 'Jamesy']
```


</details>
_____________

## Objects Exercise

For each of the exercises below, assume you are starting with the following programming object.

```js
let programming = {
    languages: ["JavaScript", "Python", "Ruby"],
    isChallenging: true,
    isRewarding: true,
    difficulty: 8,
    jokes: "http://stackoverflow.com/questions/234075/what-is-your-best-programmer-joke"
};
```

<details><summary>Write the command to add the language "Go" to the end of the languages array.</summary>

```js
programming.languages.push("Go");
```
</details>

<details><summary>Change the difficulty to the value of 7.</summary>

```js
programming.difficulty = 7;
```
</details>

<details><summary>Using the delete keyword, write the command to remove the jokes key from the programming object. </summary>

```js
delete programming.jokes;
```
</details>

<details><summary>Write the command to add a new key called isFun and a value of true to the programming object.</summary>

```js
programming.isFun = true;
```
</details>

<details><summary>Using a loop, iterate through the languages array and console.log all of the languages.</summary>

```js
for (let i = 0; i < programming.languages.length; i++) {
    console.log(programming.languages[i]);
}
```

Or you can use a `for of` loop:

```js
for (let language of programming.languages) {
    console.log(language);
}
```

</details>

<details><summary>Using a loop, console.log all of the keys in the programming object.</summary>

```js
for (let key in programming){
    console.log(key);
}
```
</details>

<details><summary>Using a loop, console.log all of the values in the programming object.</summary>

```js
for (let key in programming){
    console.log(programming[key]);
}
```
</details>

<details><summary>Write the command to add a new function into the object, where the function prints out all the languages in the language array using a for loop.</summary>

```js
programming.newFunction = function (){
    for(let i=0; i<this.languages.length; i++){
        console.log(this.languages[i]);
    }
}

programming.newFunction();

// JavaScript
// Python
// Ruby
```
</details>



