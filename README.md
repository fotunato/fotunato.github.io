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

**overridden by *formaction*
<br>
<br>

<u>method</u>


```htm
<form method="http-method-used-to-send-data-to client” action="url-which-will-receive-the-data">
</form>
```

<u>enctype</u>

enctype specifies the type of encoding in the form

```htm
<form enctype="application/x-www-form-urlencoded” | “multipart/form-data” | “text/plain”>
</form>
```

**overridden by formenctype

 1. application/x-www-form-urlencoded
this is the default enctype value
name and value are separated by ‘&’

 1. multipart/form-data
this is used when the form contains <input> elements which have file attr type

 1. text/plain
thid idenctype
enctype specifies the type of encoding in the form
<form enctype="application/x-www-form-urlencoded” | “multipart/form-data” | “text/plain”>
</form>
**overridden by formenctype

 1. application/x-www-form-urlencoded
this is the default enctype value
name and value are separated by ‘&’

 1. multipart/form-data
this is used when the form contains <input> elements which have file type attr

 1. text/plain
this is used when security is not a concern like during debugging

method
method specifies the HTTP method to submit the form to the server
<form method="post” | “get”>
</form>
**overridden by formmethod

 1. post
this is the most-used method
post is used to send data to the server
post updates the server
post is more secure because unlike get, post does not include the data in the url

 2. get
this is used to retrieve data from the server
get does not update the server
get is not as secure as post because unlike post, get includes the data in the url

novalidate
novalidate specifies that the form submission should not be validated
<form novalidate>
</form>
**overridden by formnovalidate

target
target specifies where to display the response after submitting the form
<form target="_self” | "_blank” | "_parent” | "_top”>
</form>
**overridden by formtarget

 1._self
this loads the current browser document after submission
this is default

 2. _blank
this loads a new browser document after submission
this is default

 3. _parent
this loads the parent browsing context of the current browser document after submission
if there is no parent, the browser loads the current browser document as _self

 4. _top
this loads the top-level browsing context of the current browser document after submission
this is the top-most ancestor of the current browser document without an ancestor
if there is no top, the browser loads the current browser document as _self

Input Form Attributes
formaction
formenctype
formmethod
formnovalidate

these input form attributes are added to form inputs
they will override their form attribute counterpart

formaction
formaction specifies the url which processes the form submission
<form>
 <input type="" formaction="url-which-processes-form-submission">
</form>

formenctype
formenctype specifies the type of encoding in the form
<form>
 <input type="" formenctype="application/x-www-form-urlencoded” | “multipart/form-data” | “text/plain”>
</form>

formmethod
formmethod specifies the HTTP method to submit the form to the server
<form>
 <input type="" formmethod="post” | “get”>
</form>

formnovalidate
formnovalidate specifies that the form submission should not be validated
<form>
 <input type="" formnovalidate="novalidate">
</form>

formtargetForm Attr
formtarget specifies where to display the response after submitting the form
<form>
 <input type="" formtarget="novalidate">
</form> 
