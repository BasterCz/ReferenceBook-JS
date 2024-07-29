# Cheatsheet

## Začátečnická úroveň (Beginner Level)

### Datové typy (Data Types)

```javascript
let string1 = "John Doe";                   // John Doe
let string2 = 'Hello';                      // Hello
let string3 = `Welcome, ${string1}!`;       // Welcome, John Doe!

let bool1 = true;                           // true
let bool2 = false;                          // false

let undefined1;                             // undefined

let num1 = 30;                              // 30
let num2 = 19.99;                           // 19.99

let bigInt1 = BigInt(9007199254740991);     // 9007199254740991n 

let null1 = null;                           // null

let symbol1 = Symbol('id');                 // Symbol(id)

let obj1 = {                                // { firstName: 'John', lastName: 'Doe', age: 30 }
    firstName: "John",                      
    lastName: "Doe",                        
    age: 30
};

let array1 = ["Apple", "Banana", "Cherry"]; // [ 'Apple', 'Banana', 'Cherry' ] 

function fnc1(name) {                       
    return "Hello, " + name;
}
                                           
console.log(fnc1)                           // [Function: function1] 
console.log(fnc1("Petr"))                   // Hello, Petr 
```

![Console output - Data Types](screenshots/console-output-data-types.png)

[**ReferenceBook - Data Types**](README.md#datové-typy-data-types)