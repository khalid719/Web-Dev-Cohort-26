---
title: "How JavaScript Works Internally"
datePublished: Sun Feb 08 2026 20:41:22 GMT+0000 (Coordinated Universal Time)
cuid: cmle7kk0n003002l713mebxrp
slug: how-javascript-works-internally
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1770583196450/a09b8717-a5c0-430d-a208-60197e74df03.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1770583263465/26f265d6-c848-4734-985d-20691d2d235b.png
tags: hiteshchoudharylco, chaicode, piyushgarag, chaicode-webdev-cohort-2026, khaliddev

---

## The JavaScript Engine

When you write JavaScript code, the **JavaScript Engine** (like V8 in Chrome) reads and executes it. The engine runs your code in **two phases**.

## Phase 1: Memory Creation Phase

Before executing anything, JavaScript scans your **entire code** and allocates memory for:

**Variables:** Get placeholder value `undefined` **Functions:** Get the entire function code stored

javascript

```javascript
var age = 25;
function greet() {
    var message = "Hello";
}
```

**Global Memory after Phase 1:**

* `age` → `undefined`
    
* `greet` → `{entire function code}`
    
* `message` → **Does NOT exist yet!**
    

Variables inside functions don't get memory until the function is called.

## Phase 2: Execution Phase

JavaScript now runs your code **line by line**:

* Assigns actual values to variables
    
* Executes functions when called
    
* Runs statements like `console.log()`
    

**Note:** `console.log()` statements don't get memory - they just execute and disappear. Only variables and functions need memory storage.

## Execution Context

Every time code runs, JavaScript creates an **Execution Context** - a container with two parts:

1. **Memory Component:** Stores variables and functions
    
2. **Code Component:** Executes code line by line
    

There are two types:

**Global Execution Context:** Created when program starts, holds global variables and functions

**Function Execution Context:** Created each time a function is called, has its own separate memory

javascript

```javascript
var globalVar = "I'm global";

function test() {
    var localVar = "I'm local";
}
```

* `globalVar` lives in **global memory**
    
* `localVar` lives in **function's memory** (created only when function is called)
    

## The Call Stack - The Manager

The **Call Stack** is NOT memory - it's a manager that tracks:

* What code is currently running
    
* What should run next
    
* The order of execution
    

Think of it like a stack of plates - you can only add or remove from the top.

javascript

```javascript
function first() {
    console.log("First");
}

function second() {
    first();
    console.log("Second");
}

second();
```

**Call Stack in action:**

1. `Global` execution context added
    
2. `second()` called → added on top
    
3. `first()` called inside `second()` → added on top
    
4. `first()` finishes → removed
    
5. `second()` finishes → removed
    
6. Program ends → stack empty
    

## Single-Threaded Nature

JavaScript has only **one thread** - one worker who can do only one task at a time. Everything happens sequentially, never simultaneously.

## Memory Lifecycle

**Function Memory:**

* Created when function is called
    
* Destroyed when function finishes
    
* Variables inside are gone forever after function completes
    

**Global Memory:**

* Created when program starts
    
* Destroyed when entire program ends
    
* Accessible throughout the program's lifetime
    

## Scope - Who Can Access What

**Global scope:** Variables in global memory can be accessed anywhere

**Function scope:** Variables in function memory can only be accessed inside that function

javascript

```javascript
var x = 10;  // Global - accessible everywhere

function test() {
    var y = 20;  // Local - only accessible inside test()
    console.log(x);  // ✓ Can access global
    console.log(y);  // ✓ Can access own
}

test();
console.log(x);  // ✓ Works
console.log(y);  // ✗ Error - y doesn't exist in global memory
```

Functions can see global variables, but global cannot see function variables.

## Key Takeaways

* JavaScript runs in two phases: Memory Creation, then Execution
    
* Functions get full code stored, variables get `undefined` initially
    
* Each function call creates its own execution context with separate memory
    
* Call Stack manages execution order (LIFO - Last In, First Out)
    
* JavaScript is single-threaded - one thing at a time
    
* Memory is destroyed: functions when they finish, global when program ends