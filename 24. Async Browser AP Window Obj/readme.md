### Q1: XMLHttpRequest and AJAX

The `XMLHttpRequest` object is a built-in JavaScript object that provides an easy way to make HTTP requests and interact with server-side resources asynchronously. It is a fundamental part of the AJAX (Asynchronous JavaScript and XML) technology.

In AJAX, the `XMLHttpRequest` object is used to send HTTP requests to the server, retrieve data, and update the web page dynamically without requiring a full page reload.

### Q2: Example of Making an AJAX Request
Code:
[Here](./answer-02/index.html)

Output:
![](./assets/q-2.png)

### Q3: Same-Origin Policy in AJAX

The Same-Origin Policy is a security measure implemented by web browsers to prevent web pages from making requests to a different domain than the one that served the web page. This policy helps prevent potential security vulnerabilities, such as cross-site request forgery (CSRF) and cross-site scripting (XSS).

To work around the Same-Origin Policy, techniques like JSONP (JSON with Padding), Cross-Origin Resource Sharing (CORS), and server-side proxies can be used.

### Q4: Promises vs Callbacks

**Callbacks:**

- Traditional approach for handling asynchronous operations.
- Can lead to callback hell or the pyramid of doom when nesting multiple callbacks.
- Error handling can be challenging.

**Promises:**

- Introduced to simplify asynchronous code and improve readability.
- Allows chaining and composing asynchronous operations.
- Better error handling with `.catch()`.

Promises are preferred because they provide a more structured and readable way to handle asynchronous operations and avoid the callback hell problem.

### Q5: Common Browser APIs

1. **DOM API (Document Object Model):** Manipulates the structure and content of HTML documents.
2. **Event API:** Handles user interactions and events on web pages.
3. **Canvas API:** Provides a way to draw graphics using JavaScript.
4. **Geolocation API:** Retrieves the geographical location of a user's device.
5. **Web Storage API:** Allows storing data locally using `localStorage` and `sessionStorage`.
6. **Fetch API:** Provides a modern alternative to XMLHttpRequest for making HTTP requests.
7. **WebSockets API:** Enables bidirectional communication between a client and a server over a single, long-lived connection.

### Q6: localStorage and sessionStorage APIs

**localStorage:**

- Purpose: Stores data with no expiration time.
- Usage: Allows persistently storing data even after the browser is closed and reopened.

Example:

```javascript
// Storing data in localStorage
localStorage.setItem("username", "JohnDoe");

// Retrieving data from localStorage
var username = localStorage.getItem("username");
console.log(username); // JohnDoe
```

**sessionStorage:**

- Purpose: Stores data for the duration of a page session.
- Usage: Data is cleared when the page session ends (e.g., when the browser tab is closed).

Example:

```javascript
// Storing data in sessionStorage
sessionStorage.setItem("language", "JavaScript");

// Retrieving data from sessionStorage
var language = sessionStorage.getItem("language");
console.log(language); // JavaScript
```
