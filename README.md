# Reference book - JavaScript

## Obsah (Table of Contents)

1. [Začátečnická úroveň (Beginner Level)](#začátečnická-úroveň-beginner-level)
   - [Datové typy (Data Types)](#datové-typy-data-types)

## Začátečnická úroveň (Beginner Level)

### Datové typy (Data Types)


1. **Primitivní typy (Primitive Types):**
   - `String` (Řetězec)
   - `Number` (Číslo)
   - `Boolean` (Logická hodnota)
   - `Undefined` (Nedefinováno)
   - `Null` (Prázdná hodnota)
   - `Symbol`
   - `BigInt`

2. **Objektové typy (Object Types):**
   - `Object` (Objekt)
   - `Array` (Pole)
   - `Function` (Funkce)

Příklady:

```javascript
// Strings (Řetězce)
let name1 = "John Doe";
let name2 = 'John Doe';
let name3 = `John Doe`;

// Numbers (Čísla)
let age = 30;
let price = 19.99;

// Booleans (Logické hodnoty)
let isActive = true;
let hasLicense = false;

// Undefined
let uninitializedVar;

// Null
let emptyVar = null;

// Symbol
let uniqueId = Symbol('id');

// BigInt
let bigNumber = BigInt(1234567890123456789012345678901234567890);

// Object (Objekt)
let person = {
    firstName: "John",
    lastName: "Doe",
    age: 30
};

// Array (Pole)
let fruits = ["Apple", "Banana", "Cherry"];

// Function (Funkce)
function greet(name) {
    return "Hello, " + name;
}
```

Cvičení:
1. Vytvořit proměnné pro každý datový typ a vypsat je do konzole.
- _<details><summary>Možné řešení</summary>_

    ```javascript
    // String
    let str = "Hello, World!";
    console.log("String:", str);
    // Output: String: Hello, World!

    // Number
    let num = 42;
    console.log("Number:", num);
    // Output: Number: 42

    // Boolean
    let bool = true;
    console.log("Boolean:", bool);
    // Output: Boolean: true

    // Undefined
    let undef;
    console.log("Undefined:", undef);
    // Output: Undefined: undefined

    // Null
    let nullVar = null;
    console.log("Null:", nullVar);
    // Output: Null: null

    // Symbol
    let sym = Symbol("unique");
    console.log("Symbol:", sym);
    // Output: Symbol: Symbol(unique)

    // BigInt
    let bigInt = BigInt(9007199254740991);
    console.log("BigInt:", bigInt);
    // Output: BigInt: 9007199254740991n

    // Object
    let obj = { name: "John", age: 30 };
    console.log("Object:", obj);
    // Output: Object: { name: "John", age: 30 }

    // Array
    let arr = [1, 2, 3, 4, 5];
    console.log("Array:", arr);
    // Output: Array: [1, 2, 3, 4, 5]

    // Function
    let func = function() { return "I am a function"; };
    console.log("Function:", func);
    // Output: Function: [Function: func]
    console.log("Function:", func());
    // Output: Function: I am a function
    ```
    
   </details>
2. Zkusit sečíst číslo a řetězec. Co se stane? Proč?
- _<details><summary>Možné řešení</summary>_

    ```javascript
    let number = 5;
    let string = "pet";
    let result = number + string;
    console.log(result); 
    // Output: 5pet
    // Output je string
    ```

   </details>
3. Vytvořit objekt reprezentující knihu s vlastnostmi jako název, autor a rok vydání.
- _<details><summary>Možné řešení</summary>_

    ```javascript
    let book = {
        nazev: "1984",
        autor: "George Orwell",
        rokVydani: 1949,
        zanr: "Dystopická fikce",
        pocetStran: 328,
        jeKDispozici: true,
    
        vypisPodrobnosti: function() {
            console.log(`${this.nazev} od ${this.autor}, vydáno v roce ${this.rokVydani}`);
        }
    };

    console.log(book);
    // Output:
    // {
    //   nazev: '1984',
    //   autor: 'George Orwell',
    //   rokVydani: 1949,
    //   zanr: 'Dystopická fikce',
    //   pocetStran: 328,
    //   jeKDispozici: true,
    //   vypisPodrobnosti: [Function: vypisPodrobnosti]
    // }

    book.vypisPodrobnosti();
    // Output: 1984 od George Orwell, vydáno v roce 1949
    ```

   </details>

[**CheatSheet - Data Types**](cheatsheet.md#datové-typy-data-types)

[Zpět na obsah](#obsah-table-of-contents)

