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
    if there is no parent, the browser loads the current browser document as _self

4. _top
    this loads the top-level browsing context of the current browser document after submission<br>
    this is the top-most ancestor of the current browser document without an ancestor<br>
    if there is no top, the browser loads the current browser document as _self<br><br>

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