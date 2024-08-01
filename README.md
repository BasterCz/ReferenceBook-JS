# Reference book - JavaScript

## Obsah (Table of Contents)

1. [Začátečnická úroveň (Beginner Level)](#začátečnická-úroveň-beginner-level)
    - [Datové typy (Data Types)](#datové-typy-data-types)
    - [Proměnné (Variables)](#proměnné-variables)
    - [Operátory (Operators)](#operátory-operators) 
    - [Řídicí struktura (Control Flow)](#řídicí-struktura-control-flow)

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

#### Základní datové typy:

1. **String**
   - **Primitivní**: Ano
   - **Enumerable**: Ne (ale lze *iterovat* přes znaky)
   - **Způsob exportu**: Hodnota
   - **Návratová hodnota `typeof`**: "`string`"
   - **Popis**: Reprezentuje textové řetězce. Může být uzavřen v jednoduchých (`''`), dvojitých (`""`) nebo zpětných (``` `` ```) uvozovkách.
   - **Dobré vědět**: Řetězce jsou immutable (neměnné). Metody jako `toUpperCase()` vytvářejí nový řetězec.
    ```javascript
    let text1 = 'Hello';
    let text2 = "World";
    let text3 = `Hodnota je: ${celeCislo}`; // Template literal
    ```

2. **Number**
   - **Primitivní**: Ano
   - **Enumerable**: Ne
   - **Způsob exportu**: Hodnota
   - **Návratová hodnota `typeof`**: "`number`"
   - **Popis**: Reprezentuje jak celá čísla, tak i desetinná čísla. JavaScript používá 64bitový formát double-precision floating-point pro všechna čísla.
   - **Dobré vědět**: Obsahuje speciální hodnoty jako `Infinity`, `-Infinity` a `NaN` (Not a Number).
    ```javascript
    let celeCislo = 42;
    let desetinneCislo = 3.14;
    let vedeckaNotace = 2.998e8; // 2.998 * 10^8
    ```

3. **Boolean**
   - **Primitivní**: Ano
   - **Enumerable**: Ne
   - **Způsob exportu**: Hodnota
   - **Návratová hodnota `typeof`**:: "`boolean`"
   - **Popis**: Reprezentuje logickou hodnotu true nebo false.
   - **Dobré vědět**: Hodnoty jako 0, "", null, undefined, NaN se vyhodnocují jako false v booleovském kontextu.
   ```javascript
   let jeAktivni = true;
   let maLicenci = false;
   ```

4. **Undefined**
   - **Primitivní**: Ano
   - **Enumerable**: Ne
   - **Způsob exportu**: Hodnota
   - **Návratová hodnota `typeof`**:: "`undefined`"
   - **Popis**: Reprezentuje proměnnou, která byla deklarována, ale nebyla jí přiřazena hodnota.
   - **Dobré vědět**: Funkce bez explicitního return vrací undefined.
    ```javascript
    let nedifinovanaPtomenna;
    console.log(nedifinovanaPtomenna); // undefined
    ```

5. **Null**
   - **Primitivní**: Ano (technicky je to objekt, ale chová se jako primitivní typ)
   - **Enumerable**: Ne
   - **Způsob exportu**: Hodnota
   - **Návratová hodnota `typeof`**:: "`object`" (historická chyba v JS)
   - **Popis**: Reprezentuje záměrnou absenci jakékoli hodnoty nebo objektu.
   - **Dobré vědět**: null == undefined je true, ale null === undefined je false.
    ```javascript
    let prazdnaHodnota = null;
    ```

#### Pokročilejší datové typy:

6. **Object**
   - **Primitivní**: Ne
   - **Enumerable**: Ano (pro vlastní vlastnosti)
   - **Způsob exportu**: Reference
   - **Návratová hodnota `typeof`**:: "`object`"
   - **Popis**: Kolekce klíč-hodnota párů. Základní stavební blok pro komplexní datové struktury.
   - **Dobré vědět**: Objekty jsou mutable (měnitelné). Lze dynamicky přidávat a odebírat vlastnosti.
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

7. **Array**
   - **Primitivní**: Ne (je to speciální typ objektu)
   - **Enumerable**: Ano
   - **Způsob exportu**: Reference
   - **Návratová hodnota `typeof`**:: "`object`"
   - **Popis**: Uspořádaná kolekce hodnot. Indexováno od nuly.
   - **Dobré vědět**: Délka pole je dynamická. `Array.isArray()` lze použít pro kontrolu, zda je hodnota pole.
    ```javascript
    let ovoce = ["jablko", "banán", "pomeranč"];
    ```

8. **Function**
    - **Primitivní**: Ne (je to speciální typ objektu)
    - **Enumerable**: Ne
    - **Způsob exportu**: Reference
    - **Návratová hodnota `typeof`**:: "`function`"
    - **Popis**: Blok kódu navržený k provádění konkrétního úkolu. Může přijímat vstupy (parametry) a vracet výstup.
    - **Dobré vědět**: Funkce jsou objekty prvního řádu v JavaScriptu. Mohou být přiřazeny proměnným, předány jako argumenty a vráceny z jiných funkcí.
    ```javascript
    function pozdrav(jmeno) {
        return `Ahoj, ${jmeno}!`;
    }
    ```

#### Pokročilé datové typy:

9. **Symbol**
   - **Primitivní**: Ano
   - **Enumerable**: Ne
   - **Způsob exportu**: Hodnota
   - **Návratová hodnota `typeof`**:: "`symbol`"
   - **Popis**: Reprezentuje unikátní identifikátor. Často se používá jako klíč pro vlastnosti objektů.
   - **Dobré vědět**: Každý Symbol je unikátní, i když má stejný popis.
    ```javascript
    let id = Symbol('id');
    let objekt = {
    [id]: 12345
    };
    ```

10. **BigInt**
    - **Primitivní**: Ano
    - **Enumerable**: Ne
    - **Způsob exportu**: Hodnota
    - **Návratová hodnota `typeof`**:: "`bigint`"
    - **Popis**: Reprezentuje celá čísla libovolné přesnosti. Používá se pro velmi velká čísla.
    - **Dobré vědět**: BigInt nelze míchat s běžnými čísly v aritmetických operacích.
    ```javascript
    let velkeCislo = 1234567890123456789012345678901234567890n;
    ```

11. **(Date)**
    - **Primitivní**: Ne (je to objekt)
    - **Enumerable**: Ne
    - **Způsob exportu**: Reference
    - **Návratová hodnota `typeof`**:: "`object`"
    - **Popis**: Reprezentuje datum a čas.
    - **Dobré vědět**: Měsíce jsou indexovány od 0 (0 = leden, 11 = prosinec).
    ```javascript
    let ted = new Date();
    ```

12. **(RegExp)**
    - **Primitivní**: Ne (je to objekt)
    - **Enumerable**: Ne
    - **Způsob exportu**: Reference
    - **Návratová hodnota `typeof`**:: "`object`"
    - **Popis**: Reprezentuje regulární výraz pro pokročilé vyhledávání a manipulaci s textem.
    - **Dobré vědět**: Lze vytvořit pomocí literálu `/pattern/` nebo konstruktoru `new RegExp()`.
    ```javascript
    let emailRegex = /^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/;
    ```

13. **(Map)**
    - **Primitivní**: Ne (je to objekt)
    - **Enumerable**: Ano (pomocí speciálních metod)
    - **Způsob exportu**: Reference
    - **Návratová hodnota `typeof`**:: "`object`"
    - **Popis**: Kolekce klíč-hodnota párů, kde klíče mohou být libovolného typu.
    - **Dobré vědět**: Na rozdíl od objektů, Map zachovává pořadí vložení.
    ```javascript
    let mapa = new Map();
    mapa.set("klic", "hodnota");
    ```

14. **(Set)**
    - **Primitivní**: Ne (je to objekt)
    - **Enumerable**: Ano (pomocí speciálních metod)
    - **Způsob exportu**: Reference
    - **Návratová hodnota `typeof`**:: "`object`"
    - **Popis**: Kolekce unikátních hodnot libovolného typu.
    - **Dobré vědět**: Užitečné pro odstranění duplicit z pole.
    ```javascript
    let set = new Set([1, 2, 3, 3, 4]); // Obsahuje 1, 2, 3, 4
    ```

#### Důležité koncepty:

- **Iterabilita¹:** String, Array, Map, Set, TypedArray, arguments object jsou iterabilní. Number, Boolean, Null, Undefined, Symbol, BigInt, Object (standardní) nejsou.
- **Enumerable²:** Určuje, zda je vlastnost zahrnuta při enumeraci vlastností objektu.
- **Způsob exportu³:** Hodnota (vytvoří se kopie) nebo Reference (předá se odkaz na původní objekt v paměti).

#### Cvičení:

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
- ¹ **Iterabilita**: Schopnost objektu definovat nebo přizpůsobit své chování při iteraci. Iterabilní objekty implementují metodu Symbol.iterator, která vrací iterátor. Toto umožňuje použití v cyklech for...of a s operátorem spread (...). Iterabilní objekty mohou být procházeny prvek po prvku, což je užitečné pro práci s kolekcemi dat. Příklady iterabilních objektů zahrnují Array, String, Map, Set, a TypedArray.

- ² **Enumerable**: Vlastnost objektu, která určuje, zda daná vlastnost bude zahrnuta při enumeraci vlastností objektu. Enumerabilní vlastnosti jsou viditelné a dostupné při použití cyklu for...in, metody Object.keys(), nebo při serializaci objektu (např. JSON.stringify()). Ve výchozím nastavení jsou vlastnosti vytvořené přímo na objektu enumerabilní, zatímco vlastnosti zděděné z prototypu obvykle nejsou. Enumerabilitu vlastnosti lze kontrolovat a měnit pomocí metody Object.getOwnPropertyDescriptor() a Object.defineProperty().

- ³ **Způsob exportu**: Určuje, jak je hodnota předávána při přiřazení nebo jako argument funkce. 
  - "**Hodnota**" znamená, že se vytvoří kopie původní hodnoty. To platí pro všechny primitivní typy (String, Number, Boolean, Undefined, Null, Symbol, BigInt). Když předáváte primitivní hodnotu, vytvoří se její kopie a změny provedené na kopii neovlivní původní hodnotu.
  - "**Reference**" znamená, že se předá odkaz na původní objekt v paměti. To platí pro všechny objektové typy (Object, Array, Function, Date, RegExp, Map, Set). Když předáváte referenci, obě proměnné ukazují na stejný objekt v paměti, takže změny provedené přes jednu referenci se projeví ve všech referencích na tento objekt.


---

### JavaScript Proměnné (Variables)

#### **Úvod do proměnných**

Proměnné jsou základním stavebním kamenem v JavaScriptu. Používají se k ukládání a manipulaci s daty v programu.

Základní syntax pro deklaraci proměnné:

```javascript
let nazevPromenne = hodnota;
```

#### **Typy deklarací**

JavaScript má tři způsoby deklarace proměnných:

1. `var`: Proměnná s funkčním nebo globálním rozsahem (starší syntax)
2. `let`: Proměnná s blokovým rozsahem (zavedeno v ES6)
3. `const`: Konstanta s blokovým rozsahem (zavedeno v ES6)

Příklady:

```javascript
// var (vyhnout se používání v moderním JavaScriptu)
var staryZpusob = "Jsem staromódní";

// let
let vek = 30;
vek = 31; // OK

// const
const PI = 3.14159;
PI = 3; // Chyba
```

#### Klíčové rozdíly:
- `var` má **funkční** nebo **globální** rozsah, zatímco `let` a `const` mají **blokový** rozsah.
- Proměnné deklarované pomocí `var` jsou **vyzdviženy (hoisted)**, zatímco `let` a `const` nejsou.
- Proměnné `const` nemohou být přeřazeny, ale jejich vlastnosti mohou být modifikovány, pokud jsou objekty.

#### **Konvence pojmenování**

V JavaScriptu se používají následující konvence pro pojmenování:

- `maleVelke` pro proměnné a funkce (camelCase)
- `VelkeVelke` pro třídy (PascalCase)
- `SPOJENY_HAD` pro konstanty (UPPER_SNAKE_CASE)

Příklady:

```javascript
let uzivatelskeJmeno = "Jan";
const MAX_VELIKOST = 100;
class ProfilUzivatele {}
```

**Rozsah (Scope)**

Rozsah určuje, kde v kódu je proměnná přístupná.

- **Globální rozsah**: Proměnné deklarované mimo jakoukoli funkci.
- **Funkční rozsah**: Proměnné deklarované uvnitř funkce (platí pro `var`).
- **Blokový rozsah**: Proměnné deklarované uvnitř bloku, např. uvnitř if statement nebo for loop (platí pro `let` a `const`).

```javascript
let globalniPromenna = "Jsem globální";

function testRozsahu() {
    let funkcniPromenna = "Jsem uvnitř funkce";

    if (true) {
        let blokovaPromenna = "Jsem uvnitř bloku";
        var varPromenna = "Jsem také uvnitř bloku, ale s funkčním rozsahem";
        console.log(blokovaPromenna); // OK
    }

    console.log(funkcniPromenna); // OK
    console.log(varPromenna); // OK
    console.log(blokovaPromenna); // ReferenceError
}

console.log(globalniPromenna); // OK
console.log(funkcniPromenna); // ReferenceError
```

#### Hoisting

Hoisting je JavaScript mechanismus, kde proměnné a funkční deklarace jsou přesunuty na začátek jejich rozsahu před provedením kódu.

```javascript
console.log(vyzdvizenaVar); // undefined
var vyzdvizenaVar = 5;

vyzdvizenaFunkce(); // "Ahoj, jsem vyzdvižená funkce!"
function vyzdvizenaFunkce() {
    console.log("Ahoj, jsem vyzdvižená funkce!");
}

console.log(nevyzdvizenaLet); // ReferenceError
let nevyzdvizenaLet = 10;
```

#### Temporal Dead Zone (TDZ)

TDZ je chování specifické pro `let` a `const`, kde proměnné existují v bloku, ale nemohou být použity před jejich deklarací.

```javascript
{
    console.log(tdz); // ReferenceError
    let tdz = 5;
}
```

#### Globální objekty

V prohlížeči je globálním objektem `window`, v Node.js je to `global`.

```javascript
// V prohlížeči
window.globalniPromenna = "Jsem globální";
console.log(globalniPromenna); // "Jsem globální"

// V Node.js
global.globalniPromenna = "Jsem globální";
console.log(globalniPromenna); // "Jsem globální"
```

#### Best Practices

1. Pokud lze, používejte `const`
2. Pokud má být proměnná přeřazována, použijte `let`
3. Vyhněte se použití `var`
4. Deklarujte proměnné na začátku jejich rozsahu (scope)
5. Používejte dostatečně jasné a popisné názvy proměnných

#### Cvičení

Cvičení jsou seřazena od nejjednodušších po nejsložitější:

1. Deklarujte `const` proměnnou pro Vaše jméno a `let` proměnnou pro Váš věk.
   
- _<details><summary>Možné řešení</summary>_

   ```javascript
   const jmeno = "Jan Novák";
   let vek = 31;
   ```
   </details>

2. Zkuste přeřadit `const` proměnnou. Co se stane?
   
- _<details><summary>Možné řešení</summary>_

   ```javascript
   const jmeno = "Karel Dravý";
   jmeno = "Ondřej Prchal" // TypeError: Assignment to a constant variable.
   ```
   </details>

3. Vytvořte objekt pomocí `const` a modifikujte jednu z jeho vlastností. Je to možné?
   
- _<details><summary>Možné řešení</summary>_

   ```javascript
   const osoba = {
       jmeno: "Jan Novák",
       vek: 30
   };

   osoba.vek = 31; // OK
   console.log(osoba.vek); // 31

   osoba = { jmeno: "Petr Svoboda", vek: 25 }; // TypeError: Assignment to a constant variable.
   ```
   </details>

4. Napište funkci, která demonstruje rozdíl mezi `var` a `let` v cyklu.
   
   _<details><summary>Možné řešení</summary>_

   ```javascript
   function demonstraceVarLet() {
       console.log("Použití var:");
       for (var i = 0; i < 3; i++) {
           setTimeout(() => console.log(i), 100);
       }

       console.log("Použití let:");
       for (let j = 0; j < 3; j++) {
           setTimeout(() => console.log(j), 100);
       }
   }

   demonstraceVarLet();
   // Výstup s var: 3, 3, 3
   // Výstup s let: 0, 1, 2
   ```
   </details>

5. Vytvořte funkci, která demonstruje TDZ (Temporal Dead Zone) pro `let` a `const`.
   
   _<details><summary>Možné řešení</summary>_

   ```javascript
   function demonstraceTDZ() {
       try {
           console.log(letPromenna); // ReferenceError
       } catch (e) {
           console.log("Chyba přístupu k let proměnné před deklarací:", e.message);
       }
       
       let letPromenna = "Jsem let proměnná";
       
       try {
           console.log(constPromenna); // ReferenceError
       } catch (e) {
           console.log("Chyba přístupu ke const proměnné před deklarací:", e.message);
       }
       
       const constPromenna = "Jsem const proměnná";
       
       console.log(letPromenna); // "Jsem let proměnná"
       console.log(constPromenna); // "Jsem const proměnná"
   }

   demonstraceTDZ();
   ```
   </details>

6. Napište funkci, která demonstruje rozdíl mezi lokálním a globálním rozsahem proměnných.
   
   _<details><summary>Možné řešení</summary>_

   ```javascript
   let globalniPromenna = "Jsem globální";

   function demonstraceRozsahu() {
       let lokalniPromenna = "Jsem lokální";
       
       console.log("Uvnitř funkce:");
       console.log("Globální proměnná:", globalniPromenna);
       console.log("Lokální proměnná:", lokalniPromenna);
       
       if (true) {
           let blokovaPromenna = "Jsem bloková";
           var funkcniPromenna = "Jsem funkční";
           console.log("Uvnitř bloku:");
           console.log("Bloková proměnná:", blokovaPromenna);
           console.log("Funkční proměnná:", funkcniPromenna);
       }
       
       console.log("Po bloku:");
       console.log("Funkční proměnná:", funkcniPromenna);
       try {
           console.log("Bloková proměnná:", blokovaPromenna);
       } catch (e) {
           console.log("Chyba přístupu k blokové proměnné:", e.message);
       }
   }

   demonstraceRozsahu();
   console.log("Mimo funkci:");
   console.log("Globální proměnná:", globalniPromenna);
   try {
       console.log("Lokální proměnná:", lokalniPromenna);
   } catch (e) {
       console.log("Chyba přístupu k lokální proměnné:", e.message);
   }
   ```
   </details>

[**CheatSheet - Variables**](cheatsheet.md#proměnné-variables)

[Zpět na obsah](#obsah-table-of-contents)

### Operátory (Operators)

JavaScript podporuje různé typy operátorů, které můžeme rozdělit do několika kategorií podle složitosti a funkce.

#### Základní operátory

1. **Aritmetické operátory (Arithmetic Operators):**
   - Sčítání (`+`)
     - **Popis**: Sčítá dva operandy.
     - **Použití**: `operand1 + operand2`
     - **Příklad**: 
        ```javascript
        let sum = 5 + 3; // 8
        ```
     - **Zajímavost**: Když se použije s řetězci, provádí konkatenaci.

   - Odčítání (`-`)
     - **Popis**: Odečítá druhý operand od prvního.
     - **Použití**: `operand1 - operand2`
     - **Příklad**: 
        ```javascript
        let difference = 10 - 3; // 7
        ```
     - **Zajímavost**: Lze použít jako unární operátor pro negaci čísla.

   - Násobení (`*`)
     - **Popis**: Násobí dva operandy.
     - **Použití**: `operand1 * operand2`
     - **Příklad**: 
        ```javascript
        let product = 4 * 2; // 8
        ```
     - **Zajímavost**: Při násobení řetězce číslem dochází k implicitní konverzi.

   - Dělení (`/`)
     - **Popis**: Dělí první operand druhým.
     - **Použití**: `operand1 / operand2`
     - **Příklad**: 
        ```javascript
        let quotient = 20 / 5; // 4
        ```
     - **Zajímavost**: Dělení nulou vrací `Infinity` nebo `-Infinity`.

   - Modulo (zbytek po dělení) (`%`)
     - **Popis**: Vrací zbytek po dělení prvního operandu druhým.
     - **Použití**: `operand1 % operand2`
     - **Příklad**: 
        ```javascript
        let remainder = 17 % 5; // 2
        ```
     - **Zajímavost**: Užitečné pro zjištění, zda je číslo sudé nebo liché.

2. **Přiřazovací operátory (Assignment Operators):**
   - Přiřazení (`=`)
     - **Popis**: Přiřazuje hodnotu proměnné.
     - **Použití**: `variable = value`
     - **Příklad**: 
        ```javascript
        let x = 10;
        ```
     - **Zajímavost**: Vrací přiřazenou hodnotu, což umožňuje řetězení přiřazení.

   - Přičtení a přiřazení (`+=`)
     - **Popis**: Přičte hodnotu k proměnné a výsledek přiřadí proměnné.
     - **Použití**: `variable += value`
     - **Příklad**: 
        ```javascript
        let x = 5; 
        x += 3; // x je nyní 8
        ```
     - **Zajímavost**: Funguje i s řetězci pro konkatenaci.

   - Odečtení a přiřazení (`-=`)
     - **Popis**: Odečte hodnotu od proměnné a výsledek přiřadí proměnné.
     - **Použití**: `variable -= value`
     - **Příklad**: 
        ```javascript
        let x = 10; 
        x -= 4; // x je nyní 6
        ```
     - **Zajímavost**: Při použití s řetězci dochází k implicitní konverzi na číslo.

   - Násobení a přiřazení (`*=`)
     - **Popis**: Vynásobí proměnnou hodnotou a výsledek přiřadí proměnné.
     - **Použití**: `variable *= value`
     - **Příklad**: 
        ```javascript
        let x = 3; 
        x *= 4; // x je nyní 12
        ```
     - **Zajímavost**: Může vést k neočekávaným výsledkům při míchání typů.

   - Dělení a přiřazení (`/=`)
     - **Popis**: Vydělí proměnnou hodnotou a výsledek přiřadí proměnné.
     - **Použití**: `variable /= value`
     - **Příklad**: 
        ```javascript
        let x = 15; 
        x /= 3; // x je nyní 5
        ```
     - **Zajímavost**: Při dělení nulou nastaví proměnnou na `Infinity` nebo `-Infinity`.

3. **Porovnávací operátory (Comparison Operators):**
   - Rovno (`==`)
     - **Popis**: Porovnává dva operandy na rovnost s implicitní konverzí typů.
     - **Použití**: `operand1 == operand2`
     - **Příklad**: 
        ```javascript
        console.log(5 == "5"); // true
        ```
     - **Zajímavost**: Může vést k neočekávaným výsledkům kvůli implicitní konverzi.

   - Striktně rovno (`===`)
     - **Popis**: Porovnává dva operandy na rovnost bez konverze typů.
     - **Použití**: `operand1 === operand2`
     - **Příklad**: 
        ```javascript
        console.log(5 === "5"); // false
        ```
     - **Zajímavost**: Doporučuje se pro většinu porovnání kvůli přesnějším výsledkům.

   - Nerovno (`!=`)
     - **Popis**: Kontroluje, zda dva operandy nejsou rovny, s implicitní konverzí typů.
     - **Použití**: `operand1 != operand2`
     - **Příklad**: 
        ```javascript
        console.log(5 != "5"); // false
        console.log(5 != "6"); // true
        ```
     - **Zajímavost**: Podobně jako `==`, může vést k neočekávaným výsledkům.

   - Striktně nerovno (`!==`)
     - **Popis**: Kontroluje, zda dva operandy nejsou rovny, bez konverze typů.
     - **Použití**: `operand1 !== operand2`
     - **Příklad**: 
        ```javascript
        console.log(5 !== "5"); // true
        ```
     - **Zajímavost**: Preferovaná volba pro kontrolu nerovnosti.

   - Větší než (`>`)
     - **Popis**: Kontroluje, zda je první operand větší než druhý.
     - **Použití**: `operand1 > operand2`
     - **Příklad**: 
        ```javascript
        console.log(10 > 5); // true
        ```
     - **Zajímavost**: Při porovnávání řetězců se používá lexikografické pořadí.

   - Menší než (`<`)
     - **Popis**: Kontroluje, zda je první operand menší než druhý.
     - **Použití**: `operand1 < operand2`
     - **Příklad**: 
        ```javascript
        console.log(3 < 7); // true
        ```
     - **Zajímavost**: Může být použito k porovnání dat.

   - Větší nebo rovno (`>=`)
     - **Popis**: Kontroluje, zda je první operand větší nebo roven druhému.
     - **Použití**: `operand1 >= operand2`
     - **Příklad**: 
        ```javascript
        console.log(5 >= 5); // true
        ```
     - **Zajímavost**: Užitečné pro kontrolu rozsahů hodnot.

   - Menší nebo rovno (`<=`)
     - **Popis**: Kontroluje, zda je první operand menší nebo roven druhému.
     - **Použití**: `operand1 <= operand2`
     - **Příklad**: 
        ```javascript
        console.log(4 <= 4); // true
        ```
     - **Zajímavost**: Často se používá v cyklech a podmínkách.

4. **Logické operátory (Logical Operators):**
   - AND (`&&`)
     - **Popis**: Vrací `true`, pokud oba operandy jsou pravdivé.
     - **Použití**: `operand1 && operand2`
     - **Příklad**: 
        ```javascript
        console.log(true && true); // true
        ```
     - **Zajímavost**: Vyhodnocuje druhý operand pouze pokud první je pravdivý (short-circuit evaluation).

   - OR (`||`)
     - **Popis**: Vrací `true`, pokud alespoň jeden z operandů je pravdivý.
     - **Použití**: `operand1 || operand2`
     - **Příklad**: 
        ```javascript
        console.log(false || true); // true
        ```
     - **Zajímavost**: Často se používá pro nastavení výchozích hodnot.

   - NOT (`!`)
     - **Popis**: Neguje (obrací) logickou hodnotu operandu.
     - **Použití**: `!operand`
     - **Příklad**: 
        ```javascript
        console.log(!true); // false
        ```
     - **Zajímavost**: Dvojitá negace (`!!`) se často používá pro konverzi na boolean.

#### Pokročilé operátory

5. **Unární operátory (Unary Operators):**
   - Inkrementace (`++`)
     - **Popis**: Zvýší hodnotu operandu o 1.
     - **Použití**: `++variable` nebo `variable++`
     - **Příklad**: 
        ```javascript
        let x = 5; 
        x++; 
        console.log(x); // 6
        ```
     - **Zajímavost**: Prefiková forma (`++x`) vrací novou hodnotu, postfixová (`x++`) vrací původní hodnotu.

   - Dekrementace (`--`)
     - **Popis**: Sníží hodnotu operandu o 1.
     - **Použití**: `--variable` nebo `variable--`
     - **Příklad**: 
        ```javascript
        let y = 8; 
        y--; 
        console.log(y); // 7
        ```
     - **Zajímavost**: Stejně jako inkrementace má prefikovou a postfixovou formu.

   - Unární plus (`+`)
     - **Popis**: Převádí operand na číslo.
     - **Použití**: `+operand`
     - **Příklad**: 
        ```javascript
        console.log(+"3"); // 3
        ```
     - **Zajímavost**: Může být použito pro rychlou konverzi řetězce na číslo.

   - Unární mínus (`-`)
     - **Popis**: Neguje operand.
     - **Použití**: `-operand`
     - **Příklad**: 
        ```javascript
        console.log(-5); // -5
        ```
     - **Zajímavost**: Aplikace na nečíselnou hodnotu nejprve provede konverzi na číslo.

**Bitové operátory (Bitwise Operators):**

- AND (`&`)
  - **Popis**: Provádí bitovou operaci AND na každém bitu operandů.
  - **Použití**: `operand1 & operand2`
  - **Příklad**: 
    ```javascript
    let x = 5;      // 00000000000000000000000000000101
    let y = 3;      // 00000000000000000000000000000011
    let z = x & y;  // 00000000000000000000000000000001
    console.log(z); // 1
    ```
  - **Zajímavost**: Často se používá pro bitové masky.

- OR (`|`)
  - **Popis**: Provádí bitovou operaci OR na každém bitu operandů.
  - **Použití**: `operand1 | operand2`
  - **Příklad**: 
    ```javascript
    let x = 5;      // 00000000000000000000000000000101
    let y = 3;      // 00000000000000000000000000000011
    let z = x | y;  // 00000000000000000000000000000111
    console.log(z); // 7
    ```
  - **Zajímavost**: Užitečné pro kombinování bitových příznaků.

- XOR (`^`)
  - **Popis**: Provádí bitovou operaci XOR na každém bitu operandů.
  - **Použití**: `operand1 ^ operand2`
  - **Příklad**: 
    ```javascript
    let x = 5;      // 00000000000000000000000000000101
    let y = 3;      // 00000000000000000000000000000011
    let z = x ^ y;  // 00000000000000000000000000000110
    console.log(z); // 6
    ```
  - **Zajímavost**: Může být použito pro jednoduché šifrování.

- NOT (`~`)
  - **Popis**: Invertuje bity operandu.
  - **Použití**: `~operand`
  - **Příklad**: 
    ```javascript
    let x = 5;      // 00000000000000000000000000000101
    let y = ~x;     // 11111111111111111111111111111010
    let z = y;      // 11111111111111111111111111111010
    console.log(z); // -6
    ```
  - **Zajímavost**: Výsledek je vždy -(x+1) pro vstup x.

- Bitový posun vlevo (`<<`)
  - **Popis**: Posouvá bity prvního operandu vlevo o počet pozic specifikovaný druhým operandem.
  - **Použití**: `operand1 << operand2`
  - **Příklad**: 
    ```javascript
    let x = 5;      // 00000000000000000000000000000101
    let y = 1;
    let z = x << y; // 00000000000000000000000000001010
    console.log(z); // 10
    ```
  - **Zajímavost**: Ekvivalentní násobení mocninou 2.

- Bitový posun vpravo (`>>`)
  - **Popis**: Posouvá bity prvního operandu vpravo o počet pozic specifikovaný druhým operandem.
  - **Použití**: `operand1 >> operand2`
  - **Příklad**: 
    ```javascript
    let x = 5;      // 00000000000000000000000000000101
    let y = 1;
    let z = x >> y; // 00000000000000000000000000000010
    console.log(z); // 2
    ```
  - **Zajímavost**: Zachovává znaménko (sign-propagating).

- Bitový posun vpravo s doplněním nulami (`>>>`)
  - **Popis**: Posouvá bity prvního operandu vpravo o počet pozic specifikovaný druhým operandem, doplňuje nuly zleva.
  - **Použití**: `operand1 >>> operand2`
  - **Příklad**: 
    ```javascript
    let x = -5;     // 11111111111111111111111111111011
    let y = 1;
    let z = x >>> y;// 01111111111111111111111111111101
    console.log(z); // 2147483645
    ```
  - **Zajímavost**: Vždy vrací nezáporný výsledek.

7. **Ternární (podmínkový) operátor (Ternary Operator):**
   - **Popis**: Podmíněně vrací jednu ze dvou hodnot na základě podmínky.
   - **Použití**: `podmínka ? výraz1 : výraz2`
   - **Příklad**: 
        ```javascript
        let status = (age >= 18) ? "dospělý" : "nezletilý";
        ```
   - **Zajímavost**: Jediný operátor v JavaScriptu, který přijímá tři operandy.

8. **Operátor řetězení volání (Optional Chaining Operator):**
   - **Popis**: Umožňuje číst hodnotu z vnořené vlastnosti objektu bez nutnosti explicitně ověřovat každou referenci v řetězci.
   - **Použití**: `obj?.prop`, `obj?.[expr]`, `arr?.[index]`, `func?.(args)`
   - **Příklad**: 
        ```javascript
        let neexistujiciMetoda = obj?.neexistujiciMetoda?.();
        ```
   - **Zajímavost**: Vrací `undefined`, pokud je jakákoli část řetězce `null` nebo `undefined`.

9. **Operátor nulového sloučení (Nullish Coalescing Operator):**
   - **Popis**: Vrací pravý operand, pokud levý operand je `null` nebo `undefined`, jinak vrací levý operand.
   - **Použití**: `levyOperand ?? pravyOperand`
   - **Příklad**: 
        ```javascript
        let jmeno = uzivatel.jmeno ?? "Anonymní";
        ```
   - **Zajímavost**: Na rozdíl od `||`, nebere v úvahu falsy hodnoty jako `0` nebo `""`.

10. **Operátor typu (typeof Operator):**
    - **Popis**: Vrací řetězec indikující typ operandu.
    - **Použití**: `typeof operand`
    - **Příklad**: 
        ```javascript
        console.log(typeof 42); // "number"
        ```
    - **Zajímavost**: Vrací "object" pro `null`, což je známá chyba v jazyce.

#### Speciální operátory

11. **Operátor rozkladu (Spread Operator):**
    - **Popis**: Rozkládá iterovatelný objekt na jednotlivé elementy.
    - **Použití**: `...iterovatelnyObjekt`
    - **Příklad**: 
        ```javascript
        let arr = [1, 2, 3]; console.log(...arr); // 1 2 3
        ```
    - **Zajímavost**: Může být použit pro kopírování polí nebo objektů.

12. **Operátor zbytku (Rest Operator):**
    - **Popis**: Shromažďuje zbývající elementy do pole.
    - **Použití**: `function(a, ...zbytek) {}`
    - **Příklad**: 
        ```javascript
        function sum(...theArgs) {
            let total = 0;
            for (const arg of theArgs) {
                total += arg;
            }
            return total;
        }

        console.log(sum(1, 2, 3)); // 6

        console.log(sum(1, 2, 3, 4)); // 10

        ```
    - **Zajímavost**: Umožňuje funkci přijmout libovolný počet argumentů.

13. **Operátor `in`:**
    - **Popis**: Kontroluje, zda specifikovaná vlastnost existuje v objektu.
    - **Použití**: `propname in object`
    - **Příklad**: 
        ```javascript
        console.log('name' in {name: 'John'}); // true
        ```
    - **Zajímavost**: Funguje také pro vlastnosti zděděné z prototypu.

14. **Operátor `instanceof`:**
    - **Popis**: Testuje, zda objekt je instancí specifikovaného typu objektu.
    - **Použití**: `object instanceof constructor`
    - **Příklad**: 
        ```javascript
        console.log([] instanceof Array); // true
        ```
    - **Zajímavost**: Kontroluje celý prototypový řetězec objektu.

15. **Operátor `delete`:**
    - **Popis**: Odstraňuje vlastnost z objektu.
    - **Použití**: `delete object.property` nebo `delete object['property']`
    - **Příklad**: 
        ```javascript
        let obj = {x: 1, y: 2}; delete obj.x; console.log(obj); // {y: 2}
        ```
    - **Zajímavost**: Neovlivňuje vlastnosti zděděné z prototypu.

#### Klíčová slova související s operátory

- `new`:
  - **Popis**: Vytváří novou instanci objektu.
  - **Použití**: `new Constructor()`
  - **Příklad**: 
    ```javascript
    let date = new Date();
    ```
  - **Zajímavost**: Může být použito bez závorek pro konstruktory bez parametrů.

- `void`:
  - **Popis**: Vyhodnocuje výraz a vrací `undefined`.
  - **Použití**: `void expression`
  - **Příklad**: 
    ```javascript
    void(0)
    ```
     nebo 
    ```javascript
    void 0
    ```
  - **Zajímavost**: Často se používá v odkazech pro zabránění navigace: `<a href="javascript:void(0);">Klikni</a>`

- `yield`:
  - **Popis**: Pozastavuje a obnovuje generátorovou funkci.
  - **Použití**: `yield [expression]`
  - **Příklad**: 
    ```javascript
    function* generator() {
      yield 1;
      yield 2;
    }
    ```
  - **Zajímavost**: Může být použito pro vytvoření nekonečných sekvencí.

- `await`:
  - **Popis**: Pozastavuje asynchronní funkci do dokončení Promise.
  - **Použití**: `let result = await promise;`
  - **Příklad**: 
    ```javascript
    async function fetchData() {
      let response = await fetch('https://api.example.com/data');
      let data = await response.json();
      return data;
    }
    ```
  - **Zajímavost**: Může být použito pouze uvnitř async funkcí.

#### Příklady:

```javascript
// Základní aritmetické operace
let sum = 5 + 3;  // 8
let product = 4 * 2;  // 8

// Porovnávání
console.log(5 == "5");  // true (volná rovnost)
console.log(5 === "5");  // false (striktní rovnost)

// Logické operátory
let isAdult = age >= 18 && hasLicense;

// Přiřazení
let x = 10;
x += 5;  // x je nyní 15

// Ternární operátor
let status = (age >= 18) ? "dospělý" : "nezletilý";

// Bitové operace
let flags = 0b1010;
let mask = 0b1100;
let result = flags & mask;  // 0b1000

// Operátor řetězení volání
let neexistujiciMetoda = obj?.neexistujiciMetoda?.();

// Operátor nulového sloučení
let jmeno = uzivatel.jmeno ?? "Anonymní";

// Spread operátor
let arr1 = [1, 2, 3];
let arr2 = [...arr1, 4, 5];  // [1, 2, 3, 4, 5]

// Rest operátor
function sum(...numbers) {
  return numbers.reduce((a, b) => a + b, 0);
}
console.log(sum(1, 2, 3, 4));  // 10
```

#### Cvičení:

1. **Základní:** Napište funkci, která vezme dvě čísla a vrátí jejich součet, rozdíl, součin a podíl.

- _<details><summary>Možné řešení</summary>_

    ```javascript
    function basicMath(a, b) {
    return {
        součet: a + b,
        rozdíl: a - b,
        součin: a * b,
        podíl: a / b
    };
    }

    console.log(basicMath(10, 5));
    // Output: { součet: 15, rozdíl: 5, součin: 50, podíl: 2 }
    ```

</details>

2. **Základní:** Vytvořte program, který zkontroluje, zda je číslo sudé nebo liché pomocí operátoru modulo.

- _<details><summary>Možné řešení</summary>_

    ```javascript
    function isEven(number) {
    return number % 2 === 0 ? "sudé" : "liché";
    }

    console.log(isEven(4)); // "sudé"
    console.log(isEven(7)); // "liché"
    ```

</details>

3. **Střední:** Použijte logický operátor AND ke kontrole, zda je osoba způsobilá volit (18 let nebo starší) a má platný průkaz totožnosti.

- _<details><summary>Možné řešení</summary>_

    ```javascript
    function canVote(age, hasValidID) {
    return age >= 18 && hasValidID;
    }

    console.log(canVote(20, true));  // true
    console.log(canVote(17, true));  // false
    console.log(canVote(18, false)); // false
    ```

</details>

4. **Střední:** Napište funkci, která použije bitové operátory k nastavení, vymazání a kontrole specifického bitu v čísle.

- _<details><summary>Možné řešení</summary>_

    ```javascript
    function bitOperations(n, bitPosition) {
    // Nastavení bitu
    function setBit(n) {
        return n | (1 << bitPosition);
    }

    // Vymazání bitu
    function clearBit(n) {
        return n & ~(1 << bitPosition);
    }

    // Kontrola bitu
    function checkBit(n) {
        return !!(n & (1 << bitPosition));
    }

    return {
        original: n,
        setBit: setBit(n),
        clearBit: clearBit(n),
        isBitSet: checkBit(n)
    };
    }

    console.log(bitOperations(5, 1));
    // Output: { original: 5, setBit: 7, clearBit: 5, isBitSet: true }
    ```

</details>

5. **Pokročilé:** Vytvořte funkci, která použije ternární operátor a operátor nulového sloučení k formátování uživatelského vstupu. Funkce by měla přijmout objekt s vlastnostmi `jmeno` a `vek`, a vrátit řetězec ve formátu "Jméno: [jméno], Věk: [věk]". Pokud některá vlastnost chybí, použijte výchozí hodnoty.

- _<details><summary>Možné řešení</summary>_

    ```javascript
    function formatUserInput(user) {
    const defaultName = "Neznámý";
    const defaultAge = "Neuvedeno";

    const name = user?.jmeno ?? defaultName;
    const age = user?.vek ?? defaultAge;

    return `Jméno: ${name}, Věk: ${age === "Neuvedeno" ? age : age + " let"}`;
    }

    console.log(formatUserInput({jmeno: "Jan", vek: 30})); 
    // "Jméno: Jan, Věk: 30 let"
    console.log(formatUserInput({jmeno: "Anna"})); 
    // "Jméno: Anna, Věk: Neuvedeno"
    console.log(formatUserInput({})); 
    // "Jméno: Neznámý, Věk: Neuvedeno"
    ```

</details>

6. **Pokročilé:** Implementujte jednoduchou kalkulačku pomocí operátoru `switch` a funkce vyššího řádu. Kalkulačka by měla podporovat základní operace (+, -, *, /) a umožnit uživateli vybrat operaci a zadat dvě čísla.

- _<details><summary>Možné řešení</summary>_

    ```javascript
    function calculator(operation) {
    switch(operation) {
        case '+': return (a, b) => a + b;
        case '-': return (a, b) => a - b;
        case '*': return (a, b) => a * b;
        case '/': return (a, b) => b !== 0 ? a / b : "Nelze dělit nulou";
        default: return () => "Neplatná operace";
    }
    }

    function calculate(operation, a, b) {
    const operationFunc = calculator(operation);
    return operationFunc(a, b);
    }

    console.log(calculate('+', 5, 3)); // 8
    console.log(calculate('-', 10, 4)); // 6
    console.log(calculate('*', 2, 6)); // 12
    console.log(calculate('/', 15, 3)); // 5
    console.log(calculate('/', 10, 0)); // "Nelze dělit nulou"
    console.log(calculate('%', 10, 3)); // "Neplatná operace"
    ```

</details>

[**CheatSheet - Operators**](cheatsheet.md#operátory-operators)

[Zpět na obsah](#obsah-table-of-contents)

### Řídicí struktura (Control Flow)

Řídicí struktury (strukturované příkazy) určují pořadí, v jakém je kód vykonáván. Tyto příkazy umožňují programátorům vytvářet logiku, rozhodovat na základě podmínek a opakovat bloky kódu.

#### Základní strukturované příkazy

1. **`if...else` (Podmínkový příkaz)**
   - **Popis**: Provádí různé bloky kódu na základě splnění podmínky.
   - **Použití**: Rozhodování mezi dvěma nebo více možnostmi.
   - **Příklad**:
     ```javascript
     let vek = 18;

     if (vek >= 18) {
         console.log("Dospělý");
     } 
     else {
         console.log("Nezletilý");
     }
     // Dospělý
     ```
   - **Zajímavost**: Lze řetězit více podmínek pomocí `else if`.
     ```javascript
      let vek = 16;

      if (vek >= 18) {
          console.log("Dospělý");
      } 
      else if (vek >= 15) {
          console.log("Zodpovědný");
      } 
      else {
          console.log("Nezletilý");
      }
      // Zodpovědný
     ```

2. **`for` (Cyklus s pevným počtem opakování)**
   - **Popis**: Opakuje blok kódu specifikovaný počet krát.
   - **Použití**: Iterace přes pole, generování sekvencí.
   - **Příklad**:
     ```javascript
     for (let i = 0; i < 5; i++) {
         console.log(i);
     }
     // 0
     // 1
     // 2
     // 3
     // 4
     ```
   - **Zajímavost**: Lze použít `break` pro předčasné ukončení cyklu.
        ```javascript
        for (let i = 0; i < 5; i++) {
            if(i > 3) {
                break;
            }
            console.log(i);
        }
        // 0
        // 1
        // 2
        // 3
        ```

3. **`while` (Cyklus s podmínkou na začátku)**
   - **Popis**: Opakuje blok kódu, dokud je podmínka pravdivá.
   - **Použití**: Situace, kdy nevíme předem, kolikrát se má cyklus opakovat.
   - **Příklad**:
     ```javascript
     let i = 0;
     while (i < 5) {
         console.log(i);
         i++;
     }
     // 0
     // 1
     // 2
     // 3
     // 4
     ```
   - **Zajímavost**: Pokud podmínka není nikdy splněna, kód uvnitř cyklu se nikdy neprovede.
        ```javascript
        let i = 0;
        while (i > 5) {
            console.log(i);
            i++;
        }
        // No output
        ```

#### Středně pokročilé strukturované příkazy

4. **`switch` (Vícecestné větvení)**
   - **Popis**: Porovnává hodnotu s více případy a provádí odpovídající kód.
   - **Použití**: Když máme více možných hodnot pro jednu proměnnou.
   - **Příklad**:
     ```javascript
     let fruit = "Apple";
     switch (fruit) {
         case "Apple":
             console.log("jablko");
             break;
         case "Banana":
             console.log("banán");
             break;
         default:
             console.log("Neznámé ovoce");
     }
     // jablko
     ```
   - **Zajímavost**: Bez `break` se provádění "propadne" do dalšího case¹.
        ```javascript
        switch (fruit) {
            case "Apple":
            case "Pear":
                console.log("It's a pome fruit");
                break;
            case "Banana":
            case "Mango":
                console.log("It's a tropical fruit");
                break;
            default:
                console.log("Unknown fruit type");
        }
        ```

5. **`do...while` (Cyklus s podmínkou na konci)**
   - **Popis**: Podobný `while`, ale vždy se provede alespoň jednou.
   - **Použití**: Když potřebujeme zajistit, že se kód provede alespoň jednou.
   - **Příklad**:
     ```javascript
     let i = 0;
     do {
         i++;
         console.log(i);
     } while (i < 5);
     // 1
     // 2
     // 3
     // 4
     // 5
     ```
   - **Zajímavost**: Užitečné pro validaci uživatelského vstupu.

#### Pokročilé strukturované příkazy

6. **`for...of` (Iterace přes *hodnoty*)** - ITERACE
   - **Popis**: Iteruje přes hodnoty iterovatelných objektů (např. pole, řetězce).
   - **Použití**: Když potřebujeme pracovat s hodnotami, ale ne s indexy.
   - **Příklad**:
     ```javascript
     let fruits = ["jablko", "banán", "pomeranč"];
     for (let fruit of fruits) {
         console.log(fruit);
     }
     // jablko
     // banán
     // pomeranč
     ```
   - **Zajímavost**: Funguje i s novými datovými strukturami jako `Set` a `Map`.

7. **`for...in` (Iterace přes *vlastnosti*)** - ENUMERACE
   - **Popis**: Iteruje přes vlastnosti objektu.
   - **Použití**: Když potřebujeme pracovat s klíči objektu.
   - **Příklad**:
     ```javascript
     let person = {name: "Jan", age: 30, city: "Praha"};
     for (let key in person) {
         console.log(key + ": " + person[key]);
     }
     // name: Jan
     // age: 30
     // city: Praha
     ```
   - **Zajímavost**: Iteruje i přes zděděné vlastnosti².
     ```javascript
     const parent = { inherited: "I'm inherited" };

     const child = Object.create(parent);
     child.own = "I'm an own property";

     // Iterate over all properties
     for (let prop in child) {
        if (child.hasOwnProperty(prop)) {
            console.log("Own:", prop, child[prop]);
        } else {
            console.log("Inherited:", prop, child[prop]);
        }
     }
     // Own: own I'm an own property
     // Inherited: inherited I'm inherited
     ```

#### Další koncepty řídící struktury

8. **`break` a `continue`**
   - **Popis**: `break` ukončí celý cyklus, `continue` přeskočí zbytek aktuální iterace.
   - **Použití**: Optimalizace cyklů, předčasné ukončení.
   - **Příklad**:
     ```javascript
     for (let i = 0; i < 10; i++) {
         if (i === 7) break;
         if (i % 2 === 0) continue;
         console.log(i);
     }
     // 1
     // 3
     // 5
     ```
   - **Zajímavost**: Lze použít s popiskem (label) pro vnořené cykly³.
        ```javascript
        outerLoop: for (let i = 0; i < 3; i++) {
            for (let j = 0; j < 3; j++) {
                if (i === 1 && j === 1) {
                    console.log("Skipping i=1, j=1");
                    continue outerLoop;
                }
                console.log(`i=${i}, j=${j}`);
            }
        }
        // i=0, j=0
        // i=0, j=1
        // i=0, j=2
        // i=1, j=0
        // Skipping i=1, j=1
        // i=2, j=0
        // i=2, j=1
        // i=2, j=2
        ```

        ```javascript
        outerLoop: for (let i = 0; i < 3; i++) {
            for (let j = 0; j < 3; j++) {
                if (i === 1 && j === 1) {
                    console.log("Breaking at i=1, j=1");
                    break outerLoop;
                }
                console.log(`i=${i}, j=${j}`);
            }
        }
        // i=0, j=0
        // i=0, j=1
        // i=0, j=2
        // i=1, j=0
        // Breaking at i=1, j=1
        ```

9. **`try...catch...finally` (Zachytávání výjimek)**
   - **Popis**: Umožňuje zachytit a zpracovat chyby v kódu.
   - **Použití**: Ošetření chyb, zajištění robustnosti kódu.
   - **Příklad**:
     ```javascript
     try {
         // Kód, který může vyhodit chybu
         throw new Error("Něco se pokazilo");
     } catch (error) {
         console.log("Chyba:", error.message);
     } finally {
         console.log("Tento kód se provede vždy");
     }
     ```
   - **Zajímavost**: `finally` blok se provede vždy, i když dojde k chybě.

#### Cvičení:

1. Napište program, který vypíše čísla od 1 do 100. Pro násobky 3 vypíše "Fizz" místo čísla. Pro násobky 5 vypsat "Buzz". Pro čísla, která jsou násobky jak 3, tak 5, vypsat "FizzBuzz".

   <details>
   <summary>Řešení</summary>

   ```javascript
   for (let i = 1; i <= 100; i++) {
       if (i % 3 === 0 && i % 5 === 0) {
           console.log("FizzBuzz");
       } else if (i % 3 === 0) {
           console.log("Fizz");
       } else if (i % 5 === 0) {
           console.log("Buzz");
       } else {
           console.log(i);
       }
   }
   ```
   </details>

2. Vytvořit funkci, která vezme pole čísel a vrátí součet všech sudých čísel v poli pomocí cyklu for...of.

   <details>
   <summary>Řešení</summary>

   ```javascript
   function sumEvenNumbers(numbers) {
       let sum = 0;
       for (let num of numbers) {
           if (num % 2 === 0) {
               sum += num;
           }
       }
       return sum;
   }

   console.log(sumEvenNumbers([1, 2, 3, 4, 5, 6])); // Výstup: 12
   ```
   </details>

3. Implementovat jednoduchý kalkulátor pomocí příkazu switch, který může provádět sčítání, odčítání, násobení a dělení na základě vstupu uživatele.

   <details>
   <summary>Řešení</summary>

   ```javascript
   function calculator(a, b, operation) {
       switch (operation) {
           case '+':
               return a + b;
           case '-':
               return a - b;
           case '*':
               return a * b;
           case '/':
               if (b !== 0) {
                   return a / b;
               } else {
                   return "Nelze dělit nulou";
               }
           default:
               return "Neplatná operace";
       }
   }

   console.log(calculator(5, 3, '+')); // Výstup: 8
   console.log(calculator(5, 3, '-')); // Výstup: 2
   console.log(calculator(5, 3, '*')); // Výstup: 15
   console.log(calculator(6, 2, '/')); // Výstup: 3
   console.log(calculator(5, 0, '/')); // Výstup: Nelze dělit nulou
   ```
   </details>

4. Napište funkci, která najde největší prvek v poli čísel pomocí cyklu while.

   <details>
   <summary>Řešení</summary>

   ```javascript
   function findMax(numbers) {
       if (numbers.length === 0) return undefined;
       
       let max = numbers[0];
       let i = 1;
       while (i < numbers.length) {
           if (numbers[i] > max) {
               max = numbers[i];
           }
           i++;
       }
       return max;
   }

   console.log(findMax([3, 7, 2, 9, 1])); // Výstup: 9
   ```
   </details>

5. Vytvořte funkci, která převede objekt na pole párů klíč-hodnota pomocí for...in cyklu.

   <details>
   <summary>Řešení</summary>

   ```javascript
   function objectToPairs(obj) {
       let result = [];
       for (let key in obj) {
           if (obj.hasOwnProperty(key)) {
               result.push([key, obj[key]]);
           }
       }
       return result;
   }

   let person = {name: "Jan", age: 30, city: "Praha"};
   console.log(objectToPairs(person));
   // Výstup: [["name", "Jan"], ["age", 30], ["city", "Praha"]]
   ```
   </details>

6. Napište funkci, která simuluje hod kostkou, dokud nepadne šestka. Použijte do...while cyklus a vraťte počet hodů.

   <details>
   <summary>Řešení</summary>

   ```javascript
   function rollUntilSix() {
       let rolls = 0;
       let result;
       do {
           result = Math.floor(Math.random() * 6) + 1;
           rolls++;
       } while (result !== 6);
       return rolls;
   }

   console.log("Počet hodů do šestky:", rollUntilSix());
   ```
   </details>

#### Poznámky:
¹ **Propadnutí v switch**: Pokud se nepoužije `break`, kód "propadne" do dalšího case a pokračuje, dokud nenarazí na `break` nebo konec `switch`.

² **Zděděné vlastnosti**: `for...in` cyklus iteruje i přes vlastnosti, které objekt zdědil od svého prototypu. Pro iteraci pouze přes vlastní vlastnosti objektu lze použít `Object.hasOwnProperty()` metodu.

³ **Popisek (Label)**: Popisek (labels) v JavaScriptu umožňují označit cyklus nebo blok kódu a použít `break` nebo `continue` s tímto labelem pro ukončení nebo přeskočení označeného bloku.

---

[**CheatSheet - Control Flow**](cheatsheet.md#řídicí-struktura-control-flow)

[Zpět na obsah](#obsah-table-of-contents)