
<h1 align="center">Week No. 5</h1></br>

2. [Monday](#1-monday)
3. [Tuesday](#3-tuesday)


## 1. Monday
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
The input is a string str of digits. Cut the string into chunks (a chunk here is a substring of the initial string) of size sz (ignore the last chunk if its size is less than sz).</br>

If a chunk represents an integer such as the sum of the cubes of its digits is divisible by 2, reverse that chunk; otherwise rotate it to the left by one position. Put together these modified chunks and return the result as a string.</br>

If</br>

-sz is <= 0 or if str is empty return ""</br>
-sz is greater (>) than the length of str it is impossible to take a chunk of size sz hence return "".</br>
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

## 3. Tuesday	
### Exercise 1

`Solution`:

```typescript
export type User = {
    name: string;
    age: number;
    occupation: string;
};

export const users: User[] = [
    {
        name: 'Max Mustermann',
        age: 25,
        occupation: 'Chimney sweep'
    },
    {
        name: 'Kate Müller',
        age: 23,
        occupation: 'Astronaut'
    }
];

export function logPerson(user: User) {
    console.log(` - ${user.name}, ${user.age}`);
}

console.log('Users:');
users.forEach(logPerson);
```

<a name="tp_unions"></a>

### Exercise 2


Unions:

`Solution`:
 ```typescript
 interface User {
    name: string;
    age: number;
    occupation: string;
}

interface Admin {
    name: string;
    age: number;
    role: string;
}

export type Person = User | Admin;

export const persons: Person[]  = [
    {
        name: 'Max Mustermann',
        age: 25,
        occupation: 'Chimney sweep'
    },
    {
        name: 'Jane Doe',
        age: 32,
        role: 'Administrator'
    },
    {
        name: 'Kate Müller',
        age: 23,
        occupation: 'Astronaut'
    },
    {
        name: 'Bruce Willis',
        age: 64,
        role: 'World saver'
    }
];

export function logPerson(user: Person) {
    console.log(` - ${user.name}, ${user.age}`);
}

persons.forEach(logPerson);
 ```
 ### Exercise 3
 `Solution`:
```typescript
interface User {
    name: string;
    age: number;
    occupation: string;
}

interface Admin {
    name: string;
    age: number;
    role: string;
}

export type Person = User | Admin;

export const persons: Person[] = [
    {
        name: 'Max Mustermann',
        age: 25,
        occupation: 'Chimney sweep'
    },
    {
        name: 'Jane Doe',
        age: 32,
        role: 'Administrator'
    },
    {
        name: 'Kate Müller',
        age: 23,
        occupation: 'Astronaut'
    },
    {
        name: 'Bruce Willis',
        age: 64,
        role: 'World saver'
    }
];

export function logPerson(person: Person) {
    let additionalInformation: string;
    if ('role'in person) {
        additionalInformation = person.role;
    } else {
        additionalInformation = person.occupation;
    }
    console.log(` - ${person.name}, ${person.age}, ${additionalInformation}`);
}

persons.forEach(logPerson);
```

 ### Exercise 4
 
 Same as 3 but using if sentence </br>
`Solution`:
```typescript
export function logPerson(person: Person) {
    let additionalInformation: string = '';
    if ('role' in person) {
        additionalInformation = person.role;
    }
    if ('occupation' in person) {
        additionalInformation = person.occupation;
    }
    console.log(` - ${person.name}, ${person.age}, ${additionalInformation}`);
}
```
 ### Exercise 4
 
 Same as 3 but using if sentence </br>
`Solution`:
```typescript
interface User {
    type: 'user';
    name: string;
    age: number;
    occupation: string;
}

interface Admin {
    type: 'admin';
    name: string;
    age: number;
    role: string;
}

export type Person = User | Admin;

export const persons: Person[] = [
    { type: 'user', name: 'Max Mustermann', age: 25, occupation: 'Chimney sweep' },
    {
        type: 'admin',
        name: 'Jane Doe',
        age: 32,
        role: 'Administrator'
    },
    {
        type: 'user',
        name: 'Kate Müller',
        age: 23,
        occupation: 'Astronaut'
    },
    {
        type: 'admin',
        name: 'Bruce Willis',
        age: 64,
        role: 'World saver'
    },
    {
        type: 'user',
        name: 'Wilson',
        age: 23,
        occupation: 'Ball'
    },
    {
        type: 'admin',
        name: 'Agent Smith',
        age: 23,
        role: 'Administrator'
    }
];

export const isAdmin = (person: Person): person is Admin => person.type === 'admin';
export const isUser = (person: Person): person is User => person.type === 'user';

export function logPerson(person: Person) {
    let additionalInformation = '';
    if (isAdmin(person)) {
        additionalInformation = person.role;
    }
    if (isUser(person)) {
        additionalInformation = person.occupation;
    }
    console.log(` - ${person.name}, ${person.age}, ${additionalInformation}`);
}

export function filterUsers(persons: Person[], criteria: Partial<Omit<User, 'type'>>): User[] {
    return persons.filter(isUser).filter((user) => {
        const criteriaKeys = Object.keys(criteria) as (keyof Omit<User, 'type'>)[];
        return criteriaKeys.every((fieldName) => {
            return user[fieldName] === criteria[fieldName];
        });
    });
}

console.log('Users of age 23:');

filterUsers(
    persons,
    {
        age: 23
    }
).forEach(logPerson);
```
