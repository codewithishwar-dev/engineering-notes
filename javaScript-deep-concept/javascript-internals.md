# 🚀 JavaScript Internals — Code With Ishwar

Most developers think they know JavaScript.

They don’t.

They know syntax…  
but miss the **real power behind it**.

---

## ⚡ JavaScript isn’t powerful because of features  
It’s powerful because of **how it behaves under the hood**

---

## 🧠 1. Functions are First-Class Citizens

You can pass, return, and store functions anywhere.

```js
function greet(name) {
  return `Hello, ${name}`;
}

const sayHi = greet;
console.log(sayHi("Ishwar")); // Hello, Ishwar
```
➡️ Enables callbacks, middleware, hooks

🔁 2. Closures (The Silent Superpower)

Functions remember their scope—even after execution.
```
function createCounter() {
  let count = 0;

  return function () {
    count++;
    return count;
  };
}


const counter = createCounter();
console.log(counter()); // 1
console.log(counter()); // 2
```
➡️ Used for:

Data privacy
Encapsulation
React hooks

⏳ 3. Event Loop (Non-Blocking Magic)

JavaScript is single-threaded but handles async efficiently.
```
console.log("Start");

setTimeout(() => {
  console.log("Timeout");
}, 0);

Promise.resolve().then(() => {
  console.log("Promise");
});

console.log("End");

// Output:
// Start → End → Promise → Timeout
```
➡️ Powered by:

Call stack
Callback queue
Microtask queue
🧩 4. Prototypal Inheritance
```
Objects inherit directly from other objects.
const animal = {
  eat() {
    console.log("eating");
  },
};

const dog = Object.create(animal);
dog.bark = function () {
  console.log("barking");
};

dog.eat();  // eating
dog.bark(); // barking
```
➡️ Classes are just syntactic sugar

⚡ 5. Dynamic Typing & Coercion

Flexible—but can be tricky.
```
console.log([] + {}); // "[object Object]"
console.log("5" - 2); // 3
console.log("5" + 2); // "52"
```
➡️ Understand coercion to avoid bugs

🧠 6. Almost Everything is an Object
```
function fn() {}
console.log(typeof fn); // "function"

const arr = [1, 2, 3];
console.log(typeof arr); // "object"

const num = 42;
console.log(num.toFixed(2)); // "42.00"
```
➡️ Even primitives behave like objects via wrappers

💡 What Most Developers Miss

JavaScript rewards understanding…
and punishes assumptions

🚀 The Real Shift

Beginner:
I know JavaScript syntax

Advanced:
I understand how JavaScript behaves

🔥 Final Thought

Once you understand this:

You stop debugging blindly
You start predicting outcomes

💬 Connect

If this helped you, give it a ⭐ and share your thoughts!

🏷️ Tags

javascript webdev frontend programming async closures eventloop cleancode
