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
        `Name is`+userName+ ', age is' +userAge+ ' and hobbies'+userHasHobby
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
        `Name is`+userName+ ', age is' +userAge+ ' and hobbies'+userHasHobby
    );
}

// if the function in in one line then you can shorten it even further, getting rid of "{}, "return*

const summarizeUser=(userName,userAge,userHashHobby)=>`Name is`+userName+ ', age is' +userAge+ ' and hobbies'+userHasHobby
}

// If there is only one parameter then you can also get rid of parameter brackets()
const summarizeUser=userName=>`Name is`+userName'
}
