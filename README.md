# vuejs-interview-questions
A list of interview questions for front-end developers. The questions are focused on Vue.js and vanilla JavaScript.

> Click :star:if you like the project. Pull Requests are highly appreciated.

### Table of Contents
-------------------------------------------------------------------
| No. | Questions                                                                                                                                                    |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 1   | [What is VueJS?](#what-is-vuejs)                                                                                                                             |
| 2   | [What are the major features of VueJS?](#what-are-the-major-features-of-vuejs)                                                                               |
| 3   | [What are the lifecycle methods of VueJS?](#what-are-the-lifecycle-methods-of-vuejs)                                                                         |
| 4   | [What are the conditional directives?](#what-are-the-conditional-directives)                                                                                 |
| 5   | [What is the difference between v-show and v-if directives?](#what-is-the-difference-between-v-show-and-v-if-directives)                                     |
| 6   | [What is the purpose of v-for directive?](#what-is-the-purpose-of-v-for-directive)                                                                           |
| 7   | [What is the purpose of v-for directive?](#what-is-the-purpose-of-v-for-directive)                                                                           |
| 8   | [What is a vue instance?](#what-is-the-vue-instance)                                                                                                         |
| 9   | [What are the differences between one-way data flow and two-way data binding?](#what-are-the-differences-between-one-way-data-flow-and-two-way-data-binding) |
| 10  | [What are Components?](#what-are-components)                                                                                                                 |
| 11  | [What are some advantages and disadvantages of Vue?](#what-are-some-advantages-and-disadvantages-of-vue)                                                     |
| 12  | [What is the vue-cli?](#what-is-the-vue-cli)
| 13  | [On what design pattern is Vue based on?](#on-what-design-pattern-is-vue-based-on)
| 14  | [What is Vuex?](#what-is-vuex)
| 15  | [What is the difference between `undefined` and `not defined` in JavaScript?](#what-is-the-difference-between-undefined-and-not-defined-in-javascript)
| 16  | [How do you empty an array in JavaScript?](#how-do-you-empty-an-array-in-javascript)
| 17  | [What is the difference between declaring a function in the formats listed?](#what-is-the-difference-between-declaring-a-function-in-the-formats-listed)
| 18  | [What are Service Workers and when can you use them?](#what-are-service-workers-and-when-can-you-use-them)
| 19  | [What is the difference between a method and a function in javascript?](#what-is-the-difference-between-a-method-and-a-function-in-javascript)
| 20  | [What is IIFE (Immediately Invoked Function Expression) and how it can be useful?](#what-is-IIFE-(immediately-invoked-function-expression)-and-how-it-can-be-useful?)
| 21  | [What are the ways of creating objects in JavaScript?](#what-are-the-ways-of-creating-objects-in-javaScript)

### What is VueJS?
Vue.js is an open-source, progressive Javascript framework for building user interfaces that aim to be incrementally adoptable. The core library of VueJS is focused on the view layer only, and is easy to pick up and integrate with other libraries or existing projects. The most recent version of Vue.js as of November 2018 is version 2.
### What are the major features of VueJS?
Below are the some of major features available with VueJS
 1. **Virtual DOM:** It uses virtual DOM similar to other existing frameworks such as ReactJS, Ember etc. Virtual DOM is a light-weight in-memory tree representation of the original HTML DOM and updated without affecting the original DOM.
 2. **Components:** Used to create reusable custom elements in VueJS applications.
 3. **Templates:** VueJS provides HTML based templates that bind the DOM with the Vue instance data
 4. **Routing:** Navigation between pages is achieved through vue-router
 5. **Light weight:** Vue is a light-weight library compared to other frameworks
 6. **Transitions:**
 7. **Reactivity:**
### What are the lifecycle hooks or methods in VueJS?
 1. **beforeCreate:** This is called synchronously after the Vue instance has been initialized. The beforeCreate hook runs at the very initialization of your component. data has not been made reactive, and events have not been set up yet.
 2. **created:** This is called synchronosly after the Vue instance is created. In the created hook, you will be able to access reactive data and events are active. Templates and Virtual DOM have not yet been mounted or rendered.
 3. **beforeMount:** This is called right before the component is mounted. This hook runs right before the initial render happens and after the template or render functions have been compiled. Most likely you'll never need to use this hook. This doesn't get called when doing server-side rendering.
 4. **mounted:** This is called after the component has just been mounted. You will have full access to the reactive component, templates, and rendered DOM (via this.$el). Mounted is the most-often used lifecycle hook. The most frequentl used patterns are fetching data for your componen (use created for this instead) and modifying the DOM, ofter to integrate non-Vue libraries.
 5. **beforeUpdated:** This is called when the data changes, before the virtual DOM is re-rendered. This hook runs after data changes on your component and the update cycle begins, right before the DOM is patched and re-rendered. It allows you to get the new state of any reactive data on your component before it actually get rendered.
 6. **updated:** This is called after data changes on your component and the DOM re-renders. If you need to access the DOM after a property change, here is probably the safest place to do it.
 7. **activated:** This is called when a keep/kept alive component is activated.
 8. **deactivated:** This is called when a keep/kept alive component is deactivated.
 9. **beforeDestroy:** This is called right before a Vue instance is torn down. Your component will still be fully present and functional. If you need to cleanup events or reactive subscriptions, beforeDestroy would probably be the time to do it.
 10. **destroyed:** This is called after a Vue instance has been destroyed and there's pretty much nothing left on your component. Everything that was attached to it has been destroyed. You might use the destroyed hook to do any last-minute cleanup or to inform a remote server that the component was destroyed. 

### What are the conditional directives?
VueJS provides set of directives to show or hide elements based on conditions. The available directives are: ** v-if, v-else, v-else-if and v-show**
**1. v-if:**  The v-if directive adds or removes DOM elements based on the given expression. For example, the below button will not show if isLoggedIn is set to false.
```javascript
<button v-if="isLoggedIn">Logout</button>
```
You can also control multiple elements with a single v-if statement by wrapping all the elements in a <template> element with the condition. For example, you can have both label and button together conditionally applied,
```javascript
<template v-if="isLoggedIn">
  <label> Logout </button>
  <button> Logout </button>
</template>
```
**2. v-else:**  This directive is used to display content only when the expression adjacent v-if resolves to false. This is similar to else block in any programming language to display alternative content and it is preceded by v-if or v-else-if block. You don't need to pass any value to this.
For example, v-else is used to display LogIn button if isLoggedIn(not logged in) is set to false.
```javascript
<button v-if="isLoggedIn"> Logout </button>
<button v-else> Log In </button>
```
**3. v-else-f:** This directive is used when we need more than two options to be checked.
For example, ifLoginDisabled property is disabled then we need to prevent user to login instead just display the label. This can be achieved through v-else statement.
```javascript
<button v-if="isLoggedIn"> Logout </button>
<label v-else-if="isLoginDisabled"> User login disabled </label>
<button v-else> Log In </button>
```

**4. v-show:** This directive is similar to v-if but it renders all elements to the DOM and then uses the CSS display property to show/hide elements. This directive is recommended if the elements are switched on and off frequently.
```javascript
<span if-show="user.name">Welcome user,{{user.name}}</span>
```
### What is the difference between v-show and v-if directives?
Below are some of the main differences between between **v-show** and **v-if** directives,
1. v-if only renders the element to the DOM if the expression passes whereas v-show renders all elements to the DOM and then uses the CSS display property to show/hide elements based on expression.
2. v-if supports v-else and v-else-if directives whereas v-show doesn't support else directives.
3. v-if has higher toggle costs while v-show has higher initial render costs. i.e, v-show has a performance advantage if the elements are switched on and off frequently, while the v-if has the advantage when it comes to initial render time.
### What is the purpose of v-for directive?
The built-in v-for directive allows us to loop through items in an array or object.
### What is the vue instance?
    Every Vue application works by creating a new Vue instance with the Vue function. Generally the variable vm (short for ViewModel) is used to refer Vue instance. You can create vue instance as below,
    ```javascript
    var vm = new Vue({
      // options
    })
    ```
    As mentioned in the above code snippets, you need to pass options object. You can find the full list of options in the API reference.
### What are the differences between one-way data flow and two-way data binding?
In one-way data flow the view (UI) part of an application does not update automatically when the data Model is changed so we need to write some custom code to make it update every time a data model is changed. In Vue.js, the v-bind is used for one-way data flow or binding.

In two-way data binding, the view (UI) part of the application automatically updates when the data Model is changed. In Vue.js, the v-model directive is used for two-way data binding.
### What are components?
Components are one of the most powerful features in Vue.js. In Vue, components are custom elements that help extend basic HTML elements to encapsulate reusable code.
The following is the way to register a Vue component inside another component:
```javascript
export default {
  el:'#your-element',
  components: {
    'your-component'
  }
}
```
### What are some advantages and disadvantages of Vue?
Advantages
1. Easy for applications and interface development
2. Support for two-way data binding similar to Angular
3. Ability to controls states
4. Natural thought process
5. The framework is light
6. Minimal documentation
7. Easy to understand
Disadvantages
1. Limited scope
2. Single creator
3. Small developer community
### What is the vue-cli?
The vue-cli or command line interface is a program used to install Vue.js. Apart from this vue-cli, it also helps compile and build the projects.
### On what design pattern is Vue based on?
Vue.js is based on the Model-View-View Model (MVVM) design pattern. The main motivation for this pattern is a separation model from the view.
### What is Vuex?
Vuex is a state management pattern and library for Vue.js apps. It is designed to a main data storage for all app components and guarantee predictability of reactive data changes.
### What is the difference between `undefined` and `not defined` in JavaScript?
In JavaScript if you try to use a variable that doesn't exist and has not been declared, then JavaScript will throw an error `var name is not defined` and the script will stop executing thereafter. But If you use `typeof undeclared_variable` then it will return `undefined`.

Before starting further discussion let's understand the difference between declaration and definition.

`var x` is a declaration because you are not defining what value it holds yet, but you are declaring its existence and the need for memory allocation.

```javascript
var x; // declaring x
console.log(x); // output: undefined
```

`var x = 1` is both declaration and definition (also we can say we are doing initialisation), Here declaration and assignment of value happen inline for variable x, In JavaScript every variable declaration and function declaration brings to the top of its current scope in which it's declared then assignment happen in order this term is called `hoisting`.

A variable can be declared but not defined. When we try to access it, It will result `undefined`.

```javascript
var x; // Declaration
typeof x === 'undefined'; // Will return true
```

A variable can be neither declared nor defined. When we try to reference such variable then the result will be `not defined`.

```javascript
console.log(y);  // Output: ReferenceError: y is not defined
```

### Ref Link:
[http://stackoverflow.com/questions/20822022/javascript-variable-definition-declaration](http://stackoverflow.com/questions/20822022/javascript-variable-definition-declaration)
### How do you empty an array in JavaScript?
For instance, say we have:

```javascript
var arrayList =  ['a', 'b', 'c', 'd', 'e', 'f'];
```

How can we empty the array above?

There are a couple of ways by which we can empty an array, So let's discuss all the possible way by which we can empty an array.

#### Method 1

```javascript
arrayList = [];
```

The code above will set the variable `arrayList` to a new empty array. This is recommended if you don't have **references to the original array** `arrayList` anywhere else because It will actually create a new empty array. You should be careful with this way of empty the array, because if you have referenced this array from another variable, then the original reference array will remain unchanged, Only use this way if you have only referenced the array by its original variable `arrayList`.

For instance:

```javascript
var arrayList = ['a', 'b', 'c', 'd', 'e', 'f']; // Created array
var anotherArrayList = arrayList;  // Referenced arrayList by another variable
arrayList = []; // Empty the array
console.log(anotherArrayList); // Output ['a', 'b', 'c', 'd', 'e', 'f']
```

#### Method 2

```javascript
arrayList.length = 0;
```

The code above will clear the existing array by setting its length to 0. This way of emptying an array will also update all the reference variables that point to the original array. 

For instance:

```javascript
var arrayList = ['a', 'b', 'c', 'd', 'e', 'f']; // Created array
var anotherArrayList = arrayList;  // Referenced arrayList by another variable
arrayList.length = 0; // Empty the array by setting length to 0
console.log(anotherArrayList); // Output []
```

#### Method 3

```javascript
arrayList.splice(0, arrayList.length);
```

Above implementation will also work perfectly. This way of empty the array will also update all the references of the original array.

```javascript
var arrayList = ['a', 'b', 'c', 'd', 'e', 'f']; // Created array
var anotherArrayList = arrayList;  // Referenced arrayList by another variable
arrayList.splice(0, arrayList.length); // Empty the array by setting length to 0
console.log(anotherArrayList); // Output []
```

#### Method 4

```javascript
while(arrayList.length) {
  arrayList.pop();
}
```

Above implementation can also empty the array. But not recommended to use often.
### What is the difference between declaring a function in the formats listed?
```javascript
var foo = function() {
  // Some code
}
```

```javascript
function bar () {
  // Some code
}
```

The main difference is function `foo` is defined at `run-time` and is called function expression, whereas function `bar` is defined at parse time and is called function statement. To understand in better, let's see below code :

```javascript
// Run-Time function declaration
  foo(); // Call foo function here, It will give an error
  var foo = function() {
    console.log("Hi I am inside Foo");
  };
```

```javascript
// Parse-Time function declaration
bar(); // Call bar function here, It will not give an Error
function bar() {
  console.log("Hi I am inside Foo");
}
```

### What are Service Workers and when can you use them?
It’s a technology that allows your web application to use cached resources first, and provide default experience offline, before getting more data from the network later. This principle is commonly known as Offline First.

Service Workers actively use promises. A Service Worker has to be installed,activated and then it can react on fetch, push and sync events.

As of 2017, Service Workers are not supported in IE and Safari.

### What is the difference between a method and a function in javascript?
In JS, that difference is quite subtle. A function is a piece of code that is called by name and function itself not associated with any object and not defined inside any object. It can be passed data to operate on (i.e. parameter) and can optionally return data (the return value).

```javascript
// Function statement
function myFunc() {
  // Do some stuff;
}

// Calling the function
myFunc();
```

Here myFunc() function call is not associated with object hence not invoked through any object.

A function can take a form of immediately invoked function expression (IIFE):

```javascript

// Anonymous Self-invoking Function
(function() {
  // Do some stuff;
})();
```

Finally there are also arrow functions: 

```javascript
const myFunc = arg => {
    console.log("hello", arg)
} 
```

A method is a piece of code that is called by its name and that is associated with the object. Methods are functions. When you call a method like this `obj1.myMethod()`, the reference to `obj1` gets assigned (bound) to `this` variable. In other words, the value of `this` will be `obj1` inside `myMethod`. 

Here are some examples of methods: 

##### Example 1
```javascript
var obj1 = {
  attribute: "xyz",
  myMethod: function () {  // Method
    console.log(this.attribute);
  }
};

// Call the method
obj1.myMethod();
```

Here `obj1` is an object and `myMethod` is a method which is associated with `obj1`.

##### Example 2
In ES6 we have classes. There the methods will look like this:

```javascript
class MyAwesomeClass {
  myMethod() {
    console.log("hi there");
  }
}

const obj1 = new MyAwesomeClass();
obj1.myMethod();
```

Understand: the method is not some kind of special type of a function, and it's not about how you declare a function. It's the way we **call** a function. Look at that: 

```javascript
var obj1 = {
  prop1: "buddy"
}; 
var myFunc = function () {
  console.log("Hi there", this);
};
// let's call myFunc as a function: 
myFunc(); // will output "Hi there undefined" or "Hi there Window"
 
obj1.myMethod = myFunc;
//now we're calling myFunc as a method of obj1, so this will point to obj1
obj1.myMethod(); // will print "Hi there" following with obj1. 

```
### What is IIFE (Immediately Invoked Function Expression) and how it can be useful?
#### Definition
IIFE a function that runs as soon as it's defined. Usually it's anonymous (doesn't have a function name), but it also can be named. Here's an example of IIFE:

```javascript
(function() {
  console.log("Hi, I'm IIFE!");
})();
// outputs "Hi, I'm IIFE!"
```
#### Explanation

So, here's how it works. Remember the difference between function statements (`function a () {}`) and function expressions (`var a = function() {}`)? So, IIFE is a function expression. To make it an expression we surround our function declaration into the parens. We do it to explicitly tell the parser that it's an expression, not a statement (JS doesn't allow statements in parens).

After the function you can see the two `()` braces, this is how we run the function we just declared. 

That's it. The rest is details.  
- The function inside IIFE doesn't have to be anonymous. This one will work perfectly fine and will help to detect your function in a stacktrace during debugging: 
  ```javascript
  (function myIIFEFunc() {
    console.log("Hi, I'm IIFE!");
  })();
  // outputs "Hi, I'm IIFE!"
  ```
- It can take some parameters:
  ```javascript
  (function myIIFEFunc(param1) {
    console.log("Hi, I'm IIFE, " + param1);
  })("Yuri");
  // outputs "Hi, I'm IIFE, Yuri!"
  ```
  Here there value `"Yuri"` is passed to the `param1` of the function.
- It can return a value: 
  ```javascript
  var result = (function myIIFEFunc(param1) {
    console.log("Hi, I'm IIFE, " + param1);
    return 1;
  })("Yuri");
  // outputs "Hi, I'm IIFE, Yuri!"
  // result variable will contain 1
  ```
- You don't have to surround the function declaration into parens, although it's the most common way to define IIFE. Instead you can use any of the following forms: 
  - `~function(){console.log("hi I'm IIFE")}()`
  - `!function(){console.log("hi I'm IIFE")}()`
  - `+function(){console.log("hi I'm IIFE")}()`
  - `-function(){console.log("hi I'm IIFE")}()`
  - `(function(){console.log("hi I'm IIFE")}());`
  - `var i = function(){console.log("hi I'm IIFE")}();`
  - `true && function(){ console.log("hi I'm IIFE") }();`
  - `0, function(){ console.log("hi I'm IIFE") }();`
  - `new function(){ console.log("hi I'm IIFE") }`
  - `new function(){ console.log("hi I'm IIFE") }()`
  
  Please don't use all these forms to impress colleagues, but be prepared that you can encounter them in someone's code. 

#### Applications and usefulness

Variables and functions that you declare inside an IIFE are not visible to the outside world, so you can:
 - Use the IIFE for isolating parts of the code to hide details of implementation.
 - Specify the input interface of your code by passing commonly used global objects (window, document, jQuery, etc.) IIFE’s parameters, and then reference these global objects within the IIFE via a local scope.
 - Use it in closures, when you use closures in loops.
 - IIFE is the basis of in the module pattern in ES5
code, it helps to prevent polluting the global scope and provide the module interface to the outside.

### What are the ways of creating objects in JavaScript?
#### Method 1: Function based

This method is useful if we want to create several similar objects. In the code sample below, we wrote the function `Employee` and used it as a constructor by calling it with the `new` operator. 

```javascript

  function Employee(fName, lName, age, salary){
  	this.firstName = fName;
  	this.lastName = lName;
  	this.age = age;
  	this.salary = salary;
  }

  // Creating multiple object which have similar property but diff value assigned to object property.
  var employee1 = new Employee('John', 'Moto', 24, '5000$');
  var employee1 = new Employee('Ryan', 'Jor', 26, '3000$');
  var employee1 = new Employee('Andre', 'Salt', 26, '4000$');
```

#### Method 2: Object Literal

Object Literal is best way to create an object and this is used frequently. Below is code sample for create employee object which contains property as well as method.

```javascript
var employee = {
	name : 'Nishant',
	salary : 245678,
	getName : function(){
		return this.name;
	}
}
```
The code sample below is Nested Object Literal, Here address is an object inside employee object.

```javascript
var employee = {
	name : 'Nishant',
	salary : 245678,
	address : {
		addressLine1 : 'BITS Pilani',
		addressLine2 : 'Vidya Vihar'.
		phoneNumber: {
		  workPhone: 7098889765,
		  homePhone: 1234567898
		}
	}
}
```
#### Method 3: From `Object` using `new` keyword

In the code below, a sample object has been created using `Object`'s constructor function.

```javascript
var employee = new Object(); // Created employee object using new keywords and Object()
employee.name = 'Nishant';
employee.getName = function(){
	return this.name;
}
```

#### Method 4:** Using `Object.create`

`Object.create(obj)` will create a new object and set the `obj` as its prototype. It’s a modern way to create objects that inherit properties from other objects. `Object.create` function doesn’t run the constructor. You can use `Object.create(null)` when you don’t want your object to inherit the properties of `Object`.