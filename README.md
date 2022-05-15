

# Week Challenges  

- Week 1 : [Introduction to programming & Javascript](weeks/week1)
- Week 2: [Javascript](weeks/week2)
- Week 3: [Javascript](weeks/week2)
- Week 4: [End Of Month & Pause Day](weeks/week2)
- Week 5: [Typescript](weeks/week2)

<h1 align="center">Week No. 1</h1>

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
<h1 align="center">Week No. 3</h1>

## Monday
### Solve the following exercises:
#### Who likes it? 
**Solution:**
```javascript
function likes(names) {
  let response=''
  if (names.length==0){
    response='no one likes this'
  }else{
    if (names.length==1){response = names[0]+' likes this'}
    else if(names.length==2){response = names[0]+' and ' + names[1]+' like this'}
    else if(names.length==3){response = names[0]+', ' + names[1]+' and '+names[2]+' like this'}
    else{response=names[0]+', ' + names[1]+' and '+(names.length-2)+' others like this'}
  } return response;
}
```
#### Bit Counting
**Solution:**
```javascript
var countBits = function(n) {
  // using the function toString(2) returns the binary of the number 
  let binario= n.toString(2)
  //we need to count the 1's in binario 
  let ones=0
  for (let number=0; number<binario.length; number ++){
    if (binario[number]==1){ones+=1}
  }return ones
};
```
## Tuesday
#### Simple Pig Latin
**Solution:**
```javascript
function pigIt(str){
  
  let word = str.split(' ');
  for(let char=0; char<word.length; char++){    
    if(word[char]=='!' || word[char]=='?')continue
    word[char]= word[char].slice(1)+ word[char].slice(0,1)+'ay'
  }return word.join(' ')
}
```
## Wednesday
#### Valid Parentheses
**Solution:**
```javascript
function validParentheses(parens) {
  let contador = 0;
  for (let i = 0; i < parens.length; i++) {
    if (parens[i] == ')') contador-=1;
    if (parens[i] == '(') contador+=1;
    if (contador < 0) return false;
  }
  return contador == 0;
}
```
