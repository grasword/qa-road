# Interview questions

### 1) What is the difference between a statement and an expression in JS?&#x20;

Javascript program consists of statements. They are executed one by one, in the same order as they are written. Statements can contain other constructions like expressions, keywords, operators, and other stuff.

For example this is **statements**:

```javascript
let declaredVariable; // variable declaration is a statement
let otherVariable = 0; // even with assignment
function functionCall() { // function declaration is a statement
}
if(true){} // if is statement
2+2; // even this is statement
// Even though it consists from only one expression
```

**Expressions** are parts of statements that return values. So expressions can be used whenever value is expected.

And this is expressions:&#x20;

```javascript
2+2
true
true && false
functionCall() // whatever the function returns
declaredVariable // whatever the variable value was
declaredVariable = 'new value' // assignment is an expression
```

Actually just `"foo"`, `{foo: 'bar'}`, `[1,2,3]`, or `42` are also expressions, they are called `literals` (string, object, array and number literal) because they just return their literal value.

And even this small expressions can be statements on their own.

```javascript
2;
```

This is statement. It’s useless. It doesn’t help, but still. As you can see it consists from only one expression. Statements like this are called `expression statements`.

Sometimes you can use `expression-statements` instead of usual statements, `if-else` is a good example:

```javascript
let foo;
if (bar === 'bazz') {
  foo = bar;
} else {
  foo = null;
}
```

You can use this `expression` instead:

```javascript
let foo = bar === 'bazz' ? bar : null
```

Source: [https://maksimivanov.com/posts/statements-expressions-js/](https://maksimivanov.com/posts/statements-expressions-js/)

### 2) What’s the difference between JavaScript primitive values and objects?&#x20;

JavaScript currently supports eight data types. All of these data types (`Booleans`, `Null`, `Undefined`, `Number`, `BigInt`, `String`, `Symbol`) are **primitive values** except for **object references**.

`Arrays`, `functions`, `NaN`, and `dates` all play an important role in JavaScript programs, but they are really just objects under the hood.

Primitive values can be stored in variables directly. Objects, on the other hand, are stored as references. A variable that has been assigned an object does not store that object directly, it stores the memory address of the location that the object exists at.

#### The Difference Between a Value and a Reference <a href="#f877" id="f877"></a>

Primitive values and object references are stored in JavaScript programs in different ways.

When a primitive value is assigned to a variable (eg `let foo = ‘bar’`), the variable is set to that **value** directly.

When the variable is assigned with an object, however, things are different. Instead of containing the value directly, that variable contains a **reference** to it.

#### The Difference Between Immutable and Mutable Data <a href="#dcb9" id="dcb9"></a>

One key difference between primitive values and object references is **mutability**. Primitive values are **immutable** and object references are **mutable**.

The reason primitive types are immutable is that primitives have no methods attached, which means there is no possible way to mutate the string in the first place. A primitive has a value and no properties.

// Source: [https://betterprogramming.pub/intermediate-javascript-whats-the-difference-between-primitive-values-and-object-references-e863d70677b](https://betterprogramming.pub/intermediate-javascript-whats-the-difference-between-primitive-values-and-object-references-e863d70677b)

### 3) What do people mean when they say “everything” is an object in JS?&#x20;

The answer is a little bit of JavaScript magic involving wrapper-objects and autoboxing. When a method like `string.length` is called on a primitive type like a string, JavaScript initiates an action called _autoboxing_.

Autoboxing is the process by which JavaScript wraps a primitive in an object, but only temporarily.

`String` is a global function that creates a primitive string when passed in an argument, but you can also use the `String` function as a constructor function. And this will create a new object (often referred to as _wrapper object_) representing the string `"dog"`, with the following properties:

```
const pet = new String("dog"){  0: "d",  1: "o",  2: "g",  length: 3 }
```

When `.length` is called on a primitive string, the JavaScript engine converts the string to a `String` object as shown above. It is then mutable, and you gain access to the many built-in methods attached to `String`. Once the method has been resolved, the above wrapper object is discarded. The same applies to numbers and Booleans (it does not apply to null and undefined).

Here’s a breakdown of the work JavaScript does under the hood:

1. Create a `String` wrapper object, equivalent to using `new String()`.
2. Call the inherited `.length` method on the `String` wrapper object.
3. Once the method is complete, the wrapper `String` object is discarded.
4. Return the mutated primitive string (if a method like `substr( )` is used).

#### Is Everything in JavaScript an Object? <a href="#78d8" id="78d8"></a>

Not quite. It might be more accurate to say something along the lines of everything in JavaScript can appear to behave like an object_._ Primitives like `String`, `boolean`, and `number` can behave like objects thanks to JavaScript features called object-wrapping and autoboxing.

// Source: [https://betterprogramming.pub/everything-in-javascript-is-an-object-except-for-when-it-isnt-305bc65a3410](https://betterprogramming.pub/everything-in-javascript-is-an-object-except-for-when-it-isnt-305bc65a3410)

### 4) What is not an object in JS?&#x20;

**Primitive values** are not objects(`Booleans`, `Null`, `Undefined`, `Number`, `BigInt`, `String`, `Symbol`)  &#x20;

### 5) In what ways are primitive values objects or not?&#x20;

Primitives like `String`, `boolean`, and `number` can behave like objects thanks to JavaScript features called object-wrapping and autoboxing.

### 6) How is a function an object? What about an array? What are the exact definitions of a variable, a declaration, and an assignment?

#### How is a function an object?&#x20;

In JavaScript, functions are first-class objects, because they can have properties and methods just like any other object. What distinguishes them from other objects is that functions can be called. In brief, they are [`Function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Function) objects.

// Source: [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions)

#### What about an array?

The JavaScript **`Array`** class is a global object that is used in the construction of arrays; which are high-level, list-like objects.

// Source: [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global\_Objects/Array)

#### What are the exact definitions of a variable?

Variable - In computer programming, a **variable** or **scalar** is an abstract storage location paired with an associated symbolic name, which contains some known or unknown quantity of information referred to as a _value_; or in simpler terms, a variable is a container for a particular set of bits or type of data (like integer, float, String etc...). A variable can eventually be associated with or identified by a memory address. The variable name is the usual way to reference the stored value, in addition to referring to the variable itself, depending on the context. This separation of name and content allows the name to be used independently of the exact information it represents. The identifier in computer source code can be bound to a value during run time, and the value of the variable may thus change during the course of program execution.\
// Source: [https://en.wikipedia.org/wiki/Variable\_(computer\_science)](https://en.wikipedia.org/wiki/Variable\_\(computer\_science\))

#### What are the exact definitions of a declaration?

In computer programming, a **declaration** is a language construct that specifies properties of an identifier: it declares what a word (identifier) "means". Declarations are most commonly used for functions, variables, constants, and classes, but can also be used for other entities such as enumerations and type definitions. Beyond the name (the identifier itself) and the kind of entity (function, variable, etc.), declarations typically specify the data type (for variables and constants), or the type signature (for functions); types may also include dimensions, such as for arrays. A declaration is used to announce the existence of the entity to the compiler; this is important in those strongly typed languages that require functions, variables, and constants, and their types to be specified with a declaration before use, and is used in forward declaration.

// Source:  [https://en.wikipedia.org/wiki/Declaration\_(computer\_programming)](https://en.wikipedia.org/wiki/Declaration\_\(computer\_programming\))

#### What are the exact definitions of a an assignment?

The simple assignment operator (`=`) is used to assign a value to a variable. The assignment operation evaluates to the assigned value.

// Source: [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Assignment](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Assignment)

### 7) What is control flow?&#x20;

The _control flow_ is the order in which the computer executes statements in a script.

Code is run in order from the first line in the file to the last line, unless the computer runs across the (extremely frequent) structures that change the control flow, such as conditionals and loops.

Source: [https://developer.mozilla.org/en-US/docs/Glossary/Control\_flow](https://developer.mozilla.org/en-US/docs/Glossary/Control\_flow)

### 9) What is the difference between `===` and `==`?

The loose equality operator (`==`) will return `true` if the values of the two items being compared are the same. The strict equality operator (`===`) returns `true` if the values **and** types of the two objects being compared are the same.
