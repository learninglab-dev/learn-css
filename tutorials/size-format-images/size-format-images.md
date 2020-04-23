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
