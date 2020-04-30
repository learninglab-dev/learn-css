# Setup

This setup will get you started on these tutorials using either sample boilerplate HTML or any existing HTML document. If you're working the LL `the-resources` repo and are styling markdown, checkout this [setup guide](./resources-setup.md) instead!

## Project Directory

The simplest way to connect your HTML and your styles is to put both in the same folder. A sample structure could look something like this:
```
myProject/
  -- styles.css
  -- tutorial.html
```
So, you might start by creating a folder with these blank `.css` and `.html` files. You can name them whatever you like, so long as you have one file with each extension.

If you're working with existing HTML, just make sure you've got a `.css` file in the same directory.

You can write HTML and CSS in just about any text editor. At the LL, we typically use [Atom](https://atom.io/), but you can experiment with many free editors.

## HTML

Next, you'll want to add some basic structure to your HTML file. Paste the following HTML into your `.html`. This just tells the browser to parse this document as HTML, what the page title is (feel free to change this to whatever you like), where to find the stylesheet (make sure that the file name after `href` here matches what you named your css file), and what character set we're using.  

```HTML
!DOCTYPE html>
<html>
  <head>
    <title>Boilerplate Tutorial HTML</title>
    <link rel="stylesheet" href="styles.css">
    <meta charset="utf-8">
  </head>
  <body>
    // Specific html for each tutorial goes here.
  </body>
</html>
```
If you're working with your own HTML, don't change anything. You just need to make sure this link to the stylesheet is inside your `<head></head>` tag:
```html
<link rel="stylesheet" href="styles.css">
```
Each individual tutorial will specify a few required HTML elements that that tutorial will help you style. For example, the required HTML for [center-text-on-image](../tutorials/center-text-on-image/center-text-on-image.md) looks like this:
```html
<div id="backgroundImg">
  <h1>My Title</h1>
  <h3>my subtitle</h3>
</div>
```
You'll paste this HTML inside the `<body></body>` tags of your document, if you're starting from scratch. If you're using your own, you'll just want to make sure your HTML document includes at least one set of elements of this structure.

## CSS

If you created a blank `styles.css` earlier, you're all set to start writing CSS!

You're also free to add any additional CSS, either that you found from a template online or that you've already written here to supplement what's in the tutorials.

## Viewing your Work

To view your work, simply navigate to the .html file using your computer's file browser (Finder, on a Mac) and open it up.  The file will open up as a page in your internet browser!  You can view changes you've made to the page by refreshing the page after you've saved a new addition to your .html or .css documents.
