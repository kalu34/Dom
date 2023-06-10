# Document Object Model (DOM)

HTML document is structured as a JavaScript Object. Every HTML element has a different properties which can help to manipulate it. It is possible to get, create, append or remove HTML elements using JavaScript. Check the examples below. Selecting HTML element using JavaScript is similar to selecting using CSS. To select an HTML element, we use tag name, id, class name or other attributes.

**Getting elements by tag name**

**ge*tElementsByTagName()***:takes a tag name as a string parameter and this method returns an HTMLCollection object. An HTMLCollection is an array like object of HTML elements. The length property provides the size of the collection. Whenever we use this method we access the individual elements using index or after loop through each individual items. An HTML Collection does not support all array methods therefore we should use regular for loop instead of forEach. 

// syntax
document.getElementsByTagName('tagname')

`const haeding_1 = document.getElementsByTagName('h1')`

`Const linkTag = document.getElementByTagName('a')

console.log(heading_1) //HTMLCollections
console.log(Heading_1.length) // 4

for (let i = 0; i < heading_1.length; i++) {
  console.log(heading_1[i]) // prints each elements in the HTMLCollection
}` 

`linkTag.style.text-decoration = 'none'`

**Getting elements by class name**

***getElementsByClassName()*** method returns an HTMLCollection object. An HTMLCollection is an array like list of HTML elements. The length property provides the size of the collection. It is possible to loop through all the HTMLCollection elements. See the example below

// syntax 

```jsx
const input = document.getElementsByClassName('input-text')

console.log(input-text) //HTMLCollections
console.log(input-text.length) // 4
```

**Getting an element by id**

***getElementsById()*** targets a single HTML element. We pass the id without # as an argument.lwt 

```jsx
let sectionIntro = document.getElementById('section_intro')
console.log(sectionInrro)

```

### Getting elements by using querySelector methods

The *document.querySelector* method can select an HTML or HTML elements by tag name, by id or by class name.

***querySelector***: can be used to select HTML element by its tag name, id or class. If the tag name is used it selects only the first element.

`let firstTitle = document.querySelector('h1') // select the first available h1 element
 let firstTitle = document.querySelector('#first-title') // select id with first-title
 let firstTitle = document.querySelector('.title') // select the first available element    with class title`

**Adding attribute**

**Adding attribute using setAttribute**

The ***setAttribute()*** method set any html attribute. It takes two parameters the type of the attribute and the name of the attribute. Let's add class and id attribute for the fourth title.

`const heading_1= document.querySelectorAll('h1')
heading_1[3].setAttribute('class', 'heading_1')
heading_1[3].setAttribute('id', 'section-title')`

### Adding attribute without setAttribute

We can use normal object setting method to set an attribute but this can not work for all elements. Some attributes are DOM object property and they can be set directly. For instance id and class

`//another way to setting an attribute
heading_1[3].className = 'heading_1'
heading_1[3].id = 'section-title'`

### Adding class using classList

The class list method is a good method to append additional class. It does not override the original class if a class exists rather it adds additional class for the element.

`//another way to setting an attribute: append the class, doesn't over ride
heading_1[3].classList.add('title', 'heading_1-title')`

### Removing class using remove

Similar to adding we can also remove class from an element. We can remove a specific class from an element.

`//another way to setting an attribute: append the class, doesn't over ride
heading_1[3].classList.remove('title', 'heading_1-title')`

### Adding Text to HTML element

An HTML is a build block of an opening tag, a closing tag and a text content. We can add a text content using the property *textContent* or *innerHTML.

### Adding Text content using textContent

The *textContent* property is used to add text to an HTML element.

`const heading_2= document.querySelectorAll('h2')
heading_2[3].textContent = 'Heading_2 Title is all about working Hard!!!'`

### Adding Text Content using innerHTML

Most people get confused between *textContent* and *innerHTML*. *textContent* is meant to add text to an HTML element, however innerHTML can add a text or HTML element or elements as a child.

### Text Content

We assign *textContent* HTML object property to a text

`const titles = document.querySelectorAll('h1')
titles[3].innerHTML= 'Fourth Title'`

### Adding style

### Adding Style Color

Let us add some style to our titles. If the element has even index we give it green color else red.

`const heading_1= document.querySelectorAll('h1')
titles.forEach((outtput_1, i) => { // an arrow Function is being used.
  output_1.style.fontSize = '16px' // all titles will have 16px font size
  if (i % 2 === 0) {
    title.style.color = 'yellow'
  } else {
    title.style.color = 'green'
  }
})`

### Adding Style Background Color

Let us add some style to our titles. If the element has even index we give it green color else red.

`const heading_All= document.querySelectorAll('h1')
heading_All.forEach((title, i) => {
  title.style.fontSize = '24px' // all titles will have 24px font size
  if (i % 2 === 0) { // if i is odd or even the function will change the background color 
    title.style.backgroundColor = 'yellow'
  } else {
    title.style.backgroundColor = 'red'
  }
})`

### 

### Appending child to a parent element

To see a created element on the HTML document we should append it to the parent as a child element. We can access the HTML document body using *document.body*. The *document.body* support the *appendChild()* method. See the example below.

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8" />
        <meta
            name="viewport"
            content="width=device-width, initial-scale=1.0"
        />
        <title>Document</title>
    </head>
    <body>
        <h1>Dom Manuplation Html code</h1>
        <script>
            let h2 = document.createElement("h2");
            h2.style.fontFamily = "poppins";
            h2.style.fontSize = "24px";
            h2.textContent = 'welcom to addis ababa New YOrk City'
            document.body.appendChild(h2)
            console.log(h2)
        </script>
    </body>
</html>
```