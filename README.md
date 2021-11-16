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

# CSS

<details>
  <summary>Selectors</summary>
  
  | selectors    | example    | description             | combinators         | example       | description                                              |
|--------------|------------|-------------------------|---------------------|---------------|----------------------------------------------------------|
| element      | p { }      | selects element         | element element     | div p { }     | selects all p elements inside div elements               |
| id           | #id { }    | selects by id           | element > element   | div > p { }   | selects all p elements where the parent is a div element |
| class        | .class { } | selects by class        | element.class       | div.class { } | selects all elements with a class of "class"             |
| attribute    | img[src]   | selects by attribute    | element + element   | div + p       | selects the first p element after a div                  |
| Pseudo-class | a: hover   | selects by pseudo-class | element1 ~ element2 | div ~ p       | selects every p element preceeded by a div               |
| *            | misc       | selects all elements    | element,element     | div, p        | selects all div elements and all p elements              |
|              |            |                         |                     |               |                                                          |
|              |            |                         |                     |               |                                                          |

*for a comprehensive list of selectors see [w3schools CSS Selector Reference](https://www.w3schools.com/cssref/css_selectors.asp)*
  
</details>

<details>
  <summary>Specificity</summary>
  
*this example taken from [Chris Coyier's](https://css-tricks.com/author/chriscoyier/) article [Specifics on CSS Specificity](https://css-tricks.com/specifics-on-css-specificity/)*

![specificity-calculationbase_rhrovi](https://user-images.githubusercontent.com/11747875/141937727-07286bb4-1909-4913-ab47-57a7c28e6f8f.png)
  
</details>


<details>
  <summary>Simple Grid Layout in CSS Grid</summary>
  
  ```html
<style>
  .item1{background:LightSkyBlue;}
  .item2{background:LightSalmon;}
  .item3{background:PaleTurquoise;}
  .item4{background:LightPink;}
  .item5{background:PaleGreen;}
  .item6{background:Yellow;}

  .container {
    font-size: 40px;
    min-height: 300px;
    width: 100%;
    background: LightGray;
    display: grid;
  /*this sets fractional relationship a column takes.  For example, 1 fr 2fr 1fr would mean the center column is twice as wide as the side columns. */
    grid-template-columns: 1fr 1fr 1fr;
  /*this sets fractional relationship a row takes.  For example, 1 fr 2fr 1fr would mean the center column is twice as wide as the side rows. */
    grid-template-rows: 1fr 1fr 1fr;
  /*this sets the gap between the columns */
    grid-gap: 10px;
  /*this defines the order of the template area.  Note, having the same name repeat vertically or horizontally shows it spans the entire area  */
    grid-template-areas:
      "header header header"
      "content content content"
      "footer footer footer";
  }
</style>

<div class="container">
  <div class="item1">1</div>
  <div class="item2">2</div>
  <div class="item3">3</div>
  <div class="item4">4</div>
  <div class="item5">5</div>
  <div class="item6">6</div>
</div>
```

</details>


# React


<details>
  <summary>Adding React to Development</summary>

  *this source comes from the [React Docs](https://reactjs.org/docs/add-react-to-a-website.html).*


```html 
<!--these first two scripts add the development version of react 
  <script src="https://unpkg.com/react@17/umd/react.development.js" crossorigin></script>
  <script src="https://unpkg.com/react-dom@17/umd/react-dom.development.js" crossorigin></script>

  <!-- replace the "like_button.js" with the file name of the JS file where your React is written. -->
  <script src="like_button.js"></script>
```
  
</details>


<details>
  <summary>Adding React to Production</summary>

  ```html
<!--add these scripts to the bottom of the page -->
<script src="https://unpkg.com/react@17/umd/react.production.min.js" crossorigin></script>
<script src="https://unpkg.com/react-dom@17/umd/react-dom.production.min.js" crossorigin></script>
```
  
</details>

<details>
  <summary>Adding React with JSX</summary>
  
```html
<!--add this script to the bottom of the page -->
<script src="https://unpkg.com/babel-standalone@6/babel.min.js"></script>
```
  
</details>

<details>
  <summary>Pass an Array using Props</summary>

  ```javascript
  
const List = props => {
  //notice that when we define the variable we define the actions taken on it.  Also .tasks must match a tasks added when the element is rendered
  return <p>{props.tasks.join(", ")}</p>;
};

class ToDo extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    return (
      <div>
        <h1>To Do Lists</h1>
        <h2>Today</h2>
        //notice the array is surrounded by {}
        <List tasks={["Walk", "Cook", "Bake"]} />
        <h2>Tomorrow</h2>
        <List tasks={["Study", "Code", "Eat"]} />
      </div>
    );
  }
}

```
  
</details>


# ADA Considerations 

*taken from [MDN: CSS and JavaScript accessibility best practices](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/CSS_and_JavaScript)*

<details>
  <summary>Abbreviation</summary>
  
  
```html

<p>Web content is marked up using <abbr title="Hypertext Markup Language">HTML</abbr>.</p>

```
  
  The recognized styling convention for abbreviations is a dotted underline, and it is unwise to significantly deviate from this. For more on abbreviations, 
  
</details>


<details>
  <summary>Emphasized Text</summary>
  
  ```html
<p>The water is <em>very hot</em>.</p>

<p>Water droplets collecting on surfaces is called <strong>condensation</strong>.</p>
```

</details>

<details>
  <summary>Links</summary>
  
```html

<p>Visit the <a href="https://www.mozilla.org">Mozilla homepage</a>.</p>

```
  
  The standard link conventions are underlined and a different color (default: blue) in their standard state, another color variation when the link has previously been visited (default: purple), and yet another color when the link is activated (default: red). In addition, the mouse pointer changes to a pointer icon when links are moused over, and the link receives a highlight when focused (e.g. via tabbing) or activated. The following image shows the highlight in both Firefox (a dotted outline) and Chrome (a blue outline):


You can be creative with link styles, as long as you keep giving users feedback when they interact with the links. Something should definitely happen when states change, and you shouldn't get rid of the pointer cursor or the outline — both are very important accessibility aids for those using keyboard controls.

### Hiding content

There are many instances where a visual design will require that not all content is shown at once. For example, in our Tabbed info box example (see source code) we have three panels of information, but we are positioning them on top of one another and providing tabs that can be clicked to show each one (it is also keyboard accessible — you can alternatively use Tab and Enter/Return to select them).


Screen reader users don't care about any of this — they are happy with the content as long as the source order makes sense, and they can get to it all. Absolute positioning (as used in this example) is generally seen as one of the best mechanisms of hiding content for visual effect, because it doesn't stop screen readers from getting to it.

On the other hand, you shouldn't use visibility:hidden or display:none, because they do hide content from screen readers. Unless of course, there is a good reason why you want this content to be hidden from screen readers.

</details>


<details>
  <summary>Accessibility Checklist</summary>
  
  *from [ADA Best Practices Tool Kit for State and Local Governments, Chapter 5 Addendum: Title II Checklist](https://www.ada.gov/pcatoolkit/chap5chklist.htm)
  
  [ ] Does the top of each page with navigation links have a “skip navigation” link? (This feature directs screen readers to bypass the row of navigation links and start at the webpage content, thus enabling people who use screen readers to avoid having to listen to all the links each time they move to a new page.)

[ ] Do all links have a text description that can be read by a screen reader (not just a graphic or “click here”)?

[ ] Do all of the photographs, maps, graphics and other images on the website currently have HTML tags (such as an “alt” tag or a long description tag) with text equivalents of the material being visually conveyed?

[ ] Are all of the documents posted on your website available in HTML or another text-based format (for example, rich text format (RTF) or word processing format), even if you are also providing them in another format, such as Portable Document Format (PDF)?

[ ]  If your website has online forms, do HTML tags describe all of the controls (including all text fields, check boxes, drop-down lists, and buttons) that people can use in order to complete and submit the forms?

[ ]  If your website has online forms, does the default setting in drop-down lists describe the information being requested instead of displaying a response option (e.g., “your age” instead of “18 - 21”)?

[ ] If a webpage has data charts or tables, is HTML used to associate all data cells with column and row identifiers?

[ ]   Do all video files on your website have audio descriptions of what is being displayed to provide access to visually conveyed information for people who are blind or have low vision?

[ ]  Do all video files on your website have written captions of spoken communication synchronized with the action to provide access to people who are deaf or hard of hearing?

[ ] Do all audio files on your website have written captions of spoken communication synchronized with the action to provide access to people who are deaf or hard of hearing?

[ ] Have all webpages been designed so they can be viewed using visitors’ web browser and operating system settings for color and font?

*Website Accessibility Policy and Procedures*

*This section will help you identify potential problems with the ongoing process of
ensuring website accessibility*

[ ]  Do you have a written policy on website accessibility?

[ ] Is the website accessibility policy posted on your website in a place where it can be easily located?

[ ] Have procedures been developed to ensure that content is not added to your website until it has been made accessible?

[ ]  Does the website manager check the HTML of all new webpages to confirm accessibility before the pages are posted?

[ ]  When documents are added to your website in PDF format, are text-based versions of the documents (e.g., HTML, RTF, or word processing format) added at the same time as the PDF versions?

[ ] Have in-house staff and contractors received information about the website accessibility policy and procedures to ensure website accessibility?


[ ] Have in-house and contractor staff received appropriate training on how to ensure the accessibility of your website?

[ ]  Have in-house and contractor staff who create web content or post it on your website received copies of the Department of Justice’s technical assistance document “Accessibility of State and Local Government Websites to People with Disabilities”?

[ ]  If your website contains inaccessible content, is a specific written plan including timeframes in place now to make all of your existing web content accessible?


[ ] Have you posted on your website a plan to improve website accessibility and invited suggestions for improvements?


[ ] Does your website home page include easily locatable information, including a telephone number and email address, for use in reporting website accessibility problems and requesting accessible services and information?


[ ] Do you have procedures in place to assure a quick response to website visitors with disabilities who are having difficulty accessing information or services available via the website?

[ ] Have you asked disability groups representing people with a wide variety of disabilities to provide feedback on the accessibility of your website? (Note: Feedback from people who use a variety of assistive technologies is helpful in ensuring website accessibility.)

[ ] Have you tested your website using one of the products available on the Internet to test website accessibility? (Note: Products available for testing website accessibility include no-cost and low-cost options. These products may not identify all accessibility issues and may flag issues that are not accessibility problems. However, they are, nonetheless, a helpful tool in improving website accessibility.)

[ ] Are alternative ways of accessing web-based information, programs, activities, and services available for people with disabilities who cannot use computers?

</details>









