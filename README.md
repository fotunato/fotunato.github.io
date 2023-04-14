# MY WIKI

# Forms

The form element is used to group related input through input fields, radio buttons etc

### Form attributes (global)

<u>accept-charset</u>

specifies accepted character encoding for the form
we can add multiple character encoding by adding a space between them

syntax:

```htm
<form charset="UTF-8">
</form>
```

(multiple encoding)

```htm
<form charset="UTF-8 UTF-32">
</form>
```

<u>autocomplete</u>

specifies if autocomplete is ‘on’ or ‘off’ for the form

```htm
<form autocomplete="on" | “off”>
</form>
```

<u>name</u>

specifies the name of the form
the name is submitted with the value to the server

```htm
<form name="name-of-form”>
</form>
```

<u>rel</u>

specifies the relationship between the form and the processing page it is submitting to

```htm
<form rel="noopener" | “nofollow” | “external”>
</form>
```

1. noopener

   The processing page cannot access the page which sent the data (the form’s webpage)

   Improves security by blocking malicious code which can be injected into the form’s webpage from the processing page

2. nofollow

   Search engines cannot follow the links in the form

   This stops the webpage from being indexed and published by search engines

3. external

   Processing page is hosted on a different domain than the form’s document.

   Improves security because the processing page requires a token to access the form’s document.

Find more rel values [here]([https://](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/rel#help))

### Attributes for form submission

These attributes directly affect form submission:

<u>action</u>

action specifies the URL which processes the form submission

```htm
<form action="url-which-processes-form-submission”>
</form>
```

*overridden by formaction*
<br>
<br>

<u>enctype</u>

enctype specifies the type of encoding in the form

```htm
<form enctype="application/x-www-form-urlencoded” | “multipart/form-data” | “text/plain”>
</form>
```

*overridden by formenctype*
<br>
<br>

 1. application/x-www-form-urlencoded

    this is the default enctype<br>
    name and value are separated by &

 2. multipart/form-data

    this is used when the form contains `<input>` elements which have file *attr* type

 3. text/plain

    this is used when security is not a concern like during debugging<br><br>

<u>method</u>

specifies the HTTP method to submit the form to the server

```htm
<form method="post” | “get”>
</form>
```

*overridden by formmethod*
<br>

1. post

    this is the most-used method<br>
    post is used to send data to the server<br>
    post updates the server<br>
    post is more secure because unlike get, post does not include the data in the URL

2. get

    this is used to retrieve data from the server<br>
    get does not update the server<br>
    get is not as secure as post because unlike post, get includes the data in the URL

```htm
<form novalidate>
</form>
```

*overridden by formnovalidate*

3. novalidate

    specifies that the form submission should not be validated<br><br>

<u>target</u>

target specifies where to display the response after submitting the form

```htm
<form target="_self” | "_blank” | "_parent” | "_top”>
</form>
```

*overridden by formtarget*

1. _self
    this loads the current browser document after submission<br>
    this is *default*

2. _blank
    this loads a new browser document after submission<br>

3. _parent
    this loads the parent browsing context of the current browser document after submission<br>
if there is no parent, the browser loads the current browser document as_self

4. _top
    this loads the top-level browsing context of the current browser document after submission<br>
    this is the top-most ancestor of the current browser document without an ancestor<br>
if there is no top, the browser loads the current browser document as_self<br><br>

### Input Form Attributes

1. formaction<br>
2. formenctype<br>
3. formmethod<br>
4. formnovalidate<br>

These <u>input form attributes</u> are added to form inputs
they will override their form attribute counterpart

**formaction**<br>
  specifies the URL which processes the form submission

```htm
<form>
 <input type="" formaction="url-which-processes-form-submission">
</form>
```

**formenctype**
  formenctype specifies the type of encoding in the form

```htm
<form>
 <input type="" formenctype="application/x-www-form-urlencoded” | “multipart/form-data” | “text/plain”>
</form>
```

**formmethod**<br>
  formmethod specifies the HTTP method to submit the form to the server

```htm
<form>
 <input type="" formmethod="post” | “get”>
</form>
```

**formnovalidate**<br>
formnovalidate specifies that the form submission should not be validated

```htm
<form>
 <input type="" formnovalidate="novalidate">
</form>
```

**formtarget**<br>
  formtarget specifies where to display the response after the form submission>

```htm
<input type="" formtarget="_self | _blank | _parent | _target">
</form>
```

### Form elements

These are elements which are nested in the form element

 1. fieldset
 2. legend
 3. label
 4. input
 5. select
 6. option
 7. textarea
 8. button
 9. list
 10. datalist
 11. output
 12. optgroup

**FIELDSET tag**<br>

this is used to group controls into related forms<br>
controls are form elements with input fields which receive data<br>
this also draws a box around related elements

syntax:

```htm
<form id="unique-identifier">
<fieldset
form=id="associated-unique-identifier-from-form"
name="name-of-fieldset”
disabled
>
 <legend></legend>
  <label></label>
  <label></label>
  <label></label>
</fieldset>
</form>
```

**FIELDSET attributes**<br>

**fieldset** specifies and associates <u>form controls</u>

*form*<br>
_form_ attr is given a unique identifier which associates the fieldset with a form<br>
The fieldset does not need to be nested inside the form which they are already associated, but it is good practice to nest the fieldset inside it’s associated form even if they are already associated by form and id attr

*name*<br>
_name_ attr is the name of the fieldset<br>

*disabled*
_disabled_ attr makes the form’s descendants <u>uneditable</u>, <u>unsubmittable</u> and <u>immutable</u>

**LEGEND tag**
**legend** specifies a caption for a **fieldset**

syntax:

```htm
<form>
<fieldset>
 <legend></legend>
  <label></label>
  <label></label>
  <label></label>
</fieldset>
</form>
```

**LABEL tag**<br>
**label** specifies a <u>caption</u> for the controls which it’s associated with:

 1. input
 2. button
 3. select
 4. textarea
 5. output
 6. meter*(out of scope of topic)
 7. progress

**label** is automatically associated with its 1st nested descendant<br>
That said, it is good practice to associate the label with it’s associated element<br>
The element associated with the label (like input) may be placed outside the label but in this case, the associated element’s for attr should have been associated with the id attr of the label element.<br>

syntax:

```htm
<form>
<fieldset>
 <legend>
  <label for="associated-unique-identifier">
   <input id=" for="associated-unique-identifier-from-fieldset">
  </label>
</fieldset>
</form>
```

**LABEL attributes**

*for*<br>
*for* attr associates the **label** with the *id* attr of the **label** element.

**INPUT**<br>
*continued in detail below*

**SELECT tag**
**select** specifies an input field with a dropdown menu

syntax:

```htm
<form id="unique-identifier">
 <label>
  <select
form=id="associated-unique-identifier-from-form"
name="name-for-select-field”
autocomplete="on” | “off”
disabled
multiple
required
size="input-field-width-OR-submit-button-height”
>
   <option>
  </select> 
 </label>
</form>
```

**SELECT attributes**<br>

_form_<br>
_form_ attr is given a <U>unique identifier</U> which associates the select with a form<br>
**select** <u>does not need</u> to be <u>nested inside the form</u> if they are <u>already associated</u>, but it is <u>good practice</u> to nest the **select** inside it’s <u>associated form</u> even if they are already associated by form and id attr
<br>

_name_<br>
_name_ of the **select** control
<br>

_autocomplete_<br>
_autocomplete_ specifies if **select** control will be autocompleted
<br>

_disabled_<br>
_disabled_ specifies if **select** control will be disabled
<br>

_multiple_<br>
_multiple_ specifies if multiple `<option>` controls can be selected
<br>

_required_<br>
_required_ specifies if select control will be required

_size_<br>
_size_ specifies the **input field** <u>width</u> OR **submit button** <u>height</u>