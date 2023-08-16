# Step by Step Guide and Resources List
> [!IMPORTANT]
> Make sure to write any new HTML/CSS in a text editor of your choice, and then copy into Canvas. This is in case you make a mistake and Canvas deletes everything you just made!

## Fixing List Numbers
We need to continue the ordered list from where the previous one left off. Let's tell it to start from the number **4**.

Add `start="4"` to the opening `<ol>` tag.

```html
<ol start="4">
```
## Adding IDs to elements

## Adding Anchor Links

## Aligning the first image with `figcaption`

## Align the second image

## Adding inline styles

### Styling Heading 2

### Styling "Did you know?" paragraph

## Wrapping a `div` around the entire page

## Adding `div` for intro section

## Adding grid-row to align the first country section with its image

## Changing width and height of frame elements (YouTube)
Let's change the following frame:

```html
<p><iframe title="YouTube video player" src="https://www.youtube.com/embed/LaLvVc1sS20" width="560" height="315" allowfullscreen="allowfullscreen" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"></iframe></p>
```

<p><iframe title="YouTube video player" src="https://www.youtube.com/embed/LaLvVc1sS20" width="560" height="315" allowfullscreen="allowfullscreen" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"></iframe></p>


Let's make the width take up 100% of the screen:

```
 <p><iframe title="YouTube video player" src="https://www.youtube.com/embed/LaLvVc1sS20" width="100%" height="500" allowfullscreen="allowfullscreen" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"></iframe></p>
```

 <p><iframe title="YouTube video player" src="https://www.youtube.com/embed/LaLvVc1sS20" width="100%" height="500" allowfullscreen="allowfullscreen" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"></iframe></p>



## Changing table styles by adding classes
If you have access to the stylesheet of a website, it is easier to create 'classes' that can be applied to elements rather than manaully adding inline CSS. Some classes are already available for you on certain Learning Management Systems. Let's apply some to the `<table>` on Canvas:
