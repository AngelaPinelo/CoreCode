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
