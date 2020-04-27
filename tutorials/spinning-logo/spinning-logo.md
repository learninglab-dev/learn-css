# Spinning Logo

This tutorial will show you how to make a logo or image spin. It's mainly just for fun, but it does give a little taste of CSS animations.

## Required HTML

If you haven't already checked out the [Setup](../basics/setup.md) guide, go there first! This is one of the tutorials that requires that you interact with some HTML directly. Basically, we just need a way of tagging particular image we want to spin, so you'll need this tag either in your HTML or in your markdown:

```html
<img id="spinning" src="[PATH TO YOUR IMAGE]" alt="spinning image" />
```
&nbsp;

### CSS Animations

Vanilla CSS can actually create quite a few animations! It does so using [keyframes](https://www.w3schools.com/cssref/css3_pr_animation-keyframes.asp), which might be familiar if you've worked with animations in other programs. So let's start by adding some keyframes to our `styles.css`:

```css
@keyframes logo-spin {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}
```
Let's unpack this a bit. It looks pretty weird compared to the CSS we've encountered in earlier tutorials!
