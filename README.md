# Reference book - JavaScript

## Obsah (Table of Contents)

1. [Začátečnická úroveň (Beginner Level)](#začátečnická-úroveň-beginner-level)
   - [Datové typy (Data Types)](#datové-typy-data-types)
   - [Proměnné (Variables)](#proměnné-variables)

## Začátečnická úroveň (Beginner Level)

### Datové typy (Data Types)

JavaScript má několik základních datových typů, které lze rozdělit do dvou hlavních kategorií:

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

Iterabilita¹ datových typů:
- Iterabilní: String, Array, Map, Set, TypedArray, arguments object
- Neiterovatelné: Number, Boolean, Null, Undefined, Symbol, BigInt, Object (standardní)

Detailní popis každého datového typu:

1. **String**
   - Primitivní: Ano
   - Enumerable²: Ne (ale lze iterovat přes znaky)
   - Způsob exportu³: Hodnota
   - Popis: Reprezentuje textové řetězce. Může být uzavřen v jednoduchých (''), dvojitých ("") nebo zpětných (`) uvozovkách.
    ```javascript
    let text1 = 'Ahoj';
    let text2 = "Světe";
    let text3 = `Hodnota je: ${celeCislo}`; // Template literal
    ```

2. **Number**
   - Primitivní: Ano
   - Enumerable: Ne
   - Způsob exportu: Hodnota
   - Popis: Reprezentuje jak celá čísla, tak i desetinná čísla. JavaScript používá 64bitový formát double-precision floating-point pro všechna čísla.
    ```javascript
    let celeCislo = 42;
    let desetinneCislo = 3.14;
    let vedeckaNotace = 2.998e8; // 2.998 * 10^8
    ```

3. **Boolean**
   - Primitivní: Ano
   - Enumerable: Ne
   - Způsob exportu: Hodnota
   - Popis: Reprezentuje logickou hodnotu true nebo false.
   ```javascript
   let jeAktivni = true;
   let maLicenci = false;
   ```


4. **Undefined**
   - Primitivní: Ano
   - Enumerable: Ne
   - Způsob exportu: Hodnota
   - Popis: Reprezentuje proměnnou, která byla deklarována, ale nebyla jí přiřazena hodnota.
    ```javascript
    let nedifinovanaPtomenna;
    console.log(nedifinovanaPtomenna); // undefined
    ```


5. **Null**
   - Primitivní: Ano (technicky je to objekt, ale chová se jako primitivní typ)
   - Enumerable: Ne
   - Způsob exportu: Hodnota
   - Popis: Reprezentuje záměrnou absenci jakékoli hodnoty nebo objektu.
    ```javascript
    let prazdnaHodnota = null;
    ```

6. **Symbol**
   - Primitivní: Ano
   - Enumerable: Ne
   - Způsob exportu: Hodnota
   - Popis: Reprezentuje unikátní identifikátor. Často se používá jako klíč pro vlastnosti objektů.
    ```javascript
    let id = Symbol('id');
    let objekt = {
    [id]: 12345
    };
    ```

7. **BigInt**
   - Primitivní: Ano
   - Enumerable: Ne
   - Způsob exportu: Hodnota
   - Popis: Reprezentuje celá čísla libovolné přesnosti. Používá se pro velmi velká čísla.
   ```javascript
   let velkeCislo = 1234567890123456789012345678901234567890n;
   ```

8. **Object**
   - Primitivní: Ne
   - Enumerable: Ano (pro vlastní vlastnosti)
   - Způsob exportu: Reference
   - Popis: Kolekce klíč-hodnota párů. Základní stavební blok pro komplexní datové struktury.
    ```javascript
    let osoba = {
        jmeno: "Jan",
        vek: 30,
        adresa: {
            mesto: "Praha",
            psc: "11000"
        }
    };
    ```

9. **Array**
   - Primitivní: Ne (je to speciální typ objektu)
   - Enumerable: Ano
   - Způsob exportu: Reference
   - Popis: Uspořádaná kolekce hodnot. Indexováno od nuly.
    ```javascript
    let ovoce = ["jablko", "banán", "pomeranč"];
    ```

10. **Function**
    - Primitivní: Ne (je to speciální typ objektu)
    - Enumerable: Ne
    - Způsob exportu: Reference
    - Popis: Blok kódu navržený k provádění konkrétního úkolu. Může přijímat vstupy (parametry) a vracet výstup.
    ```javascript
    function pozdrav(jmeno) {
        return `Ahoj, ${jmeno}!`;
    }
    ```

11. **(Date)**
    - Primitivní: Ne (je to objekt)
    - Enumerable: Ne
    - Způsob exportu: Reference
    - Popis: Reprezentuje datum a čas.
    ```javascript
    let ted = new Date();
    ```

12. **(RegExp)**
    - Primitivní: Ne (je to objekt)
    - Enumerable: Ne
    - Způsob exportu: Reference
    - Popis: Reprezentuje regulární výraz pro pokročilé vyhledávání a manipulaci s textem.
    ```javascript
    let emailRegex = /^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/;
    ```

13. **(Map)**
    - Primitivní: Ne (je to objekt)
    - Enumerable: Ano (pomocí speciálních metod)
    - Způsob exportu: Reference
    - Popis: Kolekce klíč-hodnota párů, kde klíče mohou být libovolného typu.
    ```javascript
    let mapa = new Map();
    mapa.set("klic", "hodnota");
    ```

14. **(Set)**
    - Primitivní: Ne (je to objekt)
    - Enumerable: Ano (pomocí speciálních metod)
    - Způsob exportu: Reference
    - Popis: Kolekce unikátních hodnot libovolného typu.
    ```javascript
    let set = new Set([1, 2, 3, 3, 4]); // Obsahuje 1, 2, 3, 4
    ```


Cvičení:
1. Vytvořte proměnné pro každý datový typ a vypište je do konzole.
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

2. Zkusite sečíst číslo a řetězec. Co se stane? Proč?
- _<details><summary>Možné řešení</summary>_

    ```javascript
    let number = 5;
    let string = "pet";
    let result = number + string;
    console.log(result); 
    // Output: 5pet
    // Output je string, protože JavaScript automaticky konvertuje číslo na string při sčítání s řetězcem.
    ```

   </details>

3. Vytvořte objekt reprezentující knihu s vlastnostmi jako název, autor a rok vydání.
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

4. Vytvořte proměnnou každého typu a vypište její typ pomocí operátoru `typeof`.
- _<details><summary>Možné řešení</summary>_

    ```javascript
    let str = "Hello";
    let num = 42;
    let bool = true;
    let undef;
    let nullVar = null;
    let sym = Symbol("id");
    let bigInt = BigInt(9007199254740991);
    let obj = {};
    let arr = [1, 2, 3];
    let func = function() {};

    console.log(typeof str);     // "string"
    console.log(typeof num);     // "number"
    console.log(typeof bool);    // "boolean"
    console.log(typeof undef);   // "undefined"
    console.log(typeof nullVar); // "object" (historická chyba v JS)
    console.log(typeof sym);     // "symbol"
    console.log(typeof bigInt);  // "bigint"
    console.log(typeof obj);     // "object"
    console.log(typeof arr);     // "object"
    console.log(typeof func);    // "function"
    ```

   </details>

5. Vytvořte objekt, který bude obsahovat vlastnosti různých datových typů, včetně vnořeného objektu a pole.
- _<details><summary>Možné řešení</summary>_

    ```javascript
    let komplexniObjekt = {
        jmeno: "Jan Novák",
        vek: 30,
        jeStudent: false,
        konickyPole: ["čtení", "běh", "programování"],
        adresa: {
            ulice: "Hlavní 123",
            mesto: "Praha",
            psc: "11000"
        },
        vypisInfo: function() {
            console.log(`${this.jmeno}, ${this.vek} let`);
        },
        id: Symbol("uniqueId"),
        velkeCislo: BigInt(1234567890123456789012345)
    };

    console.log(komplexniObjekt);
    komplexniObjekt.vypisInfo();
    ```

   </details>

6. Napište funkci, která přijme parametr a vrátí jeho datový typ jako řetězec.
- _<details><summary>Možné řešení</summary>_

    ```javascript
    function zjistitTyp(hodnota) {
        if (typeof hodnota === "object") {
            if (hodnota === null) return "null";
            if (Array.isArray(hodnota)) return "array";
        }
        return typeof hodnota;
    }

    console.log(zjistitTyp("Hello"));           // "string"
    console.log(zjistitTyp(42));                // "number"
    console.log(zjistitTyp(true));              // "boolean"
    console.log(zjistitTyp(undefined));         // "undefined"
    console.log(zjistitTyp(null));              // "null"
    console.log(zjistitTyp(Symbol("id")));      // "symbol"
    console.log(zjistitTyp(BigInt(123)));       // "bigint"
    console.log(zjistitTyp({}));                // "object"
    console.log(zjistitTyp([1, 2, 3]));         // "array"
    console.log(zjistitTyp(function() {}));     // "function"
    ```

   </details>

[**CheatSheet - Data Types**](cheatsheet.md#datové-typy-data-types)

[Zpět na obsah](#obsah-table-of-contents)

---

Poznámky:
- ¹ Iterabilita: Schopnost objektu definovat nebo přizpůsobit své chování při iteraci, například v cyklu for...of.
- ² Enumerable: Vlastnost, která určuje, zda je daná vlastnost objektu zahrnuta při enumeraci vlastností objektu, například v cyklu for...in nebo při použití Object.keys().
- ³ Způsob exportu: Určuje, jak je hodnota předávána při přiřazení nebo jako argument funkce. "Hodnota" znamená, že se vytvoří kopie, "Reference" znamená, že se předá odkaz na původní objekt v paměti.
