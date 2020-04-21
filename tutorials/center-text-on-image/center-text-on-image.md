# Center Text on an Image Using Flexbox

&nbsp;  
`Flexbox Layout` is a CSS module that allows you to control how items on your page are aligned in their respective containers. What's a container? Well, a simple way to think about it is as any HTML element that wraps around-- "contains"-- other elements. We'll use a `<div>` as our flex container in this mini-tutorial.

Here's a good [Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/), if you're interested in reading more!

---

### Required HTML

If you haven't already checked out the [Setup](../basics/setup.md) guide, go there first! This is one of the tutorials that requires that you interact with some HTML directly. So, you should either have an HTML doc with a section that looks like this or else just paste this HTML directly at the top of the markdown file you're working with:

```html
<div id="backgroundImg">
  <h1>My Title</h1>
  <h3>my subtitle</h3>
</div>
```
You'll also need a link to an image to use as your background. You can use [an LL flickr image](https://flickr.learninglab.xyz) if you don't have your own.

---

### The CSS

All of the following code goes in your `styles.css` file. Note that in steps 1-3 we're adding properties to the same "selector". Selector is the CSS term for tags like `h1` that identify elements on the page. In the end, you'll only have the final version of `div#backgroundImg` from step 3 in your stylesheet.

&nbsp;  
1. Add and size the background image:
```css
div#backgroundImg {
  background-image: url('./cards.jpg');
  background-size: cover;
  width: 100vw;
  height: 300px;
}
```
  - Using `cover` for the image size ensures that our image fills the entire `<div>` no matter the size of the user's screen.

&nbsp;  
&nbsp;  
2. Make the `<div>` containing the image a flexbox container oriented as a column:
```css
div#backgroundImg {
  background-image: url('./cards.jpg');
  background-size: cover;
  width: 100vw;
  height: 300px;
  display: flex;
  flex-direction: column;
}
```
  - We're using `column` here because we want our title and subtitle to stack on top of each other rather than spread out in a row.

&nbsp;  
&nbsp;  
3. Align the items in our flex column to center both vertically and horizontally:
```css
div#backgroundImg {
  background-image: url('./cards.jpg');
  background-size: cover;
  width: 100vw;
  height: 300px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
```
  - In flexbox `justify` deals with the primary axis, so in our case with a column the vertical one, while `align` sets the cross axis, in our case horizontal.

&nbsp;  
&nbsp;  
4. Set the font color on your title and subtitle so they're visible. On the sample image `white`, hex `#ffffff`, works well, but you can choose any color by finding its [hex color code](https://www.google.com/search?q=color+picker):
```css
h1 {
  color: white;
}
h3 {
  color: #ffffff;
}
```
That's it! Save your CSS file and open your HTML file in your browser.

---

### Result

![result](./result.png)
