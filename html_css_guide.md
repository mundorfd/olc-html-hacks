# Step by Step Guide and Resources List
> [!IMPORTANT]
> Make sure to write any new HTML/CSS in a text editor of your choice, and then copy into Canvas. This is in case you make a mistake and Canvas deletes everything you just made!

## Step by Step Guide

### Fixing List Numbers
We need to continue the ordered list from where the previous one left off. Let's tell it to start from the number **4**.

Add `start="4"` to the opening `<ol>` tag which comes after the 'Optional:' paragraph.

```html
<ol start="4">
```

### Adding `id` attributes to elements
Sometimes it is necessary to identify certain elements for styling or scripting purposes. To do this, we can add an identifer (or `id`) attribute to the element. These identifiers must be unique within the same HTML document. For this demonstration, we will use a unique `id` on the `h2` elements, so that once clicked, the list items in our linked list at the top moves the page to the corresponding section.

To do this, add `id=` and the unique identifier after the opening `h2` tag, as we have below:

```html
<h2 id="whatis">What is tea?</h2>
<h2 id="types">What are the main types of tea?</h2>
<h2 id="comefrom" </h2>
<h2 id="consumed"</h2>
```

Whatever you have used for your `id` attribute will be used later with the anchor element.

### Adding Anchor Links
Now that the `id` attributes have been added to our `h2` elements, we can return to the list at the top of the page and create the links. This is just like creating a hyperlink to another page, only we do not need to add any additional `https://...`! Instead, we are just going to use a `#` followed by the corresponding `id`. 

So inside the ordered list, we have:

```html
<ol>
    <li>What is tea?</li>
    <li>What are the main types of tea?</li>
    <li>Where does tea come from?</li>
</ol>
```
and

```html
<ol start="4">
    <li>How is tea consumed around the world?</li>
</ol>
```
We want to update the `li` parts of these so they link to our 4 headings. We can do this by replacing the first three `<li>` elements with the following:

```html
<li><a href="#whatis">What is tea?</a></li>
<li><a href="#types">What are the main types of tea?</a></li>
<li><a href="#comefrom">Where does tea come from?</a></li>
```

and (for 4th item):

```html
<li><a href="#consumed">How is tea consumed around the world?</a></li>
```

This will leave us with something like this:

```html
        <p>In this section, we'll talk about tea! Please review the following topics:</p>
        <ol>
            <li><a href="#whatis">What is tea?</a></li>
            <li><a href="#types">What are the main types of tea?</a></li>
            <li><a href="#comefrom">Where does tea come from?</a></li>
        </ol>
        <p>Optional:</p>
        <ol start="4">
            <li><a href="#consumed">How is tea consumed around the world?</a></li>
        </ol>
```

### Aligning the first image with `figcaption`

### Align the second image

### Adding inline styles

#### Styling Heading 2

#### Styling "Did you know?" paragraph

### Wrapping a `div` around the entire page

### Adding `div` for intro section

### Adding grid-row to align the first country section with its image

### Changing table styles by adding classes
If you have access to the stylesheet of a website, it is easier to create 'classes' that can be applied to elements rather than manaully adding inline CSS. Some classes are already available for you on certain Learning Management Systems. Let's apply some to the `<table>` on Canvas:


## Resource List
