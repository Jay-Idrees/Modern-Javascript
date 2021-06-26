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
