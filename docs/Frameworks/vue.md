## Rough outline
Refine later. Capturing some possible concepts.

## Instantiating a Vue App
``` javascript
const app = Vue.createApp({
    data() {
        return {
        message: 'Hello Vue!'
        }
    },
    methods: {
        reverseMessage() {
        this.message = this.message
            .split('')
            .reverse()
            .join('')
        }
    
})
```
The createApp method takes an object as an argument where it contains the data and methods for the Vue app.

### Configuration Options
#### data
#### methods
#### computed
#### watch

## Interpolation

## Binding Attributes

## Working with data
### Outputting HTML instead of text

## Working with functions
### Referencing data in functions
### Functions and DOM Effect
Vue will automatically update the DOM when your data changes, but if you are using functions within your interpolations like ` {{ foo() }}`, then those functions are always reevaluated any time Vue updates the DOM. This is because the data could be potentially have been updated and now the function needs to be reevaluated.

We can use computed properties to cache the result of a function and only reevaluate it when the data it depends on changes. We can get better performance in general from using computed properties.

## Declarative vs Imperative

## Event Object
### Event Modifiers


## Directives
Directives are Vue-specific HTML tag attributes. You can add them to an element to apply special behavior to it.
### v-once
### v-on
Used to listen to events. Can also connect to specific versions of the events by using modifiers like `v-on.keydown.enter` or `v-on.click.right`.

There is a shorthand for v-on: `@`. So `v-on:click` can be written as `@click`.
### v-model
This is a shorthand directive which manages two-way binding on an element so that you can bind a data property and update it when the element changes. It is a combination of `v-bind` and `v-on`.

Instead of:
```html
<input v-bind:value="message" v-on:input="message = $event.target.value">
```
We can do:
```html
<input v-model="message">
```

### v-bind
Connects to a data property to a DOM attribute.

There is a shorthand for v-bind: `:`. So `v-bind:href` can be written as `:href`.

### v-text
Connects a data property to the inner text of an element. It is similar to `{{ }}` but it is more explicit.

## Styling and Classes
Bind a data property to a style with.
```javascript
:style="{ color: textColor }"
```

Bind a data property to a class by v-binding to the class attribute and giving it an object, array, or string.
```javascript
:class="{ active: isActive }"
:class="[activeClass, errorClass]"
:class="{ isSelected ? 'selected' : '' }"
```

## Common Mistakes
Forgetting to mount the app to an element in the DOM.

## Errors
