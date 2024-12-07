# Array and Objects

### 1. Shopping Cart Operations

```javascript
const shoppingCart = ["Milk", "Coffee", "Tea", "Honey"];

// Add items
if (!shoppingCart.includes("Meat")) {
  shoppingCart.unshift("Meat"); // Add Meat at the beginning
}
if (!shoppingCart.includes("Sugar")) {
  shoppingCart.push("Sugar"); // Add Sugar at the end
}

// Remove item
const allergicToHoney = true;
if (allergicToHoney) {
  const indexToRemove = shoppingCart.indexOf("Honey");
  if (indexToRemove !== -1) {
    shoppingCart.splice(indexToRemove, 1);
  }
}

// Modify item
const indexOfTea = shoppingCart.indexOf("Tea");
if (indexOfTea !== -1) {
  shoppingCart[indexOfTea] = "Green Tea";
}

console.log(shoppingCart);
```

Output:

```javascript
["Meat", "Milk", "Coffee", "Green Tea", "Sugar"];
```

### 2. Array Operations with Ages

```javascript
const ages = [19, 22, 19, 24, 20, 25, 21, 24, 25, 24];

// Sort and find min and max age
const sortedAges = ages.sort((a, b) => a - b);
const minAge = sortedAges[0];
const maxAge = sortedAges[sortedAges.length - 1];

// Find median age
const middleIndex = Math.floor(sortedAges.length / 2);
const medianAge =
  sortedAges.length % 2 === 0
    ? (sortedAges[middleIndex - 1] + sortedAges[middleIndex]) / 2
    : sortedAges[middleIndex];

// Find average age
const averageAge = ages.reduce((sum, age) => sum + age, 0) / ages.length;

// Find range
const ageRange = maxAge - minAge;

// Compare (min - average) and (max - average)
const diffMinAverage = Math.abs(minAge - averageAge);
const diffMaxAverage = Math.abs(maxAge - averageAge);

console.log("Min Age:", minAge);
console.log("Max Age:", maxAge);
console.log("Median Age:", medianAge);
console.log("Average Age:", averageAge);
console.log("Age Range:", ageRange);
console.log("Difference (Min - Average):", diffMinAverage);
console.log("Difference (Max - Average):", diffMaxAverage);
```

### 3. Object Extensibility and Sealing

```javascript
const student = { firstName: "John", lastName: "Doe", age: 20, grade: "A" };

// a) Prevent further extensions
Object.preventExtensions(student);

// b) Check if extensible
const extensibleStatus = Object.isExtensible(student);

// c) Create a new object 'teacher' and seal it
const teacher = { subject: "Math" };
Object.seal(teacher);

// d) Check if sealed
const sealedStatus = Object.isSealed(teacher);

// e) Print results
console.log("Extensible Status:", extensibleStatus); // false
console.log("Sealed Status:", sealedStatus); // true
```

Output:

```
Extensible Status: false
Sealed Status: true
```

### 4. Student Management System

```javascript
const students = [
  { id: 1, firstName: "Alice", lastName: "Smith", age: 20, grade: "B" },
  { id: 2, firstName: "Bob", lastName: "Johnson", age: 22, grade: "A" },
  // Add more students as needed
];

// a. Add a Student
function addStudent(student) {
  students.push(student);
}

// b. Update Student Information
function updateStudent(id, updatedInfo) {
  const index = students.findIndex((student) => student.id === id);
  if (index !== -1) {
    students[index] = { ...students[index], ...updatedInfo };
  }
}

// c. Delete a Student
function deleteStudent(id) {
  const index = students.findIndex((student) => student.id === id);
  if (index !== -1) {
    students.splice(index, 1);
  }
}

// d. List All Students
function listAllStudents() {
  console.log(students);
}

// e. Find Students by Grade
function findStudentsByGrade(grade) {
  return students.filter((student) => student.grade === grade);
}

// f. Calculate Average Age
function calculateAverageAge() {
  const totalAge = students.reduce((sum, student) => sum + student.age, 0);
  return totalAge / students.length;
}

// Testing the functions
addStudent({
  id: 3,
  firstName: "Charlie",
  lastName: "Brown",
  age: 21,
  grade: "C",
});
updateStudent(1, { age: 21 });
deleteStudent(2);
listAllStudents();
console.log("Students with grade 'A':", findStudentsByGrade("A"));
console.log("Average Age:", calculateAverageAge());
```

### 5. 'for...in' Loop for Student Object

```JavaScript
function displayStudentInfo(student) {
  // use a for...in loop to iterate over the properties of the student object
  for (let property in student) {
    // print each property and its corresponding value to the console
    console.log(`Property: ${property}, Value: ${student[property]}`);
  }
}

displayStudentInfo(student);

```

Output:

```
Property: name, Value: Alice
Property: age, Value: 22
Property: major, Value: Computer Science
Property: GPA, Value: 3.8
Property: isEnrolled, Value: true
```