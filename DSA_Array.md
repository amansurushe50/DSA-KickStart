

## Arrays

Arrays are ordered lists of values.

### Declaration

* **Static Declaration:** Creating an array with elements.
    ```javascript
    let arr = [1, 2, 3, 4];
    ```

* **Dynamic Declaration:** Creating an empty array.
    ```javascript
    let arr = new Array();
    ```

### Common Operations

* **Traversal**: Visiting each element.
* **Insertion**: Adding elements.
* **Deletion**: Removing elements.
* **Searching**: Finding an element.

---

## JavaScript Libraries

### 🧮 Math Library

Quick access to mathematical constants and functions.

```javascript
Math.max(1, 5, 10);      // 10
Math.min(1, 5, 10);      // 1
Math.floor(4.9);         // 4
Math.ceil(4.1);          // 5
Math.round(4.6);         // 5
Math.abs(-5);            // 5
Math.sqrt(16);           // 4
Math.random();           // [0,1)
```

### 📅 Date Library

For working with dates and times.

```javascript
const now = new Date();
now.getFullYear();        // 2025
now.getMonth();           // 0-based (0 = Jan)
now.getDate();            // Day of the month
now.toISOString();        // ISO format
```

### 📋 Array Utilities (Most Common in DSA)
### 🔁 Looping & Transformation

```javascript
arr.forEach(el => console.log(el));
arr.map(x => x * 2);             // transform array
arr.filter(x => x > 2);          // keep only > 2
arr.reduce((a, b) => a + b, 0);  // sum
arr.some(x => x > 3);            // true if any match
arr.every(x => x > 0);           // true if all match
```

### 🔧 Modifying

```javascript
arr.push(4);             // add to end
arr.pop();               // remove from end
arr.shift();             // remove from start
arr.unshift(1);          // add to start
arr.slice(1, 3);         // extract [1, 2]
arr.splice(1, 2);        // remove from index 1
arr.sort((a, b) => a - b); // numeric sort
arr.reverse();           // reverse array
```

### 🧵 String Utilities

```javascirpt
str.length;
str.toLowerCase();
str.toUpperCase();
str.includes("abc");
str.indexOf("abc");
str.slice(1, 4);
str.split(" ");          // to array
str.trim();              // remove whitespaces
str.replace("a", "b");
```

### 📦 Object & JSON Utilities

```javascript
Object.keys(obj);
Object.values(obj);
Object.entries(obj);
JSON.stringify(obj);
JSON.parse(string);
```

### Problems to Solve (Hands-On)

* [x] Find max/min element
* [x] Reverse an array
* [x] Find max/min element
* [x] Traverse array and print elements
* [x] Sum of all elements
* [x] Search an element [Binary and sequential]
* [x] Insert at index
* [x] Count frequency of elements
