# 019-js-fundamental-part-2

## Problem Statement 1: Ternary Operator and Even/Odd check

**Ternary operator syntax:**

```javascript
condition ? expressionIfTrue : expressionIfFalse;
```

**Program for checking even/odd:**

```javascript
function isEven(number) {
  return number % 2 === 0 ? "Even" : "Odd";
}

const num = 10;
const result = isEven(num);
console.log(result); // Output: Even
```

## Problem Statement 2: Comma Operator

**Comma operator usage:**

* Separate multiple expressions in a single statement.
* Evaluate expressions from left to right and return the value of the last expression.

**Example:**

```javascript
let x = 1, y = 2;
console.log((x++, y++)); // Output: 2 (x incremented after the comma)
```

## Problem Statement 3: Nested Ternary Operator for Positive/Negative/Zero

```javascript
function checkNumber(number) {
  return number > 0 ? "Positive" : number < 0 ? "Negative" : "Zero";
}

const num = -5;
const result = checkNumber(num);
console.log(result); // Output: Negative
```

## Problem Statement 4: Ternary Operator for Voting Eligibility

```javascript
function checkVotingEligibility(age) {
  return age >= 18 ? "You can vote" : "You cannot vote";
}

const personAge = 17;
const message = checkVotingEligibility(personAge);
console.log(message); // Output: You cannot vote
```
