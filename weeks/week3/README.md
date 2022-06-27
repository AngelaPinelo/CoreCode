<h1 align="center">Week No. 3</h1>

1. [Monday](#1-monday)
2. [Tuesday](#1-tuesday)
2. [Wednesday](#2-wednesday)
4. [Thursday](#3-thursday)

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
#### Your order, please
**Instruccions:** Your task is to sort a given string. Each word in the string will contain a single number. This number is the position the word should have in the result.</br>

Note: Numbers can be from 1 to 9. So 1 will be the first word (not 0).</br>

If the input string is empty, return an empty string. The words in the input String will only contain valid consecutive numbers.</br>
**Solution:**
```javascript
function order(words){
  
  if(words == "") return ""
  words = words.split(" ")
  numeros = []
  
  for (let i = 0; i < words.length; i++) {
      cadena = words[i]
      for (let j = 0; j < cadena.length; j++) {
          numeros.push(Number(cadena[j]));
      }
  }
  numeros.sort();
  words2 = []
  for (let i = 0; i < numeros.length; i++) {
      numeros_str = ""+numeros[i]
      for (var j = 0; j < words.length; j++) {
          if(words[j].includes(numeros_str)){
              words2.push(words[j])
          }
      }
  }
  words2 = words2.join(" ")
  return words2
  
}
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
#### Counting Duplicates
**Instruccions:** Write a function that will return the count of distinct case-insensitive alphabetic characters and numeric digits that occur more than once in the input string. The input string can be assumed to contain only alphabets (both uppercase and lowercase) and numeric digits.
**Solution:**
```javascript
function duplicateCount(text) {
  //we use toLowerCase() to make it case insensitive  
  text = text.toLowerCase().split('').sort();
  //text is now an Array made by it owns elements
  let indice = 0, result = 0, lastIndexOfChar = 0;
  //indice works as the i in the for loops
  while (text.length) {
    lastIndexOfChar = text.lastIndexOf(text[indice]);
    if (lastIndexOfChar !== indice) {
      indice = lastIndexOfChar;
      result++;
    }
    //++indice incrementa el valor y luego lo devuelve 
    text = text.slice(++indice);
    indice = 0;
  }
  return result;
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
#### Convert string to camel case
***Instructions:*** Complete the method/function so that it converts dash/underscore delimited words into camel casing. The first word within the output should be capitalized only if the original word was capitalized (known as Upper Camel Case, also often referred to as Pascal case).
**Solution:**
```javascript
function toCamelCase(str){    
  //first of we remove the "-" and replace it with an "_"
  //this way it's going to be easier to work with avoiding more validations
    str=str.replace(/-/g, '_')
    let resultado=''    
    for (let i = 0; i < str.length; i++) {
      if (i != 0 && (str[i - 1] === '_' )) {
        resultado+= str[i].toUpperCase();
      } else if (str[i] != '_') {
        resultado += str[i];
      }
    }     
     return resultado
   }
```
#### Unique in Order
***Instructions:*** Implement the function unique_in_order which takes as argument a sequence and returns a list of items without any elements with the same value next to each other and preserving the original order of elements.
**Solution:**
```javascript
var uniqueInOrder=function(iterable){
 //since we only need to search for a repeated character that is next to another
  let repeated=''
  //this array will store the output 
  let answer=[]
  //we use a for loop for 'iterable'
  for(let i=0; i<iterable.length;i++){
    //first we need to compare the actual character to the last one
    if(iterable[i]!= repeated){
      answer.push(iterable[i])
      //in repeated we storage the last letter in the string
      repeated=iterable[i]
    }
  }return answer
}
```
## Thursday
### Solve the following exercises:
#### Encrypt this!
**Instructions:** You want to create secret messages which can be deciphered by the Decipher this! kata. Here are the conditions: </br>

-Your message is a string containing space separated words.</br>
-You need to encrypt each word in the message using the following rules:</br>
-The first letter must be converted to its ASCII code.</br>
-The second letter must be switched with the last letter</br>
-Keepin' it simple: There are no special characters in the input.</br>
**Solution:**
```javascript
var encryptThis = function(text) {   
  //now, we're going to use split to separate every word in text
  text=text.split(' ')
  let respuesta=[]
  //a for loop for every word in 'text'
  for(let i=0;i<text.length; i++){
    //we call another fuction that receives as a parameter the word and returns the modified word
    let palabra=Word(text[i])
    //once we have the modified word we send it to the respuesta arrayy
    respuesta.push(palabra)
    //Last but not least xd we join them with a space ' '
  } return respuesta.join(' ')
  
}

function Word(word){
  //on this variables we are going to store the modified text
  let firstLetter='', RestText='', InTheMiddle='';
  if(word.length===2){
    //the first letter of the word store it's value in ASCII
    firstLetter = word[0].charCodeAt(0)
    //the final string returns the first letter plus a slice of the original word without the first letter
    return `${firstLetter}${word.slice(1)}`
  }else if(word.length>2){
      firstLetter = word[0].charCodeAt(0)
      //InTheMiddle it's the last letter of the original word
      InTheMiddle =word[1]
      //rest of the text it's the text that we do not need to modify
      RestText = word[word.length-1]
    //we modify the original word
      word = word.slice(2, word.length-1);
      word = `${firstLetter}${RestText}${word}${InTheMiddle}`
      return word
  }else{
    //if text it's just 1 letter we return the ASCII value
      return word.charCodeAt(0)
    }
  
}
```
