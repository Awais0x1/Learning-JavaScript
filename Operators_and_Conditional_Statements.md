
# Operators and Conditional Statements in JavaScript

## 1. Operators

### Types of Operators

#### 1. Arithmetic Operators
Used for mathematical calculations.
```javascript
let a = 10;
let b = 5;

console.log(a + b); // Addition: 15
console.log(a - b); // Subtraction: 5
console.log(a * b); // Multiplication: 50
console.log(a / b); // Division: 2
console.log(a % b); // Modulus: 0
console.log(a ** b); // Exponentiation: 100000
```

#### 2. Assignment Operators
Used to assign values to variables.
```javascript
let x = 10; // Assign
x += 5;     // Add and assign (x = x + 5)
x -= 3;     // Subtract and assign (x = x - 3)
x *= 2;     // Multiply and assign (x = x * 2)
x /= 2;     // Divide and assign (x = x / 2)
x %= 3;     // Modulus and assign (x = x % 3)
```

#### 3. Comparison Operators
Used to compare two values and return a boolean.
```javascript
console.log(10 == "10");  // Equality (true, type ignored)
console.log(10 === "10"); // Strict equality (false, type checked)
console.log(10 != "10");  // Inequality (false, type ignored)
console.log(10 !== "10"); // Strict inequality (true, type checked)
console.log(10 > 5);      // Greater than (true)
console.log(10 < 5);      // Less than (false)
console.log(10 >= 10);    // Greater than or equal to (true)
console.log(10 <= 5);     // Less than or equal to (false)
```

#### 4. Logical Operators
Used for logical conditions.
```javascript
console.log(true && false); // AND: false
console.log(true || false); // OR: true
console.log(!true);         // NOT: false
```

#### 5. Bitwise Operators
Operate on binary representations.
```javascript
console.log(5 & 1); // AND: 1
console.log(5 | 1); // OR: 5
console.log(~5);    // NOT: -6
console.log(5 ^ 1); // XOR: 4
console.log(5 << 1); // Left shift: 10
console.log(5 >> 1); // Right shift: 2
```

#### 6. String Operators
```javascript
let firstName = "John";
let lastName = "Doe";
console.log(firstName + " " + lastName); // Concatenation: John Doe
```

#### 7. Ternary Operator
Shorthand for `if-else`.
```javascript
let age = 20;
let isAdult = age >= 18 ? "Yes" : "No";
console.log(isAdult); // Yes
```

---

## 2. Conditional Statements

### 1. `if` Statement
Executes a block of code if the condition is `true`.
```javascript
let age = 18;
if (age >= 18) {
    console.log("You are an adult.");
}
```

### 2. `if-else` Statement
Executes one block of code if the condition is `true`, and another block if it is `false`.
```javascript
let age = 16;
if (age >= 18) {
    console.log("You are an adult.");
} else {
    console.log("You are a minor.");
}
```

### 3. `if-else if` Ladder
Allows multiple conditions to be checked in sequence.
```javascript
let marks = 85;
if (marks >= 90) {
    console.log("Grade: A+");
} else if (marks >= 80) {
    console.log("Grade: A");
} else if (marks >= 70) {
    console.log("Grade: B");
} else {
    console.log("Grade: C");
}
```

### 4. `switch` Statement
Selects one of many blocks of code to execute based on a value.
```javascript
let day = 3;
switch (day) {
    case 1:
        console.log("Monday");
        break;
    case 2:
        console.log("Tuesday");
        break;
    case 3:
        console.log("Wednesday");
        break;
    default:
        console.log("Invalid day");
}
```

### 5. `Conditional (Ternary)` Operator
Used as a shorthand for `if-else`.
```javascript
let age = 20;
let category = age >= 18 ? "Adult" : "Minor";
console.log(category); // Adult
```

### 6. `Logical` Operators in Conditions
Used to combine multiple conditions.
```javascript
let age = 25;
if (age >= 18 && age <= 30) {
    console.log("You are eligible.");
}
```

---

## Best Practices
1. Always use strict comparison (`===`) to avoid unexpected type coercion.
2. Use `default` in `switch` to handle unexpected cases.
3. Use ternary operators for simple conditions.
4. Avoid deeply nested `if` statements; refactor them into smaller functions when possible.
