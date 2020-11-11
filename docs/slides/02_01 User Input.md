<!-- .slide: data-state="layout-title" class="bg-dark"-->

# User Input

<div class="slide-link"><a href="https://go.raybo.org/2CxS"><i class="fab fa-slideshare"></i> go.raybo.org/2CxS</a></div>

> >

One of the features that makes Vue.js super helpful is how it handles user input an to do that, we use a directive called v-model.

---

<!-- .slide: data-state="code-groups"-->

# **v-model** Directive

Update data on user input

<code class="code-primary">input</code> <code class="code-primary">textarea</code> <code class="code-primary">select</code>

- Two-way data binding
- Might ignore `value`, `checked` or `selected`
- Emits `value` `input` `checked` `change`

<a class="tip" href="https://go.raybo.org/2Csi" target="_blank"><code class="code-exciting">Try it</code><span>go.raybo.org/2Csi</span></a>

> >

The v-model directive lets you update your data based on changes made to different form elements.

It creates a relationship called two-way data binding. That means that when you modify a form element, it will also update data in your app. If for some reason the data changes the form will update as well.

v-model ignores sometimes ignores values on input fields. However, they might be useful when working with multiple checked or selected properties on form elements.

It will also generate properties and events when things change depending on the type of form. So checkboxes.

---

# Modifiers

Change how `v-model` works

<code class="code-primary">v-model.lazy</code> <code class="code-primary">v-model.number</code> <code class="code-primary">v-model.trim</code>

> >

There are several modifiers you can add to the `v-model` directive by adding a period and then an identifier.

The options are `.lazy` if you want the field to update after a change event instead of an input event. That means that for a text input field, you'd have to press tab or return in order for the variable to update.

Text fields are assummed to be strings by default. If you're sure you want a number, you can use the `.number` modifier.

`.trim` will get rid of any extra whitespace the user enters.

---

# Binding in **textarea**

Expressions don't work inside `<textarea>`

```
<textarea>{{ myVar }}</textarea>
```

```html
<textarea v-model="myVar"></textarea>
```

> >

Using expressions to output the value of a variable used for textarea won't work, you'll need to use v-model inside the textarea element instead.

---

# Binding to **checkboxes**

Boolean for single, array for multiple

```html
<input type="checkbox" v-model="myVar" 
  true-value="myValOne" false-value="myValTwo" />
```

```html
<input type="checkbox" value="first" v-model="myArray" />
<input type="checkbox" value="second" v-model="myArray" />
<input type="checkbox" value="third" v-model="myArray" />
```

```js
myArray : [];
```

> >

Here are some of the options you can use for working with checkboxes. First, if the variable is a boolean, it can turn the checkbox on and off depending on wether it has a true or false value.

You can also pass a  value using a `true-value` and `false-value` attribute with checkboxes, but be careful because a default uncheched checkbox won't have a value at all. If you require a default value, then use a radio button instead.

If you want to create more than one checkbox, you can give each input field a value. The values will be added or deleted from the array as you click on each checkbox.

---

# Binding to **radio**

Same variable name, different values

```html
<input type="radio" v-model="myVar" value="first" />
<input type="radio" v-model="myVar" value="second" />
<input type="radio" v-model="myVar" value="third" />
```
<a class="tip" href="https://go.raybo.org/2CtF" target="_blank"><code class="code-exciting">Try it</code><span>go.raybo.org/2CtF</span></a>

> >

Radio buttons are similar to checkboxes in that you use the same variable name, but you don't use an array and a single value will be captured, so use a variable instead of an array.



---

# Choosing with **select**

`v-model` in `<select>`, smart options

```html
<select v-model="myVar">
  <option value="">Choose...</option>
  <option>first</option>
  <option value="Option 2">second</option>
  <option>third</option>
</select>
```
<a class="tip" href="https://go.raybo.org/2Cw4" target="_blank"><code class="code-exciting">Try it</code><span>go.raybo.org/2Cw4</span></a> <a class="tip" href="https://go.raybo.org/2Csa" target="_blank"><code class="code-royal">Docs</code><span>go.raybo.org/2Csa</span></a> 

> >

If you want to use a select field, put the `v-model` directive in the `select` field. The variable you place there will receive a value based on the options selected.

If you include a value, that will be sent to the variable, otherwise, it will try to send what's in between the currently selected option.

You can include an empty value and add the **disabled** option to the `<option>` tag if you want to have a label with no value, which is especially important in iOS.

You can also use an array instead of a regular variable as well as the `multiple` option for the `select` if you want users to pick multiple options. The options picked will get stored in the array.

You can even generate the options dyamically through data, which is pretty awesome. All these options are worth a look. 



---

<!-- .slide: data-state="layout-title" data-transition="zoom" class="bg-dark"-->

# Practice

<div class="btn-group mt-3" role="group" aria-label="Basic example">
  <a type="button" class="animate__animated animate__backInLeft tip btn btn-lg btn-exciting text-white" href="https://go.raybo.org/2Csb" target="_blank">Problem<span>go.raybo.org/2Csb</span></a>
  <a type="button" class="animate__animated animate__zoomInDown tip btn btn-lg btn-royal text-white" href="https://go.raybo.org/2Ct2" target="_blank">Diff<span>go.raybo.org/2Ct2</span></a>
  <a type="button" class="animate__animated animate__backInRight animate__slow tip btn btn-lg btn-primary text-white" href="https://go.raybo.org/2Csc" target="_blank">Solution<span>go.raybo.org/2Csc</span></a>
</div>

1. Use `v-model` to control max price
1. Add a `.number` filter
1. Create a `displayLabels` boolean
1. Use a `checkbox` to toggle value
1. Modify code to show/hide labels

> >

Here's a good practice project. Here's the link to the starting code.
I've added some form elements using the bootstrap framework to help you control the pricing.

First, add a v-model to the text input field to show or change the maximum price variable.

Try using the number filter to make sure that the value casts to a number (try typing characters with the numbers)

Add a displayLabels boolean to the data

Now use a checkbox to toggle the value of this variable.

Modify the code so that the checkbox shows or hides the labels (be careful with the v-else statement)