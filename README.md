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

#### Základní datové typy (pro začátečníky):

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
   
   <details>
   <summary>Řešení</summary>

   ```javascript
   const jmeno = "Jan Novák";
   let vek = 31;
   ```
   </details>

2. Zkuste přeřadit `const` proměnnou. Co se stane?
   
   <details>
   <summary>Řešení</summary>

   ```javascript
   const jmeno = "Karel Dravý";
   jmeno = "Ondřej Prchal" // TypeError: Assignment to a constant variable.
   ```
   </details>

3. Vytvořte objekt pomocí `const` a modifikujte jednu z jeho vlastností. Je to možné?
   
   <details>
   <summary>Řešení</summary>

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