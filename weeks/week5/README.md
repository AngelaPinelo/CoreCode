
<h1 align="center">Week No. 4</h1></br>

2. [Wednesday](#2-wednesday)
3. [Thursday](#3-thursday)


## 2. Wednesday
### Simple Validation of a Username 
#### Instructions: 
Write a simple regex to validate a username. Allowed characters are: </br>
-lowercase letters,</br>
-numbers,</br>
-underscore</br>
Length should be between 4 and 16 characters (both included).</br>
</br>
`Solution`:
```javascript
  function validateUsr(username) {
  res =  /^[a-z0-9_]{4,16}$/.test(username) 
  return res
}
```
### Get Number from String  
#### Instructions: 
Write a function which removes from string all non-digit characters and parse the remaining to number
</br>
`Solution`:
```javascript
  function getNumberFromString(s) {
  let a= s.replace(/\D/g, '');
  let b= parseInt(a)
  return b 
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
