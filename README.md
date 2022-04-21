<h1 align="center">Week No. 1</h1>

# Week Challenges
1. [Tuesday](#1-tuesday)
2. [Wednesday](#2-wednesday)
3. [Thursday](#3-thursday)

## 1. Tuesday
### Programming Languages
We know how  all programming languages work: You write code to the computer to tell it what to do, but there are actually 2 different types of programming languages: compiled and interpreted. <br>
#### Compiled
A **Compiler** can be defined as a machine or a program that converts instructions from one language to another, for programming languages a compiler converts the code to a machine-languaje or low level language so that it can be read and executed by a computer. <br>
Compiled Languages are directly translated to a machine code that it's executed by the processor. This types of languages give more control over the memory management, every time you need to change the code the program needs to be "rebuiled" (that means it needs to be compiled again). Some examples of this types of languages are: C,C++,Rust.
#### Interpreted
An **Interpreter** it's a program that reads the code line by line and traduce it to the computer for it to execute each instruccion line by line. Interpreted Languages do exactly the same, they are executed line by line. Some examples of this languages are: Python, JavaScript, Ruby. 
### Is Java Compiled, Interpreted or both?
Java uses a two-step compilation using the Java compiler and the Java Virtual Machine (JVM). The Java Compiler checks the correct syntax of the code. Java Compiler is designed to be a bytecode compiler, it creates a file  written purely in bytecode based on the written code. Java Virtual Machine interprets the bytecode by loading the class file to machine Language.
### Pseudocode exercise
```
  1. START
  2. Amount  <-- Get (From User)
  3. BitValue <-- Get From (https://www.google.com/finance/quote/USD-BTC)
  4. Total <-- Amount * BitValue
  5. PRINT Total
  6. END
```
## 2. Wednesday
### Date of birth in binary
My year of birth: 2002

| 2^n | 2^10 | 2^9 | 2^8 | 2^7 | 2^6 | 2^5 | 2^4 | 2^3 | 2^2 | 2^1 | 2^0 |
| ---- | ---- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Valor | 1024 | 512 | 256 | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1|
|Resultado:| 1    | 1   | 1   | 1   | 1   | 0   | 1  | 0   | 0   | 1   | 0   |

[This video was used to solve the exercise](https://youtu.be/fGu0tM5u4b4)
### MIPS 
`Program that display my name`:
```assembly
  .data
	      name: .asciiz "\nAngela Pinelo\n"
  .text
	      main:
              li $v0, 4
              la $a0, name
              syscall
```
`Program that adds any two given numbers provided by the user`:
```assembly
.data
               
        number1: .asciiz "Please enter the first number: "
        number2: .asciiz "Please enter the second number: "
        total: .asciiz "\nThe sum is: "
  .text
        main:
             
              li $v0, 4
              la $a0, number1
              syscall

              li $v0, 5
              syscall

              # saving 
              move $t0, $v0

              
              li $v0, 4
              la $a0, number2
              syscall

              li $v0, 5
              syscall

              # saving 
              move $t1, $v0

              # adding 
              add $t2, $t0, $t1

              # showing 
              li $v0, 4
              la $a0, total
              syscall

              # printing 
              li $v0, 1
              move $a0, $t2
              syscall
```

## 3. Thursday	
### Exercise No.1
`Print all the even numbers in range from 1 to 100`:
```javascript
//the letter i acts as an index, this means 
//it takes the value of the number as it increases in 1 
for (var i = 0; i <= 100; i++) {
 //the % or mod give us the reminer of a division
  if (i % 2 == 0) console.log(i);
}
```
### Exercise No.2
`Code correction`:
```javascript
var cond = false;
//The if statement evaluates a condition to execute an action
//that's why we need to use "==" to compare instead of "=" to asignate a value
if ((cond == true)) {
  console.log('The cond variable is true');
} else {
  console.log('The cond variable is false');
}
```
### Exercise No.3
`Code correction`:
```javascript
//We need to evaluate all the conditions at the same time
//that's why we use de and operator "&&" in the else if 
var n = 100;
if (n == 100) {
  console.log('This is a special number!');
}
 else if (n % 10 == 0 && n < 1000 && n!=100 ){  
  console.log('This number is almost special');
}else {
  console.log('Just a regular number');
}
```
<h1 align="center">Week No. 2</h1>

# Week Challenges
1. [Tuesday](Tuesday)
2. [Wednesday](wednesday)
3. [Thursday](#3-thursday)

## Tuesday
### Solve the following exercises:
#### Multiply 
The following code does not execute properly:
```javascript
function multiply(a, b) {
   a * b
}
```
Solution: </br> 
The function was missing the return statement
```javascript
function multiply(a, b) {
   return a * b;
}
```
#### ASCII Total
You'll be given a string, and have to return the sum of all characters as an int. </br>The function should be able to handle all ASCII characters. </br>
Solution:</br>
To solve this exercise easier we used the method "charCodeAt()" that returns an integer using the ASCII table. </br>
you can find more information about that method by clicking here: [charCodeAt()](https://developer.mozilla.org/en-US/docs/web/javascript/reference/global_objects/string/charcodeat)
```javascript
function uniTotal (string) {
let total = 0;
for (let i=0; i<string.length; i++){
  total+= string[i].charCodeAt();
}
return total;
}
```
#### Char From ASCII Value
Write a function which takes a number and returns the corresponding ASCII char for that value.</br>
Solution:
```javascript
function getChar(c){
  let letra = '';
  let index= c;
  letra=String.fromCharCode(c);
  return letra
}
```
#### Binary Addition
Implement a function that adds two numbers together and returns their sum in binary. The conversion can be done before, or after the addition.
</br>
The binary number returned should be a string.</br>
**Solution:** To solve this exercise we used "toString()" method, using this method with a number and passing as a </br>parameter the number "2"  returns the binary equivalent as a String.</br> You can find more information about this method by cliking here:  [toString()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/toString)
```javascript
function addBinary(a,b) {
let suma = 0;
suma = a+b;
let binary = 0;
binary = suma.toString(2);
  return binary;
}
```
#### Student's Final Grade
**Instructions**: Create a function finalGrade, which calculates the final grade of a student depending on two parameters: a grade for the exam and a number of completed projects.</br>

This function should take two arguments: exam - grade for exam (from 0 to 100); projects - number of completed projects (from 0 and above);</br>

This function should return a number (final grade). There are four types of final grades:</br>

100, if a grade for the exam is more than 90 or if a number of completed projects more than 10.</br>
90, if a grade for the exam is more than 75 and if a number of completed projects is minimum 5.</br>
75, if a grade for the exam is more than 50 and if a number of completed projects is minimum 2.</br>
0, in other cases
**Solution**: 
```javascript
function finalGrade (exam, projects) {
 let nota = 0;
  if (exam > 90 || projects > 10){
  nota = 100;
  }
  else if (exam > 75 && projects >= 5){
  nota = 90;
  }
  else if (exam > 50 && projects >= 2){
  nota = 75;
  }
  return nota;
}
```
## Thursday
### Solve the following exercises:
#### Remove All Exclamation Marks From The End Of Sentence
**Solution**: To solve this exercise we used the "replace()" method that basically replace values that are inside of a string </br> for others. You can learn more about this method by clicking here: [replace()](https://www.w3schools.com/jsref/jsref_replace.asp)
```javascript
function remove (string) {
  // we need to add an extra character to indacate the end of the string 
let cadena = string + '#'
let resultado = cadena.replace(/!+#/, '');
let resultado2 = resultado.replace ('#','');
  return resultado2;
}
```
#### Vowel Remover
**Instructions:** Create a function called shortcut to remove the lowercase vowels (a, e, i, o, u ) in a given string.
**Solution:** Again we used the replace method.
```javascript
function shortcut (string) {
  let no1= string.replace(/a/g ,'');
  let no2= no1.replace(/e/g,'');
  let no3= no2.replace(/i/g,'');
  let no4= no3.replace(/o/g,'');
  let no5= no4.replace(/u/g,'');
  return no5;
}
```
#### Rock Paper Scissors!
**Solution:**
```javascript
const rps = (p1, p2) => {
  let result =''
  if (p1 == p2){
    result = 'Draw!'
  }
  else if (p1 == 'scissors' && p2 == 'rock'){
    result ='Player 2 won!'
  }
  else if (p1 == 'scissors' && p2 == 'paper'){
    result ='Player 1 won!'
  }
  else if (p1 == 'rock' && p2 == 'scissors'){
    result ='Player 1 won!'
  }
  else if (p1 == 'rock' && p2 == 'paper'){
    result ='Player 2 won!'
  }
  else if (p1 == 'paper' && p2 == 'rock'){
    result ='Player 1 won!'
  }
  else if (p1 == 'paper' && p2 == 'scissors'){
    result ='Player 2 won!'
  }
  return result;
};
```
#### Persistent Bugger
**Solution:**
