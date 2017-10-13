# Table of Content

<!-- TOC depthFrom:1 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->
- [JS](#js)  
  - [Parsing](#parsing)  
  - [Predicates](#predicates)  
  - [Booleans](#booleans)  
  - [Variables](#variables)  
  - [Comparison](#comparison)  
  - [For-Each](#for-each)  
  - [Short-Circuit Logic](#short-circuit-logic)  
  - [One-Liner Conditional (Ternary)](#one-liner-conditional-ternary)  
  - [Arrays Methods](#arrays-methods)  
  - [Functions](#functions)  
  - [Inheritance (Delegation)](#inheritance-delegation)  
  - [Best Practice](#best-practice)  
  - [Resources](#resources)  
- [JSON](#json)  
  - [Parse](#parse)  
  - [Misc.](#misc)  
- [Markdown](#markdown)  
  - [Links](#links)  

---

# JS

#### Parsing
```js
parseInt(string, radix);
parseInt('hello', 10); // NaN
parseFloat(string); // radix always 10

// + operator as parser
+ '010';  // 10

// + vs. parseInt or parseFloat
parseFloat('10.2abc') // 10.2
parseInt('10.2abc') // 10
+ '10.2abc' // NaN
```

#### Predicates
```js
isNaN(NaN); // true
isFinite(NaN); // false
```

#### Booleans
`false`, `0`, empty strings (`""`), `NaN`, `null`, and `undefined` all become false. Anything else is `true`.

#### Variables
> `let` is a block-level variable.
> `const` is a block-level constant that raises an error on modification.  
> `var` is a function-level variable.

#### Comparison
``` js
123 == '123'; // true
1 == true; // true

// BUT...

123 === '123'; // false
1 === true;    // false
```

#### For-Each
```js
myArray.forEach(function(currentValue, index, array) {
  // Do something with currentValue or array[index]
});

for (let property in object) {
  // do something with object property
}
```

#### Short-Circuit Logic
```js
// Check for null object before accessing its properties
var name = object && object.getName();

// Get cached version if it exists
var name = cachedName || (cachedName = getName());
```

#### One-Liner Conditional (Ternary)
```js
var allowed = (age > 18) ? 'yes' : 'no';
```

#### Arrays Methods
| Method name | Description |
| ----------- | ----------- |
| `a.toString()` | Returns a string with the toString() of each element separated by commas. |
| `a.toLocaleString()` | Returns a string with the toLocaleString() of each element separated by commas. |
| `a.concat(item1[, item2[, ...[, itemN]]])` | Returns a new array with the items added on to it. |
| `a.join(sep)` | Converts the array to a string — with values delimited by the `sep` param |
| `a.pop()` |	Removes and returns the last item. |
| `a.push(item1, ..., itemN)` | Appends items to the end of the array. |
| `a.reverse()` | Reverses the array. |
| `a.shift()` | Removes and returns the first item. |
| `a.slice(start[, end])` | Returns a sub-array. |
| `a.sort([cmpfn])` | Takes an optional comparison function. |
| `a.splice(start, delcount[, item1[, ...[, itemN]]])` | Lets you modify an array by deleting a section and replacing it with more items. |
| `a.unshift(item1[, item2[, ...[, itemN]]])` | Prepends items to the start of the array. |

#### Functions
- Missing arguments won't throw an error, they'll be `undefined` inside the function scope.  
Likewise, any argument over the expectation will be ignored.  
- Using the **rest parameter operator** (`...args`) will hold all the excessive arguments **after** the positional arguments.
- `arguments` is an array-like variable holding all the parameters passed to the function.

#### Inheritance (Delegation)
1. **Super Constructor** - Add a `call` to parent constructor within the child's constructor.
2. **Rewire Prototype Chain** - Copy the `prototype` property of the parent to the child using
`Object.create(Parent.prototype)`
3. **Reset Constructor** - Reset the child's `constructor` property to point to the child's constructor `Child.prototype.constructor = Child`

#### Best Practice
- Define the properties at the constructor and the methods on the `prototype`.  
Sort of like exposing an API for inheritance.

#### Resources
- [Mozilla's re-introduction to JS](https://developer.mozilla.org/en-US/docs/Web/JavaScript/A_re-introduction_to_JavaScript)

---

# JSON

#### Parse
   - `JSON.parse()` JSON to JS object.
   - `JSON.stringify()` JS object to JSON.

#### Misc.
   - Use double quotes `""`, not singles.

---

# Markdown

#### Links
`Dillinger requires [Node.js](https://nodejs.org/) v4+ to run.`
Dillinger requires [Node.js](https://nodejs.org/) v4+ to run.
