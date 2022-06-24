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
