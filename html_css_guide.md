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
