# JavaScript Fundamentals Assignment Solutions

### Q1: Write a JavaScript function called outerFunction that takes a parameter and returns an inner function. The inner function should access both the parameter of outerFunction and a variable declared within outerFunction. Demonstrate how lexical scoping allows the inner function to maintain access to these variables even after outerFunction has finished executing.

```javascript
function outerFunction(parameter) {
  // Variable declared within outerFunction
  let innerVariable = "I am from outerFunction";

  // Inner function accessing both parameter and innerVariable
  function innerFunction() {
    console.log(`Parameter from outerFunction: ${parameter}`);
    console.log(`Inner variable from outerFunction: ${innerVariable}`);
  }

  // Returning the inner function
  return innerFunction;
}

// Creating an instance of outerFunction
const myInnerFunction = outerFunction("Hello, lexical scoping!");

// Calling the inner function even after outerFunction has finished executing
myInnerFunction();
```

Output:

```
Parameter from outerFunction: Hello, lexical scoping!
Inner variable from outerFunction: I am from outerFunction
```

### Q2: Create a JavaScript program that demonstrates the basic usage of regular expressions. Write a function that takes a regex pattern and a string as input and returns true if there is a match, and false otherwise. Test the function with various patterns and strings.

```javascript
function matchWithRegex(pattern, inputString) {
  const regex = new RegExp(pattern);
  return regex.test(inputString);
}

// Testing the function with various patterns and strings
console.log(matchWithRegex("\\d{3}", "123")); // true
console.log(matchWithRegex("[A-Za-z]+", "Hello")); // true
console.log(matchWithRegex("\\d{3}", "abc")); // false
```

Output:

```
true
true
false
```

### Q3: Write a JavaScript program that demonstrates the use of character classes in regular expressions. Create a function that searches for specific character classes in a given string and returns the matches. Test the function with patterns for digits, uppercase letters, lowercase letters, and special characters.

```javascript
function matchCharacterClasses(inputString) {
  const digitPattern = /\d/g;
  const uppercasePattern = /[A-Z]/g;
  const lowercasePattern = /[a-z]/g;
  const specialCharPattern = /[^A-Za-z0-9]/g;

  return {
    digits: inputString.match(digitPattern),
    uppercaseLetters: inputString.match(uppercasePattern),
    lowercaseLetters: inputString.match(lowercasePattern),
    specialCharacters: inputString.match(specialCharPattern),
  };
}

// Testing the function with a sample string
const result = matchCharacterClasses("Hello123! World");
console.log(result);
```

Output:

```javascript
{
  digits: [ '1', '2', '3' ],
  uppercaseLetters: [ 'H', 'W' ],
  lowercaseLetters: [ 'e', 'l', 'l', 'o', 'r', 'l', 'd' ],
  specialCharacters: [ '!', ' ' ]
}
```

### Q4: Create a JavaScript program that takes a regex pattern and a string as input. Write a function that not only checks if there is a match but also extracts specific parts of the matched text using groups. Test the function with patterns that include groups to capture different parts of a date (e.g., day, month, and year) from a given string.

```javascript
function extractDateParts(pattern, inputString) {
  const regex = new RegExp(pattern);
  const match = regex.exec(inputString);

  if (match) {
    // Extracting parts using groups
    const [fullMatch, day, month, year] = match;
    return { day, month, year };
  }

  return null;
}

// Testing the function with a date pattern
const datePattern = /(\d{2})-(\d{2})-(\d{4})/;
const dateString = "25-12-2022";
const extractedDate = extractDateParts(datePattern, dateString);
console.log(extractedDate);
```

Output:

```javascript
{
  day: '25',
  month: '12',
  year: '2022'
}
```

### Q5: You are building a shipping application. Write a program that takes the type of package ("standard", "express", or "overnight") and uses a switch statement to calculate and print the estimated delivery time based on the package type. For example, "standard" might take 3-5 days, "express" 1-2 days, and "overnight" would be delivered the next day.

```javascript
function calculateDeliveryTime(packageType) {
  let deliveryTime;

  switch (packageType.toLowerCase()) {
    case "standard":
      deliveryTime = "3-5 days";
      break;
    case "express":
      deliveryTime = "1-2 days";
      break;
    case "overnight":
      deliveryTime = "next day";
      break;
    default:
      deliveryTime = "not specified";
  }

  console.log(`Estimated delivery time for ${packageType}: ${deliveryTime}`);
}

// Testing the function with different package types
calculateDeliveryTime("standard");
calculateDeliveryTime("express");
calculateDeliveryTime("overnight");
calculateDeliveryTime("unknown");
```

Output:

```
Estimated delivery time for standard: 3-5 days
Estimated delivery time for express: 1-2 days
Estimated delivery time for overnight: next day
Estimated delivery time for unknown: not specified
```
