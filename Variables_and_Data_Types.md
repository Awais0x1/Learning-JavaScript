
# Variables & Data Types in JavaScript

## 1. Variables

### What Are Variables?
- A variable is a container for storing data values.
- JavaScript uses three keywords to declare variables: `var`, `let`, and `const`.

### Declaring Variables
- **`var`**: Function-scoped or globally-scoped.
- **`let`**: Block-scoped and cannot be redeclared.
- **`const`**: Block-scoped and must be assigned a value at the time of declaration.

```javascript
// Using var
var x = 5;

// Using let
let y = 10;

// Using const
const z = 15;
```

### Rules for Naming Variables
1. Must start with a letter, `_`, or `$`.
2. Cannot contain spaces or special characters (other than `_` and `$`).
3. Reserved keywords (e.g., `let`, `const`) cannot be used as variable names.

### Scope of Variables
- **Global Scope**: Variables declared outside any function or block.
- **Local Scope**: Variables declared inside a function.
- **Block Scope**: Variables declared with `let` or `const` within a block `{}`.

### Hoisting
- JavaScript moves declarations to the top of their scope during compilation.
  - `var` is hoisted with `undefined`.
  - `let` and `const` are hoisted but remain in a **Temporal Dead Zone (TDZ)** until their initialization.

Example:
```javascript
console.log(a); // undefined
var a = 5;

console.log(b); // Error: Cannot access 'b' before initialization
let b = 10;
```

---

## 2. Data Types

### Two Categories of Data Types
1. **Primitive Data Types**: Immutable and stored by value.
2. **Reference Data Types**: Mutable and stored by reference.

### Primitive Data Types
1. **Number**
   - Includes integers and floating-point numbers.
   - Special values: `Infinity`, `-Infinity`, and `NaN`.
   ```javascript
   let num = 42;
   let pi = 3.14;
   let big = 1.23e5; // 123000
   ```

2. **String**
   - Text values enclosed in `'`, `"`, or `` (template literals).
   ```javascript
   let str = "Hello";
   let template = `Value: ${num}`;
   ```

3. **Boolean**
   - Logical `true` or `false`.
   ```javascript
   let isActive = true;
   let isLogged = false;
   ```

4. **Undefined**
   - Default value of an uninitialized variable.
   ```javascript
   let x; 
   console.log(x); // undefined
   ```

5. **Null**
   - Represents the intentional absence of any value.
   ```javascript
   let empty = null;
   ```

6. **Symbol**
   - A unique and immutable identifier (introduced in ES6).
   ```javascript
   let sym = Symbol("id");
   ```

7. **BigInt**
   - Used for integers larger than `Number.MAX_SAFE_INTEGER`.
   ```javascript
   let big = 123456789012345678901234567890n;
   ```

### Reference Data Types
1. **Object**
   - Collection of key-value pairs.
   ```javascript
   let user = { name: "Alice", age: 25 };
   ```

2. **Array**
   - Ordered collection of elements.
   ```javascript
   let arr = [1, 2, 3];
   ```

3. **Function**
   - A block of reusable code.
   ```javascript
   function greet() {
       return "Hello!";
   }
   ```

### Dynamic Typing
- JavaScript allows variables to hold values of any type, and the type can change during execution.
  ```javascript
  let x = 42;       // Number
  x = "Hello";      // String
  ```

### Type Conversion

#### Explicit Conversion
1. **To Number**: `Number()`, `parseInt()`, `parseFloat()`
   ```javascript
   Number("42"); // 42
   parseInt("42.5"); // 42
   parseFloat("42.5"); // 42.5
   ```

2. **To String**: `String()`, `toString()`
   ```javascript
   String(42); // "42"
   (42).toString(); // "42"
   ```

3. **To Boolean**: `Boolean()`
   ```javascript
   Boolean(1); // true
   Boolean(0); // false
   ```

#### Implicit Conversion (Type Coercion)
- JavaScript automatically converts data types when necessary.
  ```javascript
  console.log("5" - 2); // 3 (string to number)
  console.log("5" + 2); // "52" (number to string)
  ```

### Falsy Values
- In JavaScript, these values are considered falsy:
  - `false`
  - `0`
  - `""` (empty string)
  - `null`
  - `undefined`
  - `NaN`

Everything else is truthy.

### Type Checking
1. **Using `typeof`**
   ```javascript
   typeof 42;         // "number"
   typeof "Hello";    // "string"
   typeof null;       // "object" (quirk in JavaScript)
   typeof undefined;  // "undefined"
   ```

2. **Checking Arrays**
   ```javascript
   Array.isArray([1, 2, 3]); // true
   ```

3. **Custom Type Check**
   ```javascript
   function customTypeCheck(value) {
       if (value === null) return "null";
       if (Array.isArray(value)) return "array";
       return typeof value;
   }
   ```

---

## 3. Key Concepts

### Pass by Value vs. Pass by Reference
- **Primitives** are passed by value (copies the value).
- **Objects** are passed by reference (points to the same memory).
  ```javascript
  let x = 10;
  let y = x; 
  y = 20; 
  console.log(x); // 10 (unchanged)

  let obj1 = { name: "Alice" };
  let obj2 = obj1;
  obj2.name = "Bob";
  console.log(obj1.name); // "Bob" (same reference)
  ```

### Best Practices
1. Always use `const` unless you know the value will change.
2. Use `let` for block-scoped variables.
3. Avoid `var` due to its hoisting behavior and lack of block scope.
4. Explicitly define types where possible to avoid bugs due to type coercion.
