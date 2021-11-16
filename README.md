# Templates

resource for different code templates

### HTML template

*this boiler plate was provided by Louis Lazaris at [HTML5 Template: A Basic Boilerplate for Any Project](https://www.sitepoint.com/a-basic-html5-template/)*

```html
<!doctype html>

<html lang="en">
<head>
  <meta charset="utf-8">
  <!--set initial-scale=1 for a 1:1 aspect raito-->
  <meta name="viewport" content="width=device-width, initial-scale=1">

  <title>A Basic HTML5 Template</title>
  <meta name="description" content="A simple HTML5 Template for new projects.">
  <meta name="author" content="SitePoint">

  <meta property="og:title" content="A Basic HTML5 Template">
  <meta property="og:type" content="website">
  <meta property="og:url" content="https://www.sitepoint.com/a-basic-html5-template/">
  <meta property="og:description" content="A simple HTML5 Template for new projects.">
  <meta property="og:image" content="image.png">
  
  <!--favicon.ico is for older browsers-->
  <link rel="icon" href="/favicon.ico">
  <!--favicon.svg is for newer browsers-->
  <link rel="icon" href="/favicon.svg" type="image/svg+xml">
  <link rel="apple-touch-icon" href="/apple-touch-icon.png">
  
  <!--add multiple stylesheets if needed, last one to load will have higher priority for any conflicts-->
  <link rel="stylesheet" href="css/styles.css?v=1.0">

</head>

<body>
  <!-- your content here... -->
  <script src="js/scripts.js"></script>
</body>
</html>

```

# React

### Adding React.JS to it (development)


*this source comes from the [React Docs](https://reactjs.org/docs/add-react-to-a-website.html).*


```html 
<!--these first two scripts add the development version of react 
  <script src="https://unpkg.com/react@17/umd/react.development.js" crossorigin></script>
  <script src="https://unpkg.com/react-dom@17/umd/react-dom.development.js" crossorigin></script>

  <!-- replace the "like_button.js" with the file name of the JS file where your React is written. -->
  <script src="like_button.js"></script>
```

### Adding React (production)

```html
<!--add these scripts to the bottom of the page -->
<script src="https://unpkg.com/react@17/umd/react.production.min.js" crossorigin></script>
<script src="https://unpkg.com/react-dom@17/umd/react-dom.production.min.js" crossorigin></script>
```

### Adding React with JSX

```html
<!--add this script to the bottom of the page -->
<script src="https://unpkg.com/babel-standalone@6/babel.min.js"></script>
```

# ADA Considerations 

*taken from [MDN: CSS and JavaScript accessibility best practices](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/CSS_and_JavaScript)*

### Abbreviations 

```html

<p>Web content is marked up using <abbr title="Hypertext Markup Language">HTML</abbr>.</p>

```

The recognized styling convention for abbreviations is a dotted underline, and it is unwise to significantly deviate from this. For more on abbreviations, 

### Links

```html

<p>Visit the <a href="https://www.mozilla.org">Mozilla homepage</a>.</p>

```

The standard link conventions are underlined and a different color (default: blue) in their standard state, another color variation when the link has previously been visited (default: purple), and yet another color when the link is activated (default: red). In addition, the mouse pointer changes to a pointer icon when links are moused over, and the link receives a highlight when focused (e.g. via tabbing) or activated. The following image shows the highlight in both Firefox (a dotted outline) and Chrome (a blue outline):


You can be creative with link styles, as long as you keep giving users feedback when they interact with the links. Something should definitely happen when states change, and you shouldn't get rid of the pointer cursor or the outline — both are very important accessibility aids for those using keyboard controls.

### Hiding content

There are many instances where a visual design will require that not all content is shown at once. For example, in our Tabbed info box example (see source code) we have three panels of information, but we are positioning them on top of one another and providing tabs that can be clicked to show each one (it is also keyboard accessible — you can alternatively use Tab and Enter/Return to select them).


Screen reader users don't care about any of this — they are happy with the content as long as the source order makes sense, and they can get to it all. Absolute positioning (as used in this example) is generally seen as one of the best mechanisms of hiding content for visual effect, because it doesn't stop screen readers from getting to it.

On the other hand, you shouldn't use visibility:hidden or display:none, because they do hide content from screen readers. Unless of course, there is a good reason why you want this content to be hidden from screen readers.



