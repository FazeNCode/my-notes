<h2> What is TypeScript: </h2>
It’s a superset of JavaScript, developed by Microsoft.
Compiles to plain JavaScript.
Browsers normally don't know how to run TypeScript code,  so that means you need a compiler to compile it down to it's original language 'JavaScript'
tsconfig.json file is used to configure how TypeScript Works

PROS:
------
More Robust 
Easily Spot Bugs
Predictability 
Readability

Cons:
-----
More Code To Write
More To learn 
Required Compilation 	
Not True Static Typing



Commands:
--------

Compile the typescript to plain javascript
```
tsc filename  
```

Start watch mode
```
tsc --watch filename 
```

Create the tsconfig file
```
tsc --init 	
```

      REACT  (JSX) JavaScript-Syntax-Extension 
		is considered to be a framework like Angular or Vue, 
		but it lacks built in functionality. To add functions in react
	You download packages for example, Npm to create.  Npx to execute

	
		
-VARIABLES-, var,  let,  const 



-DATA TYPES- Strings, Characters, Boleen, Null, Undefined, Symbols




-Concatenation-
---------------------
console.log("My name is " + name +" and my age is" + age);


-Template Strings-
-----------------------
// console.log(`My name is ${name} and I am ${age} years old`);
//const info = `My name is ${name} and I am ${age} years old`
// console.log(info);





-Methods-
------------------------------------------------------------------------
A method is a function that is associated with a object

console.log(f.length); 
A property doesn't use double parentheses 

console.log(f.toUpperCase());
A method must use double parentheses for it to work () A method is a function that is associated with a object

//console.log(f.substring(0,3));
Substring method is to count the number of strings in the character: Remember a method must be wrapped with double parenthesis.

//console.log(tech.split(' ,')) 
Split method is a type of an array, which you can add lists to




<h3> Data types </h3> 
numbers ---> 1, 2 ,3 ,4 ,5
strings ---> "hello" , 'hey' , 'a' "B"
arrays --->  []
objects ---> {}
boolean ---> true /false


<h3> Math Operators </h3>
Multiply --->  *
Divide --->  /
Exponents --->  **
Modulus/Remainder -->  %  5%2=1
Addition --->  +
Subtraction --->  -



<h3> Math Methods </h3>
Math.floor ---> Rounds down
Math.ciel --->  Rounds up
Math.random ---> gives a random
*/


<h3> Variables </h3>
Var ---> OutDated no longer used as much
Let ---> Global variable, can be changed
Const ---> Constant variable, cannot be changed



<h3>  Conditionals </h3>
== ---> Checks for equality
=== ---> Checks for equality and data type
> ---> Greater than
< ---> Less than
>= ---> Greater than or equals to
<= ---> Less than or equals to

// Weather app   (Conditionals)
// let weather = prompt("How is the weather")
// // If there is rain, grab yourself an umbrella
// if (weather == 'rain') {
//     console.log ("Grab yo umbrella it's poruin out there famdem")
// }
// // if it's not raining, grab yo shorts an t-shirt
// else{
//     console.log("Appears to be no rain in sight, you can wear your shorts and t-shirt")
// }


Functions can store block of codes
This is an example of function with no argument

```
function callingFunction(){
 console.log('I'm calling a function')
}
callingFunction()

```


This is an example of a function with an argument
```
function myName(name){
     console.log(name)
}
 myName('faze')

```


```

// // Created a function name greeting
// // passing an argument "name" in the greeting function
// function greeting(name){


//             // String concatenation
//     console.log("hey" + " " + name  + " nice to meet you!")
//             // Template Literals
//     greet = `hey ${name} nice to meet you!`
     
//         console.log(greet)
// }
// //This is how you call a function
// greeting('faisal')

```

```
// function sum(a, b){
//     // the return statement makes the function reusable, you can use the same function in multiple places
//     return a + b
// }
// num1 = sum(1, 2)
// console.log(num1)


```



// Template literals provide an easy way to interpolate variables and expressions into string.
// Interpolation is an efficient way of concatenation
// String Interpolation, references a variable within a string.

```
// ES6 Version of writng the function
function foodTotalCost(food , tip){
    const tipPercentage = tip / 100
    const tipAmount = food * tipPercentage

    // total = food + tipAmount
    const total = sum(food, tip)
    return total
}
console.log(foodTotalCost (100 , 20))

```

