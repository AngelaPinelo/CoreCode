
<h1 align="center">Week No. 5</h1></br>

2. [Monday](#1-monday)
3. [Thursday](#3-thursday)


## 1. monday
### Find the missing letter
#### Instructions: 
Write a method that takes an array of consecutive (increasing) letters as input and that returns the missing letter in the array.</br>

You will always get an valid array. And it will be always exactly one letter be missing. The length of the array will always be at least 2.</br>
The array will always contain letters in only one case.
</br>
`Solution`:
```javascript
  function findMissingLetter(array) {
  //we´re going to use charCodeAt bc it give us the unicode value of the letter
  for (let i = 0; i < array.length; i++) {
    if (array[i].charCodeAt() + 1 !== array[i + 1].charCodeAt()) {
  //with fromCharCode we can get the letter from the unicode value
      let a= String.fromCharCode(array[i].charCodeAt() + 1);
      return a
    }
  }
}
```
### Reverse or Rotate  
#### Instructions: 

</br>

`Solution`:

```javascript
 function revrot(str, sz) {
  if (sz <= 0 || sz >= str.length || str === '') return ''
  let regex = new RegExp(`\\d{${sz}}`, 'g')
  let chunks = str.match(regex)
  let sum = 0, chunkr=[]
  let resultado = chunks.map((chunk) => {
    sum = chunk
      .split('')
      .map((digit) => Math.pow(+digit, 3))
      .reduce((prev, curr) => prev + curr, 0);
    chunkr = chunk.split('')
    if (sum % 2 == 0) return chunkr.reverse().join('')
    return chunkr.push(chunkr.shift()), chunkr.join('')
  });
  return resultado.join('')
}
```

## 3. Thursday	
### String Cleaning 
#### Instructions: 
Your boss decided to save money by purchasing some cut-rate optical character recognition software for scanning </br>
in the text of old novels to your database. At first it seems to capture words okay, but you quickly notice that it throws </br>
in a lot of numbers at random places in the text.
</br>
`Solution`:
```javascript
  function stringClean(s){
  // we just need to remove the numbers 
  let a=s.replace(/\d+/g,'')
  return a
}
```
### Regex password validation 
#### Instructions: 
You need to write regex that will validate a password to make sure it meets the following criteria:</br>

-At least six characters long</br>
-contains a lowercase letter</br>
-contains an uppercase letter</br>
-contains a number</br>
Valid passwords will only be alphanumeric characters.</br>
</br>
`Solution`:
```javascript
  function validate(password) {
  return /^[A-Za-z0-9]{6,}$/.test(password) 
  //we can use the symbol + to indicate that it will came at least one time 
  && /[a-z]+/.test(password) 
  //or we can also use the {1} for the same purpose
  && /[A-Z]{1}/.test(password)
  && /\d{1}/.test(password);
}
```

