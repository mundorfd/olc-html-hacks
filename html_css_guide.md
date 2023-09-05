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

Now when you click on any of the list items, it will append the `#id` to the end of the current URL, and scroll the page to the corresponding `id`. This will work on **any** page you copy the HTML into, and is why we did not add a full link with `https://...`!

### Aligning the first image with `figcaption`
Our next step involves a few different steps. Let's decompose the problem:

1. Use HTML elements `figure` and `figcaption` to combine the image and its caption into one block.
2. Align the image to the right using the `float` CSS property.

Essentially, we are going from this:

```html
<p><img src="https://canvas.oregonstate.edu/courses/1941713/files/98401295/preview" alt="camellia sinensis" width="249" height="302" data-api-endpoint="https://canvas.oregonstate.edu/api/v1/courses/1941713/files/98401295" data-api-returntype="File" /></p>
<p><span style="font-size: 10pt;">Photo: Tea plant <em>(Camellia sinensis) </em>from K&ouml;hler's Medicinal Plants, 1897. Source: <a class="inline_disabled" href="https://en.wikipedia.org/wiki/File:Camellia_sinensis_-_K%C3%B6hler%E2%80%93s_Medizinal-Pflanzen-025.jpg" target="_blank" rel="noopener">Wikimedia Commons, Public Domain.</a></span></p>
```

To this:

```html
    <figure style="width: 25%; float: right; margin-bottom: 10px; margin-left: 30px;"><img src="https://canvas.oregonstate.edu/courses/1941713/files/98401295/preview" alt="camellia sinensis" width="249" height="302" data-api-endpoint="https://canvas.oregonstate.edu/api/v1/courses/1941713/files/98401295" data-api-returntype="File" />
        <figcaption><span style="font-size: 10pt;">Photo: Tea plant <em>(Camellia sinensis) </em>from K&ouml;hler's Medicinal Plants, 1897. Source: <a class="inline_disabled" href="https://en.wikipedia.org/wiki/File:Camellia_sinensis_-_K%C3%B6hler%E2%80%93s_Medizinal-Pflanzen-025.jpg" target="_blank" rel="noopener">Wikimedia Commons, Public Domain.</a></span></figcaption>
    </figure>
```

The changes required are simpler than they look:

* Replace outer `<p>` tags with `<figure>` tags
* Replace inner `<p>` tags with `<figcaption>` tags
* Add required inline CSS to the initial `<figure>`, which will position it to the right.

For this demonstration, we have added the following styles to the `<figure>` tag: 

```css
width: 25%;
float: right;
margin-bottom: 10px;
margin-left: 30px;
```
1. The `width` property sets the **maximum** width that the image can be.
2. The `float` property will place the element either to the left or right, allowing text to wrap around it.
3. The `margin-bottom` and `margin-left` properties will set margin areas on the bottom and left. You can also use the shorthand `margin` property, which will set a margin area on the top, right, bottom and left (in that order). So 0 on the top, 0 on the right, 10 pixels on the bottom, and 30 pixels on the left. This would have the same effect as setting each up manually, like this: `margin-bottom: 10px; margin-left: 30px;`

> [!NOTE]
> Margins, and properties like this, go clockwise around the element, starting from the top.

![New Float Right](assets/new_float_right.png)

### Align the second image
Aligning the second image works in much the same way, only this time we are going to `float` it to the left instead of the right:
```html
<figure style="width: 40%; float: left; margin: 0 30px 10px 0;"><img src="https://canvas.oregonstate.edu/courses/1941713/files/98401296/preview" alt="Four types of tea" width="381" height="230" data-api-endpoint="https://canvas.oregonstate.edu/api/v1/courses/1941713/files/98401296" data-api-returntype="File" />
        <figcaption><span style="font-size: 10pt;">Photo: Teas of different levels of oxidation (left to right): green, yellow, oolong, and black. Source: <a class="inline_disabled" href="https://en.wikipedia.org/wiki/File:Tea_in_different_grade_of_fermentation.jpg" target="_blank" rel="noopener">Wikimedia Commons, Public Domain.</a></span></figcaption>
    </figure>
```

The CSS settings for this are:

```css
width: 40%;
float: left;
margin: 0 30px 10px 0;
```

So a maximum width of 40%, floating the image to the left, and a margin of 0 on the top, 30 pixels on the right, 10 pixels on the bottom, and 0 pixels on the left.


![New Float Left](assets/new_float_left.png)

### Adding inline styles
Without any additional styling, elements like headings or paragraphs will have whatever the default styles are from the `styles.css` file. As we cannot edit this, we need to continue adding our styles "inline" if we want to apply things like font changes, backgrounds, and borders.

#### Styling Heading 2
Let's style the `h2` elements so they stand out. We are going to make the following changes:

1. Change font color to white (there are many ways to do this, but the quickest is to use the hexidecimal code for white, which is #ffffff).
2. Add a dark green background color to the entire element (using hex code #004225).
3. Change the font-size to `18pt`.
4. Add a margin to the top of 50 pixels.
5. Add a margin to the bottom of 20 pixels.
6. Add additional padding around the text of the element of 7 pixels. (This will push the text 7 pixels out in either direction).

The CSS for this would be:
```css
color: #ffffff;
background-color: #004225;
font-size: 18pt;
margin-top: 50px;
margin-bottom: 20px;
padding: 7px;
```

> [!NOTE]
> Steps 4 and 5 could be combined by using the `margin` shorthand property as we have done above. In this case, it would be `margin: 50px 0 20px 0;` 

One of our new `h2` elements will now look like this:

```html
<h2 id="whatis" style="color: #ffffff; background-color: #004225; font-size: 18pt; margin-top: 50px; margin-bottom: 20px; padding: 7px;">What is tea?</h2>
```

![New Heading 2 Style](/assets/new_heading2.png)

#### Styling "Did you know?" paragraph
We want to call attention to the "Did you know?" paragraph. Let's set another font color, give it a background color, some additional padding and margins to move it to the center, and a line at the top using the `border-top` property to show a greater degree of separation from the main text:

```css
color: #2d3b45;
background-color: #fefefa;
padding: 10px;
margin: 30px 7% 0 7%;
border-top: 3px solid #b2b2af;
```

So now the paragraph's HTML looks like this:

```html
<p style="color: #2d3b45; background-color: #fefefa; padding: 10px; margin: 30px 7% 0 7%; border-top: 3px solid #b2b2af;">Did you know? Although health benefits of drinking tea have been assumed throughout the history, there is no high-quality evidence showing that tea consumption gives significant benefits other than possibly increasing alertness, an effect caused by caffeine in the tea leaves.</p>
```

![New "Did You Know?" Paragraph](/assets/new_did_you_know.png)

### Styling with `div`
The `div` tag is used to create a section in the HTML document, or to contain elements for styling purposes. Let's use them to style the page.

#### Wrapping a `div` around the entire page
At OSU Ecampus, we like to limit the maximum width a page can have. This provides a cleaner look on Canvas. You can set this to anything you want, or simply not include it at all if you would like your page content to extend to the maximum width of the user's web browser window.

Start by going all the way to the top of the HTML, and adding the following:

```html
<div style="max-width: 1000px;">
```

Then, at the very end of the document, close the `div` with 

```html
</div>
```

Your page should now look something like this:

```html
<div style="max-width: 1000px;">
   [ALL THE CONTENT!]
</div>
```

What this small change has done is limit the maximum width of the content to 1000 pixels. No matter how wide the web browser window, the content will not exceed 1000 pixels in width.

#### Adding `div` for intro section
We can also use `div` tags to style entire sections of the page. Let's style all of our Introduction section in one go by wrapping it with a `div`:

As before, we can break down the requirements for our Introduction section. It should have:

1. A set font color.
2. A new background color.
3. A full border on all sides.
4. Some padding to give the content some space away from the edge of the border.

The CSS for this would be:

```css
color: #2d3b45;
background-color: #fefefa;
border: 1px solid #b2b2af;
padding: 10px 20px 10px 20px;
```

Then we just add it to our Introduction section by creating the `div` container with the styles:
```html
 <div style="color: #2d3b45; background-color: #fefefa; border: 1px solid #b2b2af; padding: 10px 20px 10px 20px;">
```

And close at the end of the Introduction section:

```html
</div>
```

So now the entire introduction section is separated from the rest of the page with a container, which is styled using our chosen colors and border:

```html
 <div style="color: #2d3b45; background-color: #fefefa; border: 1px solid #b2b2af; padding: 10px 20px 10px 20px;">
        <blockquote>
            <p>&ldquo;I say let the world go to hell, but I should always have my tea.&rdquo; ― Fyodor Dostoevsky, Notes from Underground</p>
        </blockquote>
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
        <a href="#consumed"> </a>
    </div>
```

![New Intro Section](/assets/new_intro_section.png)

### Working with classes
If you have access to the stylesheet of a website, it is easier to create 'classes' that can be applied to elements rather than manaully adding inline CSS. Some classes are already available for you on certain Learning Management Systems. 

#### Changing table styles by adding classes
Let's apply some classes to the `<table>` on Canvas. To get the effect we have here, we are going to use the follwing classes:

* `ic-Table`
* `ic-Table--striped`:  produces a striped table among rows in the table body.
* `ic-Table--hover-row`: highlights the row the user's cursor is currently hoving over.

This results in the following large block of HTML:

```html
   <table class="ic-Table ic-Table--striped ic-Table--hover-row" style="border-collapse: collapse; width: 52.6913%; height: 306px; margin-left: auto; margin-right: auto;" border="1">
        <caption>Tea consumption ranking</caption>
        <tbody>
            <tr style="height: 26px;">
                <th style="width: 11.3756%; text-align: left; height: 26px;" scope="col">Rank</th>
                <th style="width: 24.8694%; text-align: left; height: 26px;" scope="col">Country</th>
                <th style="width: 63.683%; height: 26px;" scope="col">Annual tea consumption per capita (lbs)</th>
            </tr>
            <tr style="height: 28px;">
                <td style="width: 11.3756%; height: 28px;">1</td>
                <td style="width: 24.8694%; height: 28px;">Turkey</td>
                <td style="width: 63.683%; text-align: center; height: 28px;">6.96</td>
            </tr>
            <tr style="height: 28px;">
                <td style="width: 11.3756%; height: 28px;">2</td>
                <td style="width: 24.8694%; height: 28px;">Ireland</td>
                <td style="width: 63.683%; text-align: center; height: 28px;">4.83</td>
            </tr>
            <tr style="height: 28px;">
                <td style="width: 11.3756%; height: 28px;">3</td>
                <td style="width: 24.8694%; height: 28px;">United Kingdom</td>
                <td style="width: 63.683%; text-align: center; height: 28px;">4.28</td>
            </tr>
            <tr style="height: 28px;">
                <td style="width: 11.3756%; height: 28px;">4</td>
                <td style="width: 24.8694%; height: 28px;">Pakistan</td>
                <td style="width: 63.683%; text-align: center; height: 28px;">3.30</td>
            </tr>
            <tr style="height: 28px;">
                <td style="width: 11.3756%; height: 28px;">5</td>
                <td style="width: 24.8694%; height: 28px;">Iran</td>
                <td style="width: 63.683%; text-align: center; height: 28px;">3.30</td>
            </tr>
            <tr style="height: 28px;">
                <td style="width: 11.3756%; height: 28px;">6</td>
                <td style="width: 24.8694%; height: 28px;">Russia</td>
                <td style="width: 63.683%; text-align: center; height: 28px;">3.05</td>
            </tr>
            <tr style="height: 28px;">
                <td style="width: 11.3756%; height: 28px;">7</td>
                <td style="width: 24.8694%; height: 28px;">Morocco</td>
                <td style="width: 63.683%; text-align: center; height: 28px;">2.68</td>
            </tr>
            <tr style="height: 28px;">
                <td style="width: 11.3756%; height: 28px;">8</td>
                <td style="width: 24.8694%; height: 28px;">New Zealand</td>
                <td style="width: 63.683%; text-align: center; height: 28px;">2.63</td>
            </tr>
            <tr style="height: 28px;">
                <td style="width: 11.3756%; height: 28px;">9</td>
                <td style="width: 24.8694%; height: 28px;">Chile</td>
                <td style="width: 63.683%; text-align: center; height: 28px;">2.62</td>
            </tr>
            <tr style="height: 28px;">
                <td style="width: 11.3756%; height: 28px;">10</td>
                <td style="width: 24.8694%; height: 28px;">Egypt</td>
                <td style="width: 63.683%; text-align: center; height: 28px;">2.23</td>
            </tr>
        </tbody>
    </table>
```


#### Adding grid-row to align the first country section with its image
One of the most common ways to align content on a page is to use a table, the make the borders invisible. This usually results in the intended layout, but is not very accessible, nor a responsive solution for multiple screen sizes. Instead, there are many ways to change the layout of the page using frameworks and tools that Canvas has directly integrated, such as Bootstrap and Flexbox.

Canvas has its own implementation of Flexbox using the `.grid-row` class, and so we will use this to position the images and text in the section about different countries and their tea-drinking styles.

> [!NOTE]
> On Canvas, we are going to use the `grid-row` class, as this is a custom interpretation of a grid layout modified by Instructure. The regular form of this is just `row`.

Open a new `div` container, but instead of just using a `style` attribute, we are going to use a `class` attribute as well:

```html
<div class="grid-row" style="margin-top: 30px; margin-bottom: 50px;">
[...]
</div>
```

##### Background info
Now, let's explain quickly what this does. The `grid-row` class will split all content inside the container into 12 equal columns (or parts if it's easier to picture). You can then choose how much of the 12 columns you want each row in the grid to take up. You can also change these based on the screen size. So perhaps you want all 12 parts of a row to be given to one image on a mobile device, but on a larger screen, you want two images to occupy that space.

The following screen sizes can be applied to the above flex item classes. You can decide if you would like to make visual adjustments to each kind of screen size available.

| Identifier  | Screen Size |
| ------------- | ------------- |
| xs  | Extra Small  |
| sm  | Small  |
| md | Medium |
| lg | Large  |

Inside our first `div`, we can add more `div` containers with the screen sizes and column/part allocation. For example:

```html
<div class="col-xs-12 col-md-4">
[The content goes here!]
</div>
```

Let's say you wanted to make 3 columns with text and images inside them. When someone views it on laptop/desktop, you would like the columns to be next to each other horizontally. When someone looks at it from a mobile device, however, you would want the columns to stack vertically. We can use this using 3 instances of this class: `<div class="col-xs-12 col-md-4">`. What this is telling the browser is that on an 'xs' or extra small screen, the column takes up all 12 of the allocated 12 parts. On a 'md', or medium screen, it will only take up 4 of the twelve (remember that we wanted 3 columns and so ). Setting it to 12 in extra small screens like phones will vertically stack all columns within this container as they are set to utilize every part of the screen, not just 4 parts of it as with the medium screen size.

```html
<div class="grid-row" style="margin-top: 30px; margin-bottom: 50px;">
  <div class="col-xs-12 col-md-4">
    [The content goes here!]
  </div>
  <div class="col-xs-12 col-md-4">
    [The content goes here!]
  </div>
  <div class="col-xs-12 col-md-4">
    [The content goes here!]
  </div>
</div>
```

And what would happen here is that on an extra small screen like a mobile device, the content would be seperated onto 3 rows. However, on a medium screen size and above, all of that content would be on one row, because the first one takes up 4 parts, the next one takes up 4 parts, and the final one takes up 4 parts. 4 + 4 + 4 = 12, and so that is the size of one row. If you changed one of them from `col-md-4` to `col-md-5`, we would get 13, and anything over 12 is pushed onto the next row.

##### Back to the demo
On our site, we are going to make each row uneven, as this gives more room for the images over the text.

```html
    <div class="grid-row" style="margin-top: 30px; margin-bottom: 50px;">
        <div class="col-xs-12 col-lg-5">
            <h3>China and Japan</h3>
            <p>The Chinese and Japanese tea ceremonies traditions employ certain techniques and ritualized protocol of brewing and serving tea for enjoyment in a refined setting. &nbsp;All of these tea ceremonies and rituals contain "an adoration of the beautiful among the sordid facts of everyday life", as well as refinement, an inner spiritual content, humility, restraint and simplicity.</p>
        </div>
        <div class="col-xs-12 col-lg-7">
            <p><img src="https://canvas.oregonstate.edu/courses/1941713/files/98401297/preview" alt="Tea ceremony" width="500" height="333" data-api-endpoint="https://canvas.oregonstate.edu/api/v1/courses/1941713/files/98401297" data-api-returntype="File" /></p>
        </div>
    </div>
    <div class="grid-row" style="margin-top: 30px; margin-bottom: 50px;">
        <div class="col-xs-12 col-lg-5">
            <h3>UK</h3>
            <p>In the United Kingdom, 63% of people drink tea daily. It is customary for a host to offer tea to guests soon after their arrival. Tea is consumed both at home and outside the home, often in caf&eacute;s or tea rooms. Afternoon tea with cakes on fine porcelain is a cultural stereotype.</p>
        </div>
        <div class="col-xs-12 col-lg-7">
            <p><img src="https://canvas.oregonstate.edu/courses/1941713/files/98401298/preview" alt="Old school style tea set with cakes" width="503" height="336" data-api-endpoint="https://canvas.oregonstate.edu/api/v1/courses/1941713/files/98401298" data-api-returntype="File" /></p>
        </div>
    </div>
    <div class="grid-row" style="margin-top: 30px; margin-bottom: 50px;">
        <div class="col-xs-12 col-lg-5">
            <h3>Russia</h3>
            <p>Russia has a long, rich tea history dating to 1638 when tea was introduced to Tsar Michael. Russian tea is brewed and can be served sweet, and hot or cold. It is traditionally taken at afternoon tea, but has since spread as an all day drink, especially at the end of meals, served with dessert. Social gatherings were considered incomplete without tea, which was traditionally brewed in a samovar.&nbsp;</p>
        </div>
        <div class="col-xs-12 col-lg-7">
            <p><img src="https://canvas.oregonstate.edu/courses/1941713/files/98401299/preview" alt="Traditional Russian tea with samovar" width="501" height="427" data-api-endpoint="https://canvas.oregonstate.edu/api/v1/courses/1941713/files/98401299" data-api-returntype="File" /></p>
        </div>
    </div>
    <div class="grid-row" style="margin-top: 30px; margin-bottom: 50px;">
        <div class="col-xs-12 col-lg-5">
            <h3>India</h3>
            <p>Indian tea culture is strong; the drink is the most popular hot beverage in the country. It is consumed daily in almost all houses, offered to guests, consumed in high amounts in domestic and official surroundings, and is made with the addition of milk with or without spices, and usually sweetened. It is sometimes served with biscuits to be dipped in the tea and eaten before consuming the tea.&nbsp;</p>
        </div>
        <div class="col-xs-12 col-lg-7">
            <p><img src="https://canvas.oregonstate.edu/courses/1941713/files/98401300/preview" alt="Pouring Indian tea with milk and spices from a ceramic teapot" width="500" height="333" data-api-endpoint="https://canvas.oregonstate.edu/api/v1/courses/1941713/files/98401300" data-api-returntype="File" /></p>
        </div>
    </div>
    <div class="grid-row" style="margin-top: 30px; margin-bottom: 50px;">
        <div class="col-xs-12 col-lg-5">
            <h3>Burma</h3>
            <p>In Burma (Myanmar), tea is consumed not only as hot drinks, but also as sweet tea and green tea known locally as laphet-yay and laphet-yay-gyan, respectively. Pickled tea leaves, known locally as lahpet, are also a national delicacy. Pickled tea is usually eaten with roasted sesame seeds, crispy fried beans, roasted peanuts and fried garlic chips.</p>
        </div>
        <div class="col-xs-12 col-lg-7">
            <p><img src="https://canvas.oregonstate.edu/courses/1941713/files/98401301/preview" alt="Traditional Burmese Lahpet salad, made out of fermented tea leaves, served with nuts, beans and sprouts." width="500" height="331" data-api-endpoint="https://canvas.oregonstate.edu/api/v1/courses/1941713/files/98401301" data-api-returntype="File" /></p>
        </div>
    </div>
```

## Challenges 
The following challenges are available to test what you know! Choose the level that is right for you.

### HTML/CSS is new to you
If you have never edited HTML and CSS before, try this challenge:

### Experienced with HTML/CSS
If you're a little more experienced with HTML and CSS, try this challenge:

## Resource List
1. [W3Schools HTML Elements Reference](https://www.w3schools.com/tags/tag_div.ASP)
2. [W3Schools HTML class Attribute](https://www.w3schools.com/html/html_classes.asp)
3. [Bootstrap](https://getbootstrap.com)
4. [Flexbox Grid](http://flexboxgrid.com)
