# Size and Format images

&nbsp;  
In this mini-tutorial we'll look at the CSS properties you can use to format the images on your page. In this tutorial, we'll work with images that are tagged as image elements `<img/>` in HTML. In the [next tutorial](../center-text-on-image/center-text-on-image.md), we'll show you how to use an image as a background.

In this tutorial we'll look at:
- [Sizing](#sizing)
- [Display](#display)
- [Borders](#borders)
- [Opacity](#opacity)
- [Filters](#filters)  

And for Bonus Points:
- [Hover Overlay](#hover-overlay)

As usual, here's a favorite [outside guide](https://www.w3schools.com/css/css3_images.asp) to image properties.

## Required HTML

If you haven't already checked out the [Setup](../basics/setup.md) guide, go there first! This is one of the tutorials that requires that you interact with some HTML directly. So, you should either have an HTML doc with a section that looks like this or else just paste this HTML directly into the markdown file you're working with wherever you'd like to see a customized image:

```html
<div id="imgHolder">
  <img id="customImg" src="[PATH TO YOUR IMAGE]" alt="my image" />
</div>
```
&nbsp;

## CSS Image Properties

All of the following code, or any of it that you choose to use, goes in your `styles.css` file. Note that in this mini-tutorial, there is no "final" product. Instead we'll try out a variety of image styles that you might want to use in your own projects.

&nbsp;

### Add Selectors

Before we can make any changes to our image, we need to add the relevant "selectors" to our `styles.css`. Selectors are what the HTML elements like `img` and `div` are called in CSS.  

In the demo HTML, we only have two elements. Note the we're identifying them by `id` here, so that we can style just the one image. If you have multiple images to style, assign them separate `id` values and then replicate this structure as many times as you have images:
```css
div#imgHolder {

}
img#customImg {

}
```
&nbsp;

### Sizing

The first thing you'll want to do is give your images a size. Note that images will not display _at all_ if you don't give them a size. In markdown, the parser that converts your markdown to HTML takes care of this for you by default, but if you're inserting an image using `<img />` size properties are required.

When sizing your images, you have a choice: Do you want to size your images **absolutely** or **responsively**? While you might think responsive is always the way to go, we might caution that this depends on whether your whole layout, or the relevant section of it, is responsive. Having just an image resize while everything else remains static might be less preferable than a user having to scroll around your layout if they're on a smaller screen.

So, to give your image an absolute size you can simply assign it a `width` and `height`:
```css
div#imgHolder {

}
img#customImg {
  width: 300px;
  height: auto;
}
```
Assigning `auto` to one dimension ensures that the aspect ratio of your image is maintained.

You might also size an image by sizing the `div` that contains it:
```css
div#imgHolder {
  width: 300px;
  height: 300px;
}
img#customImg {
  width: 100%;
  height: auto;
}
```
Here we've specified an absolute height on the container and then told our image to fill the whole width of the container.

If you want your image to size responsively, you can do using either relative units (`vw` stands for viewport width) or the `max-width` and `max-height` properties:
```css
div#imgHolder {

}
img#customImg {
  width: .5vw;
  height: auto;
}
```
```css
div#imgHolder {

}
img#customImg {
  max-width: 50%;
  height: auto;
}
```
&nbsp;

### Display

`display` is a, perhaps oddly named, but nonetheless essential property to know about when formatting images. It takes a few values, but the key ones are `inline` and `block`. Elements that are set as `block` start on a new line and fill the full width of the screen unless otherwise specified. Elements that are `inline` do not start on a new line and only take up as much width as is needed to display their content. By default, `<img />` is an inline element.

If you want you image to start on a new line, you'll want to set its `display` property:
```css
div#imgHolder {

}
img#customImg {
  width: 300px;
  height: auto;
  display: block
}
```
You can also use the properties `margin-left` and `margin-right` to adjust the placement of your image on the screen within the block.

&nbsp;

### Borders

Next, you might want to customize your image's border. This might involve putting a colored border around the image or just rounding the image's corners.

Use `border` to add a visible border around the image:
```css
div#imgHolder {

}
img#customImg {
  width: 300px;
  height: auto;
  display: block;
  margin-left: auto;
  margin-right: auto;
  border: 5px solid black;
}
```
`border` takes three values: a width, a style, and a color. You can find all the border style options [here](https://www.w3schools.com/css/css_border.asp). Most units are acceptable for size, and as we saw with text styling, colors can be specified by name for basic colors and by [hex code](https://www.google.com/search?q=color+picker) for all the rest.

Use `border-radius` to round the corners of your image:
```css
div#imgHolder {

}
img#customImg {
  width: 300px;
  height: auto;
  display: block;
  margin-left: auto;
  margin-right: auto;
  border: 5px solid black;
  border-radius: 25px;
}
```
Setting `border-radius` to `50%` will make your image round. You can also specify each corner individually to make asymmetric shapes: `border-radius: 25px 10px 15px 10px`

&nbsp;  

### Opacity

Opacity is just what it sounds like. The `opacity` property takes values from `0`, transparent, to `1.0`, full saturation.
```css
div#imgHolder {

}
img#customImg {
  width: 300px;
  height: auto;
  display: block;
  margin-left: auto;
  margin-right: auto;
  border: 5px solid black;
  border-radius: 25px;
  opacity: .75;
}
```
&nbsp;

### Filters

Finally, you can use the `filter` property to apply some basic visual effects. Note, however, we might recommend using a different software to edit your images directly rather than relying on the browser's application of these effects.
```css
div#imgHolder {

}
img#customImg {
  width: 300px;
  height: auto;
  display: block;
  margin-left: auto;
  margin-right: auto;
  border: 5px solid black;
  border-radius: 25px;
  filter: grayscale(100%);
}
```
`filter` takes the name of filter and then a percentage, e.g. `filter: contrast(200%)` or `filter: blur(10%)`
