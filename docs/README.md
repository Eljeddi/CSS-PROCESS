# Fundamentals

## Cascade, Specificity, and inheritance.

### Cascade

> When declarations conflicts the cascade consider these things:

1. Stylesheet origin (Author important-> author -> User agent)
2. Selector specificity
3. Source order

### Specificity

> When conflicted styles have the same origin then browsers priority are:

1. Inline styles
2. Selector specificity (ex: 1,2,0 is for 1 id , 2 classes & 0 tags)

> 1,0,0 takes precedence over 0,2,2.
> As we mentioned if conflicted styles have same specificity then whichever appear last wins.

### Inheritance

```css
:root {
  font-size: 16 px;
  /*Applied to all the DOM tree*/
}
```

#### The inherit keyword

```html
<footer class="footer">
  copyright &copy; all right reserved
  <a href="#">Terms of use</a>
</footer>
```

```css
a:link {
  color: blue;
}
.footer {
  color: white;
  background: black;
}
.footer a {
  color: inherit;
}
```

> What is the color of the link?

#### The initial keyword

what if we apply the following?

```css
.footer a {
  color: initial;
}
```

> Initial value just reset every property to its default value.which is black for the color property.

#### Shorthand property

```css
font: italic bold 18px/1.2 helvetica;
/*font-style font-weight font-size line-height font-family */
background:
border:
```

> Shorthand are cool, they keep code clean but be aware that sometime they overrides some styles, here is an example:

```css
h1 {
  font-weight: bold;
}
.title {
  font: 32px helvetica;
}
```

```html
<h1 class="title">Hello</h1>
<!-- is it gone be  bold ???>
```

> The answer is No ! because font property have a hidden part:

```css
.title {
  font-style: normal;
  font-weight: normal;
  /*overrides the "h1: bold" property because they have the same origin but the font wins the specificity (0,0,1 over 0,1,0) */
  ....;
}
```

## Relative units
