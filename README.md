# -IMPORTANT-FUNCTIONS-AND-HOISTING

## 🧠 **JavaScript Hoisting**

---

### 🔵 **1. Function Declarations — Fully Hoisted**
**Definition:** The entire function is hoisted. You can call it *before* it appears in the code.

```js
sayHello(); // ✅ works

function sayHello() {
  console.log("Hello");
}
```

**Mental model:**  
> JS lifts the whole function to the top.

**Use when:**  
- You want flexible ordering  
- Teaching beginners  
- Writing utility functions

---

### 🟢 **2. Function Expressions — NOT Hoisted**
**Definition:** Only the *variable name* is hoisted, not the function value.

```js
sayHello(); // ❌ error: sayHello is not a function

const sayHello = function () {
  console.log("Hello");
};
```

**Mental model:**  
> JS lifts the *variable*, but it’s still empty until assignment.

**Use when:**  
- You want predictable, strict ordering  
- You want block‑scoped behavior

---

### 🟣 **3. Arrow Functions — NOT Hoisted**
Arrow functions behave exactly like function expressions.

```js
sayHello(); // ❌ error

const sayHello = () => {
  console.log("Hello");
};
```

**Mental model:**  
> Arrow functions are just function expressions with nicer syntax.

**Common beginner trap:**  
Using the function before it’s defined.

---

### 🟠 **4. Class Declarations — NOT Hoisted**
Classes behave like `const` variables — they exist but cannot be used before definition.

```js
const user = new User(); // ❌ ReferenceError

class User {}
```

**Mental model:**  
> Classes are “hoisted” but in a locked state until defined.

---

### 🔴 **5. `var` — Hoisted but Dangerous**
`var` is hoisted **and initialized to `undefined`**, causing weird behavior.

```js
console.log(name); // undefined (not an error!)
var name = "Nafiz";
```

**Mental model:**  
> JS lifts the variable AND gives it a default value.

**Avoid in modern code.**

---

## 🧩 **Summary Table (Color‑coded for your classroom)**

| Construct | Hoisted? | Usable Before Definition? | Notes |
|----------|----------|---------------------------|-------|
| **Function Declaration** | Yes | **Yes** | Safest for beginners |
| **Function Expression** | Variable only | **No** | Must be defined first |
| **Arrow Function** | Variable only | **No** | Same rules as expressions |
| **Class Declaration** | Yes (but locked) | **No** | Throws ReferenceError |
| **var** | Yes (initialized to `undefined`) | Yes (but unsafe) | Avoid |

---

## ⚡ Bonus: The 3‑Line Rule You Can Teach Students
> **Declarations hoist. Assignments don’t.**  
> **Function declarations hoist fully.**  
> **Arrow functions behave like variables.**

---
