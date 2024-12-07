# 020-conditions-and-loops

**Q1. What are conditional statements? Explain conditional statements with syntax and examples.**

Conditional statements allow you to control the flow of execution of a program based on certain conditions. They allow you to write code that performs different actions depending on whether a condition is true or false.

**Syntax:**

```javascript
if (condition) {
  // code to execute if the condition is true
} else {
  // code to execute if the condition is false
}
```

**Example:**

```javascript
let age = 18;

if (age >= 18) {
  console.log("You are eligible to vote.");
} else {
  console.log("You are not eligible to vote.");
}
```

**Q2. Write a program that grades students based on their marks.

If greater than 90 then A Grade
If between 70 and 90 then a B grade
If between 50 and 70 then a C grade
Below 50 then an F grade**

```javascript
function gradeStudent(marks) {
  if (marks >= 90) {
    return "A";
  } else if (marks >= 70 && marks < 90) {
    return "B";
  } else if (marks >= 50 && marks < 70) {
    return "C";
  } else {
    return "F";
  }
}

const studentMarks = 85;
const grade = gradeStudent(studentMarks);
console.log(`Student's grade: ${grade}`);
```

**Q3. What are loops, and what do we need them? Explain different types of loops with their syntax and
examples.**

Loops are used to repeat a block of code multiple times. They are useful for tasks that need to be done repeatedly, such as iterating over a collection of data or performing calculations.

**Types of loops:**

* **For loop:** Used to iterate a specific number of times.
* **While loop:** Used to iterate until a condition becomes false.
* **Do...while loop:** Similar to a while loop, but it always executes the code block at least once, even if the condition is false initially.

**Syntax:**

```javascript
// For loop
for (let i = 0; i < 5; i++) {
  // code to execute
}

// While loop
let i = 0;
while (i < 5) {
  // code to execute
  i++;
}

// Do...while loop
let i = 0;
do {
  // code to execute
  i++;
} while (i < 5);
```

**Example:**

```javascript
// Print numbers from 1 to 5
for (let i = 1; i <= 5; i++) {
  console.log(i);
}
```

**Q4. Generate numbers between any 2 given numbers.

Ex:

```
const num1 = 10;

const num2 = 25;

Output: 11, 12, 13, ..., 25
```

```javascript
function generateNumbers(start, end) {
  const numbers = [];
  for (let i = start + 1; i < end; i++) {
    numbers.push(i);
  }
  return numbers;
}

const num1 = 10;
const num2 = 25;
const generatedNumbers = generateNumbers(num1, num2);
console.log(generatedNumbers); // Output: [11, 12, 13, ..., 24]
```

**Q5. Use the while loop to print numbers from 1 to 25 in ascending and descending order.**

**Ascending order**

```javascript
let i = 1;
while (i <= 25) {
  console.log(i);
  i++;
}
```

**Descending order**

```javascript
let i = 25;
while