# Modern Javascript - ES6

I have created this repository, so I can cirle back to it later when I want to review modern Javascript syntax with examples

- **Difference between `var`, `let` and `const`**

- You use `const` when you never plan on changing the value of the variable
- `let` allows you to change the function of a variable only inside the function and not outside
- `var` allows you to change the value of the variable anywhere
- Use `const` as much as possible when you do not expect the variable value to change


- **Arrow Function**

- Standard function Example:

```Javascript

const name='Jay';
let age=29;
const hashobbies=true;

// note that here I can change the age by stating age=30
// But you can not change the name because its stored as const

function summarizeUser(userName,userAge,userHasHobby){
    return(
        'Name is'+userName+ ', age is' +userAge+ ' and hobbies'+userHasHobby
    );
}
// Above is a named function. If I did not specify sumarizeUser then it would be
// called an anonymous function
// You can also capture the function as a variable const summarizeUser= anomalous function
```
- Uisng Arrow function - you are able to eliminate the word 'function'

```Javascript
const summarizeUser=(userName,userAge,userHashHobby)=>{
     return(
        'Name is'+userName+ ', age is' +userAge+ ' and hobbies'+userHasHobby
    );
}

// if the function in in one line then you can shorten it even further, getting rid of "{}, "return*

const summarizeUser=(userName,userAge,userHashHobby)=>'Name is'+userName+ ', age is' +userAge+ ' and hobbies'+userHasHobby
}

// If there is only one parameter then you can also get rid of parameter brackets()
const summarizeUser=userName=>'Name is'+userName'
}

// But if there are no parameters needed in the functions then empty paranthesis () should be mentioned
const summarizeUser=()=>'Name is Jay'
}

```
- Note that you cannot use `.this` inside the function if you are using an arrow function

**Arrays and Looping through array**
- Objects and arrays are reference types which means that even with using constants `const` variables- the values can be changed. Which means for example if you use `.push` method you can modify the array.


```Javascript
const hobbies=['sports', 'Cooking'];

// Traditional syntax

for(var i = 0; i < 10; i++){
    console.log(i)
}

// Modern ES6 Javascript
// you are assigining a 'parameter name' of hobby to each individual datapoint in the hobbies array
for (let hobby of hobbies){
    console.log(hobby);
}

```

**Using Map on Arrays**
- Map takes an existing array and modifies the individual components inside the array

```Javascript
consol.log(hobbies.map(hobby=>'Hobby:'+hobby))
// here you have specified to print "hobby" before printing each individual hobby
```

**Using Spread operator**
- The spread operator copies all the contents (elements in array or object properties in objects) of whatever follows the three ...
- Behind the scenes what this does is pulls out all the individual elements one by one and then copies them into the new array
- It works for both objects and arrays

```javascript
const hobbies=['sports', 'Cooking'];
const hobbies2={
    sports:'sports'
    cooking:'cooking'
}
const copiedArray=[...hobbies]; //hobbies is a pre-existing array in this case
const copiedArray={...hobbies2}; //hobbies is a pre-exisiting object in this case
```

**Using Rest operator**
- Rest operator can be used to merge multiple arguments into an array

```javascript
const toArray=(...args)=>{
    return args;
    };

    console.log(toArray(1,2,3,4))
    // Note that it gives more flexibility with regards to how many arguments you want to pass into the array
