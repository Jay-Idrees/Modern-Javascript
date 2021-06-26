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
```

**Object Destructuring**
- You can extract specific elements/properties from an objects. Note that all the idividual contents of an object are usually called properties
- Note that unlike Array destructuring, the names of the elements/properties must exactly match as in the object from which they are being extracted. In contrast for arrays the names need not to match exactly, the destructring operates by the location of index

```javascript
// Below is our object
const person={
    name:'Jay',
    age:29,
    greet(){console.log('Hi, I am '+ this.name);};//Here this refers to the person object
}

//Traditional way of extracting elements:
const printName=(person)=>{ //Note that the 'person' here is a parameter not the person object
    console.log(person.name);
};
printName(person) //The person here is the person object itself that is being passed as argument for the parameter

// You can also directly destructure an object inside the function paranthesis

const printName=({name,age})=>{ 
// Here when the object person is passed you are telling it to extract only name and age, which will be stored as variables
    console.log(name, age);
}
printName(person)

// The modern Javascript way of object destructuring is as below:

const {name, age}=person;
// here you are extrcting name and age from the person object
```
**Array Destructuring**
- Similar to object destructuring, except that it operated by index location rather than the exact name of the element being extracted

```javascript
const hobbies=['Sports', 'Cooking'];
const [hobby1,hobby2]=hobbies // Note that you are usiing a name different from sports or cooking
console.log(hobby1,hobby2)
```