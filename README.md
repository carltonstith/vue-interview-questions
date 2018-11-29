# vuejs-interview-questions
List of VueJS Interview Questions

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
 1. **beforeCreate:** This is called synchronously after the Vue instance has been initialized.
 2. **created:** This is called synchronosly after the Vue instance is created.
 3. **beforeMount:** This is called right before the component is mounted.
 4. **mounted:** This is called after the component has just been mounted.
 5. **beforeUpdated:** This is called when the data changes, before the virtual DOM is re-rendered.
 6. **updated:** This is called after a data change.
 7. **activated:** This is called when a keep/kept alive component is activated.
 8. **deactivated:** This is called when a keep/kept alive component is deactivated.
 9. **beforeDestroy:** This is called right before a Vue instance is instantiated.
 10. **destroyed:** This is called after a Vue instance has been destroyed.

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




