# 🧠 Call by Value vs Call by Reference

## 🚨 Key Truth

👉 Java, JavaScript, Python (and many modern languages) are **NOT call by reference**  
👉 They are **Call by Value**

---

## 🧠 Why the Confusion?

When we pass objects to functions:

- Changes sometimes reflect outside the function  
- This *feels like* call by reference  

❌ But internally, it's still **value copying**

---

## ⚙️ Core Concept

- Every variable stores a **value**
- For primitives → actual data  
- For objects → **memory address (reference)**  

👉 During function call → **copy of that value is passed**

---

## ⚙️ Algorithm (What Happens Internally)

1. Variable is created and stores a value  
2. Function is called  
3. A new **stack frame** is created  
4. Parameters receive **copy of argument values**  
5. Function operates on copied values  
6. Stack frame is destroyed after execution  

---

## 🔍 Behavior Explained

### ✅ Case 1: Mutation (Works)

```text
obj.name = "Ishwar"
