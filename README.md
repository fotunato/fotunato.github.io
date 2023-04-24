```
<style>
  @import url('https://fonts.googleapis.com/css2?family=Buda:wght@300&family=Forum&family=Josefin+Sans&family=Khula&family=Libre+Baskerville&family=Philosopher&family=Playfair+Display&family=Questrial&family=Raleway&family=Sora&display=swap');
</style>
```

# MY WIKI

# Forms

The form element is used to group related input through input fields, radio buttons etc

### Form attributes (global)

<u>accept-charset</u>

specifies type of character encoding the server uses to interpret the form data for the form<br>
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



3. novalidate

```htm
 <form novalidate>
 </form>
```

*overridden by formnovalidate*
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

*disabled*<br>
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
The element associated with the label (like input) may be placed outside the label but in this case, the associated element’s _for_ attr should have been associated with the id attr of the label element.<br>

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

**SELECT tag**<br>
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
_required_ specifies if `<select>`</select> control will be required

_size_<br>
_size_ specifies the **input field** <u>width</u> OR **submit button** <u>height</u>

**OPTION tag**<br>
**option** specifies the **option**(s) control(s) for the _parent_ `<select>` element

syntax:

```htm
<form id="unique-identifier">
 <label>
  <select>
   <option
value="value-which-is-submitted-to-server"
disabled
label
selected
>
   <option>
  </select> 
 </label>
</form>
```

**OPTION attr**<br>

_value_<br>
_value_ specifies text which is submitted to the server<br>
if _no value_ is given, the _visible text_ is submitted to the server
<br>

_disabled_<br>
_disabled_ specifies if the <u>selected option</u> is _disabled_
<br>

_label_<br>
_label_ specifies the text which is <u>visible</u><br>
if _label_ and the normal <u>visible text</u> are both provided, _label_ takes <u>precedence</u>
<br>

_selected_<br>
_selected_ specifies that the option is _selected_ <u>by default</u> when the page loads
<br>

syntax:

```htm
<select>
 <optgroup
 disabled
 label
 >
  <option>
  <option>
 </optgroup>
</select>
```
<br>

_submit_ creates  button as well but a button created from **button** type has NO DEFAULT STYLING whilst a button created from submit type has DEFAULT STYLING_
<br>

_datalist_<br>
_datalist_ specifies a pre-defined list for an associated input
the user can input text into the input field<br>

syntax:

```htm
<input list="unique-identifier">
<datalist id="unique-identifier-from input-list”>
 <option value="option1”>
 <option value="option2”>
 <option value="option3”>
</datalist>
```

**_select_** vs _datalist_
in _select_, the user can <u>only select one</u> (or more if multiple attr is specified)
in _datalist_, the user can <u>type into the text field</u> which means the user has <u>infinitely more options</u>
<br>

_select_ is used to provide the <u>ONLY AVAILABLE OPTIONS</u> for the user but _datalist_ options are <u>more of a suggestion</u> since the user can choose one of those or simply type in their choice <u>which does not have to be one of the available choices</u>

**INPUT types**<br>
**INPUT types** determine <u>what type of input</u> should be collected
<br>
<br>

**INPUT attr**<br>
_accept_<br>
_accept_ determines _what type of file_ (_file-types_) should be <u>accepted by the input</u><br>
_accept_ applies to ONLY **file** type<br>
<u>Wildcards</u> can be used to target <u>more than one file-type</u>:<br>

```htm
<ul>
 <li>comma(,)</li>
 <li>file/*</li>
   <Ol>
    <li>audio/*</li>
    <li>video/*</li>
    <li>image/*</li>
   </Ol>
</ul>
```

 **comma (,)**<br>
 `<input type="file” accept="file1,file2,file3">`
	
 **_file/***_ :<br><br>
   **audio/**<br>
		`<input type="file” accept="audio/*">`<br>
targets all audio files

  **video/**<br>
		`<input type="file” accept="video/*">`<br>
targets all video files

  **image**<br>
		`<input type="file” accept="image/*">`<br>
targets all image files
<br>

_autocomplete_<br>
*NEW BROWSERS WILL <u>OVERRIDE</u> _autocomplete_ to <u>provide prompts</u> for user to <u>REMEMBER PASSWORD</u> or <u>REMEMBER USERNAME</u><br>
This is because <u>this mode</u> is thought to be <u>more secure</u> than asking the user to input their username & password EVERY SINGLE TIME<br>
_autocomplete_ determines if a browser should _autocomplete_ input data<br>
_autocomplete_ applies to all input types which accept text OR numeric values i.e_ _name, password, email etc_<br>
_autocomplete_ can be applied to a form **INPUT** type<br>
In this case, it applies to <u>all the form’s input</u> unless the input itself has a <u>contrary autocomplete attr</u>

`<input</u> type="” autocomplete="">`

OR

values<br>
**_on_** (<u>file type</u>)<br>
`<input type="” autocomplete="on">`<br>
_autocomplete_ is turned **on**

**_off_**<br>
`<input type="” autocomplete="off">`<br>
_autocomplete_ is **off**

*the <u>values</u> (themselves) determine if _autocomplete_ should be <u>on</u> or <u>off</u><br>

_new-password_<br>
`<input type="” autocomplete="new-password">`<br>
_password_ is <u>not autocompleted</u> since this <u>specifies a new password</u><br>

_name_<br>
`<input type="” autocomplete="name"`<br>
_name_ is <u>autocompleted</u><br>

_email_<br>
`<input type="” autocomplete="email">`<br>
_email_ is <u>autocompleted</u><br>

_username_<br>
`<input type="” autocomplete="username">`<br>
_username_ is <u>autocompleted</u><br>

_cc-name_<br>
_cc-number_<br>
_etc_<br>
_both are for cc details as well as other cc-*_<br>

More values exist for autocomplete can be found [here]([https://](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/autocomplete))

_autofocus_<br>
`<input type="" autofocus>`<br>
 _autofocus_ specifies an input which should be <u>automatically focused</u> on when the page is <u>first loaded</u><br>

_capture_<br>
_capture_ is used to collect <u>images</u>,<u>audio</u> & <u>video</u>.
_accept_ attr specifies the **file-type** which is <u>captured</u> by _capture_ attr
_capture_ applies to **file type**

_values_
The result produced by the capture attr is <u>**contextual**</u> but by _default_, _capture_ attr has 2 values:

* user<br>
`<input type="file” capture="user | environment" accept=".ext">`<br>
This collects _.ext_ (_.ext_ means _extension_) **file-type** data from the **device** <u>facing the user</u>

* environment<br>
`<input type="file” capture="environment" accept=".ext">`<br>
This collect _.ext_ (_.ext_ means _extension_) **file-type** data from the **device** <u>facing away from the user</u>/ <u>outward-facing device</u>

BY DEFAULT, *user* and *environment* open the <u>front camera</u> (user) and the <u>back camera</u> (environment) on <u>devices with cameras</u> (audio & video)/ microphone (audio) to collect the value(s) specified by accept, if the values **file** type accepts are images, videos or audio.<br>
Since PC’s do not have back cameras, the file-type will _default_ to a _default file input type_.<br>
`<input type="file">`<br>

_cross-origin_<br>
`<script | link | img src="external source of resource” cross-origin="anonymous | user-credentials | ‘empty-string'">`<br>
This is used to specify that a browser needs to access resources <u>from other sources</u> like an api<br>
_cross-origin_ is applicable in `<script>`, `<link>` & `<img>`.<br>
Simply, _cross-origin_ is specifying <u>how to request resources</u> (like scripts, links and images) <u>from other sources</u> other than it’s native document<br><br>

Values<br><br>
_anonymous_<br>
`<script | link | img src="external source of resource” cross-origin="anonymous">`<br>
The <u>source</u> of the resource is <u>different</u> from the <u>native document</u><br>
<u>No user-credentials</u> are <u>required</u> to fetch the resource<br>

_user-credentials_<br>
`<script | link | img src="external source of resource” cross-origin="user-credentials">`<br>
The _source_ of the resource is _different_ from the <u>native document</u><br>
_user-credentials_ are <u>required</u> to <u>fetch the resource</u><br>

_‘empty-string’_<br>
`<script | link | img src="external source of resource” cross-origin="">`<br>
The _source_ of the resource is the <u>native document</u> itself

_disabled_<br>
`<input type="” disabled>`<br>
_disabled_ applies to _all_ **input** types which _accept_ <u>text</u> OR <u>numeric values</u><br>
_disabled_ also applies to `<fieldset>`<br>
In this case though, all the _children_ of the `<fieldset>` are _disabled_ except for the `<legend>` tag<br>

use cases<br>
i. disabling an input tag after a deadline<br>
ii. disabling some elements which would only become active when other elements have been completed/ activated<br>
etc<br>

_elementtiming_ ***js**<br>
`<img elementtiming="identifier-for-observed-element”>`<br>
`<svg>
	<image elementtiming="identifier-for-observed-element”>
</svg>`

_elementtime_ is used to <u>provide an identifier</u> for some elements<br>
_elementtime_ applies to:<br>
	* imgemail<br>
	* image element in svg elememt<br>
	* poster attr for video element<br>

_for_<br>
`<label for="unique-identifier"></label>`<br>
	`<input id="unique-identifier">`<br>
_for_ is added to <label> and <output> to <u>associate</u> them to their associated <u>controls</u><br>
an _id_ attr is added to the _associated_ <u>controls</u><br>

_height_ & _width_<br>
`<input type="image" src="” height="height-of-image” width="width-of-image”>`<br>
_height_ & _width_ specify the <u>height</u> and <u>width</u> of an <u>image</u><br>

_list_<br>
`<input list="unique-identifier”>`<br>
`<datalist id="unique-identifier-from input-list”>`<br>
`	<option value="option1”>`<br>
`	<option value="option2”>`<br>
	`<option value="option3”>`<br>
`</datalist>`<br>
_list_ points to an associated _datalist_ which has <u>pre-defined options</u> for an `<input>` element<br>
_list_ attr (in the **input**) and the _id_ attr (in the **datalist**) must be <u>associated</u> with a _unique identifier_<br>

_max_
`<input type="” max="max-number-for-value">`
_max_ specifies the <u>maximum value</u> for the input **file** type<br>
_max_ applies to <u>**all**</u> input types which receive <u>number input</u><br>
_max_ applies to:
+ date
+ datetime-local
+ month
+ number
+ range
+ tel
+ time
+ week
<br>

_min_<br>
`<input type="” min="min-number-for-value">`<br>
_min_ specifies the <u>minimum value</u> for the input **file** type<br>
_min_ applies to <u>**all**</u> input types which receive <u>number input</u><br>
_min_ applies to:
+ date
+ datetime-local
+ month
+ number
+ range
+ tel
+ time
+ week
<br>

_maxlength_<br>
`<input type="” maxlength="max-number-of-characters-for-value">`<br>
_maxlength_ specifies the <u>maximum number of characters</u> for the input **file** type<br>
<u>maxlength</u> applies to <u>**all**</u> input types which receive <u>number input</u><br>
_maxlength_ applies to:
+ date
+ datetime-local
+ month
+ number
+ range
+ tel
+ time
+ week
<br>

_minlength_<br>
`<input type="” minlength="min-number-of-characters-for-value">`<br>
_minlength_ specifies the <u>minimum number of characters</u> for the input **file** type<br>
_minlength_ applies to <u>**all**</u> input types which receive <u>number input</u><br>
_minlength_ applies to:
+ date
+ datetime-local
+ month
+ number
+ range
+ tel
+ time
+ week
<br>

_multiple_<br>
`<input type="” multiple>`<br>
_multiple_ specifies that a user can _add_ <u>more than one value</u> into an <u>input field</u><br>
_multiple_ applies to:
+ file
+ email
+ `<select>`

_file_<br>
`<input type="file” multiple>`<br>
By default, **ONLY ONE** object can be _added_ to the **file** input AT ONE TIME<br>
_multiple_ attr allows for **more than ONE** object to be _added_ to the **file** input AT ONE TIME

_email_<br>
`<input type="email” multiple>`<br>
By default, **ONLY ONE** email can be _added_ to the **file** input AT **ONE TIME**<br>
_multiple_ attr allows for _more than ONE_ email to be _added_ to the **file** input **AT ONE TIME**<br>
The emails should be _separated_ by a <u>comma</u> (,)<br>
_eg. a@yahoo.com,b@yahoo.com,c@yahoo.com ..._

_pattern_<br>
`<input type="” pattern="regex-pattern">`<br>
`<pattern="regex-which-the-browser-validates-input-value-against" title="text-which-appears-as-tooltip">`<br>
_pattern_ specifies a <u>regular expression</u> (_regex_) which is used to **validate** the _input value_<br>
the _pattern_ attr is part of the **constraint validation** process<br>
_title_ attr is added to the **input** to <u>provide a tooltip</u> for the _password_ attr<br>
_pattern_ applies to:
+ text
+ tel
+ email
+ URL
+ password
+ search
<br>

**REGULAR EXPRESSIONS** (regex)<br>
These <u>regex</u> define a <u>string</u> _against which_ the _input’s value_ is **validated**<br>
Using <u>regex</u> simply comes down to _understanding_ the _strings_ which _come together_ to _form_ a **LARGER** <u>regex</u> _string component_<br>

There are many types of <u>regex</u>:<br>
1. Quantifiers<br>

TBD<br>
_pattern_ attr should be used with _title_ attr

_placeholder_<br>
`<input type="” placeholder>`<br>
_placeholder_ specifies a **hint** which appears in an _input field_ to give the user an idea about what _kind of input_ is expected<br>
_placeholder_ text usually appears _lighter_ than the actual text<br>
_placeholder_ text _disappears_ when input is entered into the input field<br>
Unlike _value_ attr, _placeholder_ text is <u>not submitted</u> when _no input_ is _entered_ into the _text field_<br>

_readonly_<br>
`<input="” readonly>`<br>
_readonly_ specifies an _input form_ to be:<br>
+ uneditable (like disabled)
+ able to receive focus (unlike disabled)
+ can be tabbed (unlike disabled)
+ submitted with the form (unlike disabled)
:read-only pseudo-class is used to target input forms in the read-only state
readonly applies to:
  1. date
  2. datetime-local
  3. email
  4. month
  5. number
  6. password
  7. search
  8. tel
  9. text
  10.  time
  11.  url
<br>

use cases<br>
1. displaying all completed input fields after all the data has been collected<br>
2.  readonly stops the user from changing details at this point<br>
3. block input into cc input field after cc details have been inputted<br>

_required_<br>
`<input type="” required>`<br>
_required_ specifies that an **input** <u>should have a value</u><br> 
if the _specified input_ has <u>no value</u>, a _prompt_ appears when the **form** is _submitted_<br>
_required_ attr is used to <u>stop the browser</u> for <u>validating</u>/ <u>auto-validating</u> a **form** _IF THE INPUT IS EMPTY_.<br>

_required_ applies to:<br>
+ checkbox
+ date
+ datetime-local
+ email
+ file
+ month
+ number
+ password
+ radio
+ search
+ tel
+ text
+ time
+ url
+ week<br>
+ (elements)<br>
  + `<select>`
  + `<textarea>`

_size_<br>
`<input type=""`<br>
`size="input-field-width-OR-submit-button-height”>`<br>
_size_ is used to determine:<br>
	1. <u>width</u> of an input field<br>
	2. <u>height</u> of a submit button<br>

_size_ applies to:<br>
	1. text<br>
	2. `<submit>`

_step_<br>
`<input type="” step="interval-amount”>`<br>
_step_ specifies the <u>interval</u> between _min_ and _max_<br>
_step_ applies to:
+ date
+ datetime-local
+ month
+ number
+ range
+ time
+ week
<br>

_title_<br>
`<input type="” title="this-will-appear-on-hover">`<br>
_title_ attr specifies a <u>tooltip</u> which <u>appears on hover</u><br>
_title_ attr should be _used with_ **pattern** attr<br>


_value_<br>
`<input type="” value="default-input">`<br>
_value_ attr specifies a **hint** which _appears_ in an **input field** by _default_<br> 
Unlike _placeholder_ attr,the _value_ input is _submitted_ when **no input** is _entered_ into the **text field**<br><br>

### INPUT types
_button_<br>
`<input type="button" value="text-on-button">`<br>
_button_ creates a _well..._<u>_button_</u><br><br>
_**submit** creates **button** as well but a <u>button</u> created from **button type** has <u>NO DEFAULT STYLING</u> whilst a **button** created from **submit type** has <u>DEFAULT STYLING_</u>

_checkbox_<br>
`<label>`<br>
`	<input type="checkbox”>`<br>
`</label>`<br>
_checkbox_ type creates a <u>checkbox</u><br>
By default, <u>different</u> checkboxes can be checked <u>at the same time</u><br>
To make it so **ONLY ONE** _checkbox_ is _checked_ **at one time**, we need to to give the checkboxes **the same name** attr<br>
This makes it so **only one** checkbox can be chosen **at any one time**<br>
_checkbox_ is **preferable** for _selecting_ <u>multiple options</u> but _radio buttons_ are _preferable_ for _selecting_ <u>just 1 option</u><br>

_color_<br>
`<label>`<br>
	`<input type="color” value="#000000">`<br>
`</label>`<br>
_color_ type creates an _input field_ that contains _color_<br>
This field appears _differently_ in _different browsers_.
_Some browsers_ might use a _simple_ <u>color changer</u> whilst _others_ open a <u>color picker</u> in a _new window_ amongst _other changes_ in _other browsers_<br>
The _default value_ is **#000000** (black)<br>
The _value_ needs to be a **hex decimal** with **7 values**<br>
If not, the _color_ <u>reverts</u> to the **INPUT ** type, which is **black**<br>

_date_<br>
`<input type="date"` 
`value="yyyy-mm-dd" `
`min="earliest-date-to-accept"`
`max="latest-date-to-accept”`
`step=""interval-as-user-chooses-dates-in-DAYS”`
`>`<br>

for **STEP**, 1 =  1day<br>
_value_ attr specifies the _default date_ in the <u>input field</u> when the <u>webpage</u> _first loads_
_date_ type creates an _input field_ which <u>receives dates</u><br>
On _some browsers_, a _special interface_ appears.
the _format_ of the **date** must be **yyyy**-**mm**-**dd**<br>

_datetime-local_<br>
`<input type="datetime-local" ` `value="yyyy-mm-dd-HH-MM" `
`min="earliest-date-to-accept"`
`max="latest-date-to-accept”`
`step=""interval-as-user-chooses-time-in-SECONDS”`>`<br>

for **STEP**, 60 = 60s<br>
_value_ attr specifies the _default_ <u>date</u> & <u>time</u> in the _input field_ when the <u>webpage</u> _first loads_.<br>
_datetime-local_ type _creates_ an _input field_ which _receives_ <u>dates</u> & <u>time</u><br>
On _some browsers_, a _special interface_ appears<br>
the _format_ of the <u>date</u> must be **yyyy**-**mm**-**dd**<br>

_email_<br>
`<input type="email" pattern="regex-for-email">`<br>
_email_ type _creates_ an _input field_ which _receives_ <u>email input</u><br>

_file_<br>
`<input type="file"`
`accept="accepted-file-type”`
`capture="user | environment”`
`multiple`
`>`<br>

**file** type _creates_ an _input field_ which _receives_ **uploaded files**<br>

_hidden_<br>
`<input type="hidden” name="” value="hidden-content">`<br>
_hidden_ input _creates_ an _input field_ which is _hidden_ on the document/ _not visible_ to the user<br>
The _hidden content_ can be _accessed_ via the _browser’s inspection tools_ though<br>
the _name_ attr is normally used to <u>add a name</u> for the **input**<br>
for _hidden_ type though, _name_ can be set to “_charset_” prop which causes the inputted value type to be submitted with it’s prop set to the character encoding<br>

use cases<br>
1. secure content may be hidden on the document to add a layer of security for the webpage<br>

_image_<br>
`<input type="image” `
`scr="source-of-image”`
`alt="alternative-text-shown-if-image-is-not-loaded"`
`height="height-of-image"`
`width="width-of-image"`
`formaction="”`
`formenctype="”on value="suggested-step3“`
`formmethod="”`
`formnovalidate="”`
`formtarget="”`
`>`
<br>


_image_ type specifies an _image_ which <u>appears</u> as a <u>submit button</u><br>

use cases<br>
1. any photo/ flavicon can be used as a submit button

_month_<br>
`<input type="month”`
`value="YYYY-MM(default-month)”`
`max="YYYY-MM(latest-date-allowed)”`
`min="YYYY-MM(earliest-date-allowed)”`
`readonly`
`step="number-intervals” | (number is allowed)`<br>
`list="unique-identifier”`<br>
`<datalist id="associated-unique identifier”>`<br>
`	<option value="suggested-month1”>`<br>
`	<option value="suggested-month2”`<br>
`	<option value="suggested-month3“`<br>
`</datalist>`<br>
`>`<br>
_month_ type specifies an **input field** which _allows_ the user to <u>input a date</u><br>
a <u>date picker</u> may _appear_ in _some browsers_<br>

_number_<br>
`<input type="number”`
`value="YYYY-MM(default-month)”`
`max="YYYY-MM(latest-date-allowed)”`
`min="YYYY-MM(earliest-date-allowed)”`<br>
`maxlength="maximum-number-of-characters”`
`minlength="minimum-number-of-characters"`
`step="number-intervals” | (number is allowed)`<br>
`list="unique-identifier”`<br>
`<datalist id="associated-unique identifier-with-list”>`<br>
`	<option value="suggested-number1”>`<br>
`	<option value="suggested-number2”`<br>
`	<option value="suggested-number3“`<br>
`</datalist>`<br>
`>`<br>

_password_<br>
`<input type="password"`
`value="default-password(can be empty)”`
`maxlength="maximum-number-of-characters”`
`minlength="minimum-number-of-characters"`
`placeholder="placeholder-text”`
`readonly`
`size="size-of-input-field”`
`autocomplete="”`<br>
`>`<br>
_password_ specifies a _password field_ is _required_ for _entering_ <u>passwords</u><br> 

_radio_<br>
`<input type="radio”`<br>
`value="unique-value-for-radio-button”`<br>
`name="common-name-given-to-radio-buttons-in-same-group”`<br>
`checked (automatically checked)`<br>
`required`<br>
`>`<br>

**radio buttons** specify _input fields_ which can be _selected_ (and _appear_ like actual radio buttons)<br>
*a _CSS prop_ called **appearance** can be used to _style_ to **radio buttons** but it is _fairly new_ so _browser support_ is **limited**<br>
**radio buttons** are preferable for _selecting_ just **1 option** but _checkbox_ is preferable for _selecting_ <u>multiple options</u><br>

_range_<br>
`<input type="range"`<br>
`value="starting-point-for-slider” | (default is halfway between max & min)`<br>
`max="minimum-value”`<br>
`min="maximum-value”`<br>
`step="number-intervals” | (number is allowed)`<br>
`list="unique-identifier”`<br>
`<datalist id="associated-unique identifier-with-list”>`<br>
`	<option value="suggested-step1”>`<br>
`	<option value="suggested-step2”`<br>
`	<option value="suggested-step3“`<br>
`</datalist>`<br>
`>`<br>
_range_ specifies a <u>slider</u>
The _minimum_ and _maximum_ <u>extremes</u> can be _specified_<br>

*_additional_ _CSS props_ (_not fully supported_ on all browsers)<br>
**appearance** - for styling appearance<br>
**orient** - for styling vertical / horizontal orientation<br>

_reset_<br>
`<input type="reset”`<br>
`title="text-which-appears-on-hover" | (accessibility)`<br>
`>`<br>
_reset_ type specifies an _input field_ which _resets_ **ALL INPUT FIELDS** in the **form**<br>

_search_<br>
`<input type="search”`<br>
`value="default-text”`<br>
`maxlength="maximum-number-of-characters”`<br>
`minlength="minimum-number-of-characters"`<br>
`placeholder="placeholder-text”`<br>
`>`<br>
_search_ defines a _text field_ which receives _search input_<br>
_search input_ is basically just a _text input field_ with _specialized features_ like:<br>
	1. default styling (like the appearance of a magnifying glass icon in some browsers)<br>
	2. less browser support<br>

_submit_<br>
`<input type=submit`<br>
`value="text-which-appears-on-submit-button”`<br>
`formaction="”`<br>
`formenctype="”`<br>
`formmethod="”`<br>
`formnovalidate="”`<br>
`formtarget="”`<br>
`>`<br>
_submit_ specifies a **button** which 
sends _form data_ to the _nearest form_ (the _parent element_, if it exists)<br>

_tel_<br>
`<input type="”`<br>
`maxlength="maximum-number-of-characters”`<br>
`minlength="minimum-number-of-characters"`<br>
`placeholder="placeholder-text”`<br>
`readonly`<br>
`size="input-field-width-OR-submit-button-height”`<br>
`list="unique-identifier”`<br>
`<datalist id="associated-unique identifier-with-list”>`<br>
`	<option value="suggested-step1”>`<br>
`	<option value="suggested-step2”`<br>
`	<option value="suggested-step3“`<br>
`</datalist>`<br>
`>`<br>
_tel_ specifies a _text field_ which receives <u>telephone numbers</u><br>
_tel_ input is basically just a _text input field_ with _specialized features_ like:<br>
	1. displaying numeric keyboard for input<br>
	2. provides special formatting for phone numbers<br>

_text_<br>
`<input type="text”`<br>
`maxlength="maximum-number-of-characters”`<br>
`minlength="minimum-number-of-characters"`<br>
`placeholder="placeholder-text”`<br>
`readonly`<br>
`size="input-field-width-OR-submit-button-height”`<br>
`list="unique-identifier”`<br>
`<datalist id="associated-unique identifier-with-list”>`<br>
`	<option value="suggested-step1”>`<br>
`	<option value="suggested-step2”`<br>
`	<option value="suggested-step3“`<br>
`</datalist>`<br>
`>`<br>

_time_<br>
`<input type="time”`<br>
`value="HH-MM" | (default time) `<br>
`min="earliest-time-to-accept"`<br>
`max="latest-time-to-accept”`<br>
`step=""interval-as-user-chooses-time-in-SECONDS”`<br>
`list="unique-identifier”`<br>
`<datalist id="associated-unique identifier-with-list”>`<br>
`	<option value="suggested-step1”>`<br>
`	<option value="suggested-step2”`<br>
`	<option value="suggested-step3“`<br>
`</datalist>`<br>
`>`<br>
_time_ specifies an _input field_ which _accepts_ <u>time input</u><br>

_url_<br>
`<input type="url”`<br>
`value="default-url"`<br>
`maxlength="maximum-number-of-characters”`<br>
`minlength="minimum-number-of-characters"`<br>
`placeholder="placeholder-text”`<br>
`readonly`<br>
`size="input-field-width-OR-submit-button-height”`<br>
`list="unique-identifier”`<br>
`<datalist id="associated-unique identifier-with-list”>`<br>
`	<option value="suggested-step1”>`<br>
`	<option value="suggested-step2”`<br>
`	<option value="suggested-step3“`<br>
`</datalist>`<br>
`>`<br>
_url_ specifies an _input field_ which _accepts_ **url’s**<br>

_week_<br>
`<input type="week”`<br>
`value="YYYY-W+(week number) | 2023-W10 = 10th week of 2023 | (default-week)”`<br>
`max="YYY-W(+week number) | (latest-week-allowed)”`<br>
`min="YYY-W(+week number) | (earliest-date-allowed)”`<br>
`step="number-intervals” | (number is allowed)`<br>
`readonly`<br>
`list="unique-identifier”`<br>
`<datalist id="associated-unique identifier”>`<br>
`	<option value="suggested-month1”>`<br>
`	<option value="suggested-month2”`<br>
`	<option value="suggested-month3“`<br>
`</datalist>`<br>
`>`<br>
<br>
`<textarea>`<br>
This is used to specify a text field for multi-line text<br>
_rows_ attr is used to specify the number of rows<br>
_cols_ attr is used to specify the number of column<br>

`<input type="time”>`
This is used to allow the user to _specify a time_<br>
A _time-picker_ appears in _some browsers_<br>

_additional attr_<br>

1. _min_<br>
determines the <u>earliest time</u> which _can be chosen_<br>

2. _max_<br>
determines the <u>latest time</u> which _can be chosen_<br>

3. _step_<br>
determines the _intervals_ in the _time_ (in _seconds_)<br>
when _step_ is _not specified_, _default_ is **‘60’**/ **1 minute**<br>
 
EXAMPLE<br>
`<input type="time” max=”00:00“ min="01:00" step="600">`<br>
The user can choose between **00:00** and **01:00** at **10 minute** (**60s** x **10**) _intervals_<br>

_Time-zone_ is <u>not specified</u> when using <time> attr<br>
_format_ for **time** is **00:00** -> **24:00**<br>

_general attributes_<br>
_required_<br>
The _input tag_ should _be filled_ or should _not be empty_<br>
If _input field_ is _left empty_, an <u>error message</u> will _appear_<br>

_min-height_<br>
This applies to **text fields** _eg. **input** | **textarea**_<br>
We can specify the _min height_ of text in these _text fields_****

*tip*<br>
add _placeholder text_ to **all** _text fields_

*tip*<br>
add _unique name_ (_names_) attr to **all** _submittable text_ as _best practice_

### Validation of `<input>` & `<form>`<br>
when input is received, the browser must first validate the input to determine if the input is within pre-defined parameters before the input is submitted to the server

pre-defined parameters
these parameters can be defined by:
1. the author of the webpage
2. the browser itself

validation by the author of the webpage<br>
there are different ways to provide the parameters:
1. required attr<br>
`<input type="” required="REGEX">`<br>
regex patterns are used to provide the patterns for the required attr
2. Javascript
Javascript can be used to validate input data

Validation by the browser itself (auto-validation)<br>
The browser auto-validates the input with auto-defined patterns

Why is validation important
1. user experience
2. security

user experience<br>
The user may input incorrect info by mistake.<br>
If the wrong information is validated, incorrect data is collected<br>
This will invariably lead to problems down the line<br>
We can use _**:valid**_ and **_:invalid_** pseudo-classes to specify changes which occur when the  user enters the wrong info or the right info<br>

security<br>
Hackers intentionally send malicious code as input<br>
This is so that if this malicious code is validated, this data is sent up and injected into the server<br>
The hacker now has their malicious code in the server<br>
Validation blocks this malicious code from being sent to the server<br>
As such, validation provides a LAYER OF SECURITY<br>

### :valid and :invalid pseudo-classes<br>
**:valid pseudo-class**<br>
this specifies a state where the input has been validated<br>
we can specify changes like a green input background or adding a “tick” to inform the user that their data is correct has been validated<br>

**:invalid pseudo-class**<br>
this specifies a state where the input has been invalidated or has not been validated<br>
this happens when the collected data does not meet the requirements for the pre-defined patterns for validation<br>
we can specify changes like a green input background or adding a “tick” to inform the user that their data is correct has been validated<br> 

Client-side vs Server-side validation<br>
<u>Client-side validation</u> refers to validation which when a client inputs data before the data is submitted to the server.<br>
Constraint validation comprises all the steps of validation which are introduced into a document on the client-side<br>

<u>Server-side validation</u> involves validation after the data has been submitted up to the server.<br>
Languages like php, python & js are called server-side languages because <br>
They are used to develop code which deploys on server-side rather than client-side<br>
js is a client-side language as well though<br>
Optimally, it is advised to provide both client-side and server-side validation to provide double-layer protection<br>

Constraint validation<br>
HTML5 introduced the use of constraint validators in 2014.<br>
Here, client-side validation is provided through the use of:<br>
1. input types<br>
Simply, we specify the input type<br>
2. input attr<br>
Simply, we specify ALL the necessary input attr
i.e we provide all necessary attr like min, max, step as it applies to that specific input type<br>
3. pseudo-class selectors<br>
Simply, we specify pseudo-classes like :valid & :invalid to specify a new state<br>
eg.
+ :valid
+ :invalid
+ :required (selects required inputs) 
+ :invalid (selects inputs with invalid values)<br>

_i.e Values which will not appear like a value less than min attr_<br>

Basically, we follow constraint validation when we follow good-practices for input types<br>
