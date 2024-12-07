# 021-function-assignments

**Q1: Square Arrow Function**

```javascript
const square = (number) => number * number;

const result = square(5);
console.log(result); // Output: 25
```

**Q2: Generate Greeting Function**

```javascript
function generateGreeting(name) {
  return `Hello, ${name}!`;
}

const greeting1 = generateGreeting("John");
const greeting2 = generateGreeting("Mary");
const greeting3 = generateGreeting("Peter");

console.log(greeting1); // Output: Hello, John!
console.log(greeting2); // Output: Hello, Mary!
console.log(greeting3); // Output: Hello, Peter!
```

**Q3: IIFE for Square Calculation**

```javascript
(function calculateSquare(number) {
  const result = number * number;
  console.log(result); // Output: squared number
})(10);
```

**Q4: Calculate Tax with Closure**

```javascript
function calculateTax(income) {
  let taxRate;

  if (income <= 10000) {
    taxRate = 0.1;
  } else if (income <= 20000) {
    taxRate = 0.15;
  } else {
    taxRate = 0.2;
  }

  return income * taxRate;
}

const tax1 = calculateTax(15000);
const tax2 = calculateTax(25000);

console.log(`Tax for 15000: ${tax1}`); // Output: Tax for 15000: 2250
console.log(`Tax for 25000: ${tax2}`); // Output: Tax for 25000: 5000
```

**Q5: Factorial with Recursion**

```javascript
function factorial(number) {
  if (number === 0) {
    return 1;
  }
  return number * factorial(number - 1);
}

const result1 = factorial(5); // 120
const result2 = factorial(3); // 6

console.log(result1);
console.log(result2);
```

**Q6: Currying Function**

```javascript
function curry(fn) {
  const args = [];
  return function curried(...newArgs) {
    args.push(...newArgs);
    if (args.length === fn.length) {
      return fn(...args);
    }
    return curried;
  };
}

const add = curry((a, b) => a + b);

const sum1 = add(5);
const sum2 = sum1(10);

console.log(sum2); // Output: 15
```
