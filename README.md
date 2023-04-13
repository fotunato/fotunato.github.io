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

