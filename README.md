# `JavaScript ES6: Notes`

`ES6 stands for ECMAScript 6`. ECMAScript was created to standardize JavaScript, and ES6 is the 6th version of ECMAScript, it was published in 2015, and is also known as ECMAScript 2015.

<p align="center">
 <img width="400px" src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRBybT5AiMT6lKUBXFddhbZHbmTywnlibNhJA&usqp=CAU" align="center" alt="JavaScript ES6" />
 <h2 align="center">JavaScript ES6: Notes</h2>
</p>

---



// JavaScript ES5 vs ES6 features


// ***** Variables *****
// Variables declared with "var" in JavaScript are function scoped.
// Variables declared with "let & const" are block scoped.

// var name = 'John';
// console.log(name);      // John

// let name = 'Wick';
// console.log(name);      // Wick



// const PI = 3.141592653589793238;


// const name = 'John';
// name = 'Wick';
// console.log(name);      // TypeError





// *** Block & Function Scope ***
// Example 1:

// Return from block scope
// function modJS(love) {
//     if(love) {
//         var name = 'John';
//         var name2 = 'Wick';

//         console.log(`My name is ${name} ${name2}.`);      // My name is John Wick.
//     }
// }

// modJS(true);



// Return from function scope
// function modJS(love) {
//     if(love) {
//         var name = 'John';
//         var name2 = 'Wick';
//     }
//     console.log(`My name is ${name} ${name2}.`);      // My name is John Wick.
// }

// modJS(true);



// Return from function scope
// function modJS(love) {
//     if(love) {
//         let name = 'John';
//         const name2 = 'Wick';
//     }
//     console.log(`My name is ${name} ${name2}.`);      // ReferenceError
// }

// modJS(true);




// *** Block & Function Scope ***
// Example 2:

// var matchWinner = 'Aus';
// if(true) {
//     var matchWinner = 'Ban';
//     console.log(matchWinner);      // Ban
// }
// console.log(matchWinner);      // Ban



// let matchWinner = 'Aus';
// if(true) {
//     let matchWinner = 'Ban';
//     console.log(matchWinner);      // Ban
// }
// console.log(matchWinner);      // Aus






// ***** Template literals (Template strings) *****

// ES5
// var firstName = 'John';
// console.log("My name is " + firstName + ". I am 26.");      // My name is John. I am 26.

// ES6
// let firstName = 'John';
// let lastName = 'Wick';
// console.log(`My name is ${lastName}. I am 32.`);        // My name is Wick. I am 32.
// console.log(`${lastName}`.startsWith('W'));        // true
// console.log(`${lastName}`.endsWith('c'));        // false
// console.log(`${lastName}`.includes('ic'));        // true
// console.log(`${lastName}`.repeat(3));        // WickWickWick
// console.log(`${lastName} # `.repeat(3));        // Wick # Wick # Wick #
// console.log(`${firstName} ${lastName} | `.toUpperCase().repeat(3));        // JOHN WICK | JOHN WICK | JOHN WICK |



// let a = 20;
// let b = 30;
// console.log(`Result is ${a + b} not ${2 * a + b}.`);   // Result is 50 not 70.





// Swap two numbers without using third variable:

// let a = 5;
// let b = 10;

// let temp = a;
// a = b;
// b = temp;

// or just by array destructuring:
// [a,b] = [b,a];

// console.log(`The value of a is ${a} and the value of b is ${b}.`);
// The value of a is 10 and the value of b is 5.







// ***** Destructuring *****
// The Destructuring assignment syntax is a JavaScript expression that makes it possible to unpack values from arrays, or properties from objects, into distinct variables.


// ===== Array Destructuring =====

// Previously,
// const myLan = ['js', 'php', 'c', 'python', 'java'];

// var lan1 = myLan[0];
// var lan2 = myLan[1];
// var lan3 = myLan[2];

// console.log("My fav language is " + lan1);
// // My fav language is js


// ES6:
// const myLan = ['js', 'php', 'c', 'python', 'java'];

// let [lan1, lan2, lan3] = myLan;

// console.log(`My fav language is ${lan1}.`);
// // My fav language is js



// ES6:
// const myLan = ['js', 'php', 'c', 'python', 'java'];

// let [lan1,,,, lanLast] = myLan;

// console.log(`My fav language is ${lanLast}.`);
// // My fav language is java.






// ===== Object Destructuring =====

// Previously,
// const bioData = { 
//     name: 'John', 
//     age: 26, 
//     deg: 'MCS'
// }
// console.log(`My name is ${bioData.name}, I'm ${bioData.age} years old and my qualification is ${bioData.deg}.`);
//  // My name is John, I'm 26 years old and my qualification is MCS.


// ES6:
// const bioData = { 
//     name: 'John', 
//     age: 26, 
//     deg: 'MCS',
//     sub: {
//         major1: 'DevOps',
//         major2: 'ML'
//     }
// }

// let {name: myName, age, deg, sub} = bioData;

// console.log(`My name is ${myName}, I'm ${age} years old and my qualification is ${deg}. My major is in ${sub.major2}.`);

// // My name is John, I'm 26 years old and my qualification is MCS. My major is in ML.







// ***** Arrow Functions *****

// Arrow functions (Fat Arrow functions) are undoubtedly one of the most popular features of ES6. They introduced a new way of writing concise functions.

// ES5:
// var sum = function() {
//     var a = 5;
//     var b = 10;
//     return a + b;
// }
// console.log(sum());     // 15


// ES6:
// const sum = () => {
//     let a = 5;
//     let b = 10;
//     return a + b;
// }
// console.log(sum());     // 15


// let a = 5;
// let b = 10;
// const sum = () => a + b;
// console.log(sum());     // 15


// let a = 5;
// const sum = (b) => a + b;
// console.log(sum(10));     // 15


// const sum = (a,b) => a + b;
// console.log(sum(5,10));     // 15








// ***** Default Function Parameters *****

// Default function parameters allow named parameters to be initialized with default values if no value or undefined is passed.

// function multiply(a, b) {
//     console.log(a * b);
// }
// multiply(4);     // NaN



// function multiply(a, b) {
//     b = (typeof b !== 'undefined') ? b : 2
//     console.log(a * b);
// }
// multiply(4);     // 8


// ES6:
// const multiply = (a, b = 2) => {
//     console.log(`The result is ${a * b}.`);
// }
// multiply(4);     // The result is 8.


// const multiply = (a, b = 2, c = 5) => {
//     console.log(`The result is ${a * b * c}.`);
// }
// multiply(4);     // The result is 40.







// ***** Rest Parameters *****

// Rest parameter is an improved way to handle function parameter, allowing us to more easily handle various input as parameters in a function. The rest parameter syntax allows us to represent an indefinite number of arguments as an array.

// ES5:
// function sum(a,b) {
//     console.log(a+b);
// }
// sum(1,2,3,4,5,6);     // 3


// function sum(a,b,c,d,e,f) {
//     console.log(a+b+c+d+e+f);
// }
// sum(1,2,3,4,5,6);     // 21



// ES6:
// function sum(...anything) {
//     console.log(anything);       // returns array
// }
// sum(1,2,3,4,5,6,7,8,9);     // [ 1, 2, 3, 4, 5, 6, 7, 8, 9 ]


// function sum(...anything) {
//     console.log(...anything);       // returns values
// }
// sum(1,2,3,4,5,6,7,8,9);     // 1 2 3 4 5 6 7 8 9


// function sum(...anything) {
//     console.log(...anything);       // returns values

//     let total = 0;
//     for (let i of anything) {   // returns sum
//         total += i;
//     }
//     console.log(total);       // 45
// }
// sum(1,2,3,4,5,6,7,8,9);     // 1 2 3 4 5 6 7 8 9



// function cars(a,b,...c) {
//     console.log(`${a} ${b}`);       // Tesla BMW
//     console.log(c);                 // [ 'Ferrari', 'Ford', 'Porsche', 'AlfaRomeo' ]
//     console.log(c[0]);              // Ferrari
//     console.log(c.length);          // 4
//     console.log(c.indexOf('AlfaRomeo'));       // 3
// }
// cars('Tesla','BMW','Ferrari','Ford','Porsche','AlfaRomeo');     // 1 2 3 4 5 6 7 8 9






// ***** Spread Operator *****

// Spread operator allows an iterable to expand in places where 0+ arguments are expected. It is mostly used in variable array where there is more than 1 values are expected. It allows us the privilege to obtain a list of parameters from an array. Syntax of Spread operator is same as Rest parameter but it works completely opposite of it.

// ES5:
// function sum(a,b,c) {
//     console.log(a+b+c);
// }
// sum(1,2,3);     // 6


// function sum(a,b,c) {
//     console.log(a+b+c);
// }

// var myArr = [1,2,3];

// sum.apply(null, myArr);     // 6



// ES6:
// function sum(a,b,c) {
//     console.log(a+b+c);
// }

// var myArr = [1,2,3];

// sum(...myArr);     // 6



// Spread operator replace concat()
// ES5:
// let arr1 = [1,2,3];
// let arr2 = [4,5,6];

// arr1 = arr1.concat(arr2);
// console.log(arr1);          // [ 1, 2, 3, 4, 5, 6 ]



// ES6:
// let arr1 = [1,2,3];
// let arr2 = [4,5,6];

// arr1 = [...arr1,...arr2];
// console.log(arr1);          // [ 1, 2, 3, 4, 5, 6 ]


// let arr1 = [1,2,3];
// let arr2 = [4,5,6];
// let arr3 = [7,8,9];

// arr1 = [...arr1,...arr2,...arr3];
// console.log(arr1);          // [ 1, 2, 3, 4, 5, 6, 7, 8, 9 ]




// Spread operator replace copy()
// ES5:
// let arrCopy1 = [1,2,3];
// let arrCopy2 = arrCopy1;    // One array is copied in another

// arrCopy2.push(4,5);         // Insert new array values
// console.log(arrCopy2);      // [ 1, 2, 3, 4, 5 ]
// console.log(arrCopy1);      // [ 1, 2, 3, 4, 5 ] original array changed 



// ES6:
// let arrCopy1 = [1,2,3];
// let arrCopy2 = [...arrCopy1,4,5];    // One array is copied in another with new values

// console.log(arrCopy2);      // [ 1, 2, 3, 4, 5 ]
// console.log(arrCopy1);      // [ 1, 2, 3 ]



// let arrCopy1 = [1,2,3];
// let arrCopy3 = [6,7,8];
// let arrCopy2 = [...arrCopy1,4,5,...arrCopy3,9];    // One array is copied in another with new values

// console.log(arrCopy2);      // [ 1, 2, 3, 4, 5, 6, 7, 8, 9 ]
// console.log(arrCopy1);      // [ 1, 2, 3 ]






// ***** Math Object *****

// Math.sign(), Math.trunc()

// let number = -5.55;
// console.log(Math.sign(number));
// // -1   meaning negative

// let number2 = 5.55;
// console.log(Math.sign(number2));
// // 1   meaning positive

// let number3 = 0;
// console.log(Math.sign(number3));
// // 0   meaning zero

// let number4 = NaN;
// console.log(Math.sign(number4));
// // NaN   meaning Not a Number

// let name = 'John';
// console.log(Math.sign(name));
// // NaN   meaning Not a Number

// let number5 = 5.556;
// console.log(Math.trunc(number5));
// // 5   only show the number before decimal

// let number6 = -5.556;
// console.log(Math.trunc(number6));
// // -5   only show the number before decimal

// let number7 = 5.556;
// console.log(Math.floor(number7));
// // 5   only show the number before decimal

// let number8 = -5.556;
// console.log(Math.floor(number8));
// // -6   only show the number before decimal







// ***** Exponentiation Operator *****

// Exponentiation operator (**) raises the first operand to the power of the second operand.

// x ** y produces the same result as Math.pow(x,y)

// x and y both are operands
// x + y = is an expression


// let a = 5;
// let b = 3;
// console.log(a**b);   // 125 


// let a = 5;
// let b = 4;
// console.log(a**b);   // 625 


// let a = 10;
// console.log(a**4);   // 10000 


// let a = 10;
// let c = 4**a;
// console.log(c);   // 1048576


// console.log(10**4);  // 10000 








// ***** New Numbers & Global Methods *****

// isFinite(), isNaN(), Number.isInteger()

// Global isFinite() method returns false if the argument is infinity or NaN.

// let num = 5;
// console.log(isFinite(num));     // true     so it's finite


// let num2 = Infinity;
// console.log(isFinite(num2));     // false     so it's infinite


// let num5 = -5;
// console.log(isFinite(num5));     // true     so it's finite


// let num3 = NaN;
// console.log(isFinite(num3));     // false     so it's infinite


// let num4 = 'John';
// console.log(isFinite(num4));     // false     so it's infinite


// let num6 = -5;
// console.log(Number.isFinite(num6));     // true     so it's finite


// let num7 = NaN;
// console.log(Number.isFinite(num7));     // false     so it's infinite




// Global isNaN() method returns true if the argument is NaN.

// let num = 5;
// console.log(isNaN(num));     // false     so it's not NaN


// let num2 = 'John';
// console.log(isNaN(num2));     // true     so it's NaN


// let num3 = NaN;
// console.log(isNaN(num3));     // true     so it's NaN


// let num4 = Infinity;
// console.log(isNaN(num4));     // false     so it's not NaN


// let num5 = Infinity;
// console.log(Number.isNaN(num5));     // false     so it's not NaN


// let num6 = 'John';
// console.log(Number.isNaN(num6));     // false     so it's not NaN





// Number.isInteger() method returns true if the argument is an integer.

// let num = 5;
// console.log(Number.isInteger(num));     // true     so it's an integer

// let num1 = -5;
// console.log(Number.isInteger(num1));     // true     so it's an integer

// let num2 = 0;
// console.log(Number.isInteger(num2));     // true     so it's an integer

// let num3 = 5.1;
// console.log(Number.isInteger(num3));     // false     so it's not an integer






