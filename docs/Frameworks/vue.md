## Rough outline

Refine later. Capturing some possible concepts.

## ROUGH IDEAS
ref attribute: can be added to html elements to reference them in the DOM. We can use these references to access the element in the Vue instance as `this.$refs.refName`.

virtual dom: Vue needs to know when to update the DOM, but reading the whole DOM is expensive. A virtual DOM is maintained by Vue and we compare to an old version of the virtual DOM to see what has changed. Then if differences are detected we update the parts in the real DOM where the change occurred.

vue lifecycle hooks

```mermaid
graph TD
    A[createApp({ ... })] --> B[beforeCreate()]
    B --> C[created()]
    C --> D[beforeMount()]
    D --> E[mounted()]
    C --> F[Compile template]
    F --> D
    E --> G[Mounted Vue Instance]
```

```mermaid
graph TD
    A[Mounted Vue Instance] --> B[Data Changed]
    B --> C[beforeUpdate()]
    C --> D[updated()]
```

```mermaid
graph TD
    A[Mounted Vue Instance] --> B[beforeUnmount()]
    B --> C[unmounted()]
    C --> D[Instance Unmounted]
```


## Instantiating a Vue App

```javascript
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

Computed properties can be helpful to limit the amount of logic that is used in our HTML code.<

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

#### stop

Prevents click propagation.

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
<input v-bind:value="message" v-on:input="message = $event.target.value" />
```

We can do:

```html
<input v-model="message" />
```

### v-bind

Connects to a data property to a DOM attribute.

There is a shorthand for v-bind: `:`. So `v-bind:href` can be written as `:href`.

### v-text

Connects a data property to the inner text of an element. It is similar to `{{ }}` but it is more explicit.

### v-if

### v-else

Has to be used on a direct neighbour of an element that uses the v-if/v-elseif directive.

### v-elseif

Has to be used on a direct neighbour of an element that uses the v-if directive.

### v-show

Similar to v-if but without the benefit of v-else, v-elseif. This directive hides the element from the DOM versus v-if which has the element not attached to the DOM. Might want to use if you have an element that switches its visibility a lot.

### v-for

Looping over array

Looping over object

Looping over range

#### Use of key

Vue reuses DOM elements when re-rendering to optimize performance. This can cause unexpected behaviour when adding/removing your data. You should use the key attribute to give a unique value to the element so that Vue knows to keep them separate.

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

### Single Curlies {} or Double Curlies {{}}

## Under the hood

### Element reuse

## Errors
