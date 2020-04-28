# Spinning Logo

This tutorial will show you how to make a logo or image spin. It's mainly just for fun, but it does give a little taste of CSS animations.

## Required HTML

If you haven't already checked out the [Setup](../basics/setup.md) guide, go there first! This is one of the tutorials that requires that you interact with some HTML directly. Basically, we just need a way of tagging particular image we want to spin, so you'll need this tag either in your HTML or in your markdown:

```html
<img id="spinning" src="[PATH TO YOUR IMAGE]" alt="spinning image" />
```
&nbsp;

## CSS Animations

Vanilla CSS can actually create quite a few animations! One way it does so is using [keyframes](https://www.w3schools.com/cssref/css3_pr_animation-keyframes.asp), which might be familiar if you've worked with animations in other programs. So let's start by adding some keyframes to our `styles.css`:

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

### @keyframes
What does that @ sign mean in CSS? As you might guess, this is not a normal [selector](../intro-to-selectors/intro-to-selectors.md). We're not referencing an element in our HTML. Instead, @ indicates that we're defining a rule. In this case, the rule defines the steps, or keyframes, in the animation we're creating.

We specify those keyframes using either `from` (0%) and `to` (100%) or other percentages in between. Here, because we're rotating in a complete circle, we can just use `from` and `to`. All other points in the animation are part of the rotation from 0-360 degrees.

There are two other things to notice about the syntax here:
1. We gave our animation a name `logo-spin`. You can name your animations anything you like, but this is the name you'll use to apply your animation to an element.
2. Inside our `from {}` and `to {}` blocks we're calling `transform`. [Transform](https://developer.mozilla.org/en-US/docs/Web/CSS/transform) takes various functions as values, including `translate()` and `scale()`. Here we're using `rotate()` because we want our logo to turn. `rotate()` in turn (all puns intended) takes a value in degrees. After you've finished this mini-tutorial you might want to try replacing `rotate()` with another function or changing the number of degrees to get a better sense of how these transforms work.

### Using the Animation

Next add the following to your `styles.css`:

```css
#spinning {
  animation: logo-spin infinite 20s linear;
  display: block;
  margin: auto;
  width: 500px;
  height: auto;
}
```
This probably looks a little more familiar. You'll remember from our [images tutorial](../size-format-images/size-format-images.md) that setting an image to `display: block;` and `margin: auto;` centers it either on the page or in its parent container. Then we're using the property `animation` to of course set our animation.

`animation`takes [a number of values](https://developer.mozilla.org/en-US/docs/Web/CSS/animation). We're using four here:
1. `animation-name`: logo-spin
2. `animation-iteration-count`: infinite-- our animation never stops
3. `animation-duration`: 20s-- it takes 20s to complete one full rotation
4. `animation-timing-function`: linear-- the motion is at a consistent speed

That's it! Save your work and view the result:

![result](./assets/result.gif)
