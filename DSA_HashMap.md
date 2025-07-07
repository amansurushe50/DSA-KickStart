# 📘 HashMap (Hash Table / Dictionary) in JavaScript

A **HashMap** (also known as a hash table or dictionary in other programming languages) is a collection of key-value pairs that provides efficient lookup, insertion, and deletion operations — typically in **O(1)** time on average.

---

## ✅ JavaScript Built-in HashMap

JavaScript provides a built-in `Map` object that functions as a HashMap:

```js
const prices = new Map();
prices.set("apple", 100);
prices.get("apple"); // 100
```
- Use `Map` when you need insertion order and support for any key type (including objects).

---

## 🛠️ Custom HashMap Implementation

To better understand how HashMaps work internally, we can build our own implementation with the following core operations:

### Core Operations:
- **Insert** a key-value pair
- **Retrieve** a value by key
- **Delete** a key
- **Display** the internal structure
- **Hashing** of keys

---

## ⚙️ Hashing

A **hash function** converts a key (usually a string) into a numeric index to store it in an array (called a bucket array).

---

## Implementation

```javascript

class HashMap{
  constructor(size){
     this.table = new Array(size);
     this.size = size;
  }
  hash(key){
    let total = 0;
    for(let i =0; i< key.length; i++){
      total+= key.charCodeAt(i)
    }
    return total% this.size
  }
  
  set(key, value){
    const index = this.hash(key)
    this.table[index] = value
  }
  
  get(key){
    const index = this.hash(key)
    return this.table[index]
  }
  
  remove(key){
  const index = this.hash(key)
  this.table[index] = undefined
  }
  
  display(){
    for(let i= 0 ; i < this.table.length; i++){
      if(this.table[i]){
        console.log(i, this.table[i])
      }
    }
  }
  
}

const table = new HashMap(50);

table.set('name','Aman')
table.set('age','32')
table.remove('name')
table.get('name')
table.get('age')
table.remove('name')

```
## ⚠️ Problem: Collisions

**What happens if you set a key with `{ name: "Aman" }` and then another key `{ name: "Riyan" }`?**

You may observe **loss of data**.  
**Why?**  
If the hash function returns the same index for both, the second value **overwrites** the first — this is called a **collision**.

**Note:** The data should never be lost!

---

## 🛡️ Collision Resolution Strategies

When two different keys hash to the same index (**collision**), we need strategies to resolve them:

### 1. Separate Chaining

- Each bucket holds a list (e.g., an array or linked list) of key-value pairs.
- Multiple values can coexist in the same bucket.

**Pros:**  
✅ Simple and effective.

**Cons:**  
❌ Can increase memory usage and degrade performance with too many collisions.

---

### 2. Open Addressing (Probing)

Instead of using a list, open addressing looks for the next available slot within the array.

#### a. Linear Probing

- If a collision occurs at index `i`, check `i+1`, `i+2`, `i+3`, etc., until an empty slot is found.

#### b. Quadratic Probing

- The step size increases quadratically:  
  Check `i + 1²`, `i + 2²`, `i + 3²`, and so on.

#### c. Double Hashing

- Use a second hash function to compute the step size:  
  `index = (hash1(key) + i * hash2(key)) % size`

**Pros:**  
✅ Reduces clustering compared to linear probing.

**Cons:**  
❌ More complex to implement and requires careful selection of hash functions.

---

## 📝 Summary

- HashMaps provide **constant time** operations for insert, lookup, and delete.
- **Collisions** can cause data loss if not handled.
- **Separate chaining** and **open addressing** are common strategies to resolve collisions.

---

## 📚 References

- [MDN Web Docs: Map](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map)
- [Wikipedia: Hash Table](https://en.wikipedia.org/wiki/Hash_table)

---
