# Boxes II: Flexbox

Much like `margin`, `display:inline` and `display:block` affect elements **outside** the element they are set on. Though conceptually important, their usefulness as layout tools is pretty limited—you can only accomplish so much compositionally by making rules to tell boxes when and how they're allowed to push other boxes around.

In the bad old days, designers used to resort to all kinds of hacky solutions to accomplish what you'd think would be incredibly straightforward layout tasks. Centering elements often involved setting symmetrical **negative margins,** the idea being that if you told something it had to be pulled equally in two opposite directions, it would end up exactly in the middle. Minimizing contrivance passed for something like elegance—designers would brag about how their layout solution was ever-so-slightly less hacky than the next person's.

Fortunately for everyone, **Flexbox** came along in 2009, and all manner of once-difficult layout tasks have been a total breeze ever since.

## Flexing 101: `display-flex`

Like `padding`, `display:flex` controls how elements **inside** an element behave. More than that, `flex` actually creates a miniature universe inside its host element, complete with its own laws of physics.

Consider this:
```
<div class="parent">
  <div class="child" id="red"></div>
  <div class="child" id="orange"></div>
  <div class="child" id="yellow"></div>
  <div class="child" id="green"></div>
  <div class="child" id="blue"></div>
  <div class="child" id="violet"></div>
</div>
```
```
.parent {
  display: flex;
}
```

Here we have a parent `div` (`.parent`) with six child `div`s, each with a unique `id` that gives it a different `background-color` (for simplicity, we're not showing you the styling information for the children, but it's all in `finished_styles.css`). We give the parent `div` a `display: flex` property, which turns it into a flexbox and all of its children into flex items. Because we haven't given `.parent` any other flex properties, it's showing us the default behavior, which is to arrange its children in a row (we can also specify this explicitly by declaring `flex-direction: row`)

![flex-row](./assets/flex-row.png)

_"You are now a flexbox! All of your children are now flex items, outer display properties like `inline` and `block` no longer apply to them, you alone are in control of their layout!"_

We can override the default and tell `.parent` to arrange its children in a column, like so:

```
.parent {
  display: flex;
  flex-direction: column;
}
```

![flex-column](./assets/flex-column.png)

Notice how the red child is always first and the purple child is always last? Flexboxes always lay out their children following **the order in which they appear** in the HTML. We can't scramble the order, but we _can_ tell the parent to reverse it:

```
flex-direction: column-reverse;
```
![flex-column-reverse](./assets/flex-column-reverse.png)
```
flex-direction: row-reverse;
```
![flex-row-reverse](./assets/flex-row-reverse.png)

## Intermediate flexing: `flex-wrap`

What happens when we resize our window?
```
.child {
  height: 100px;
  width: 100px;
}
```
![no-wrap](./assets/no-wrap.png)

Even though we told each `.child` to be a 100px x 100px square, they're forced to get narrower when we resize the window since they have nowhere else to go.

`flex-wrap` to the rescue!
```
.parent {
  display: flex;
  flex-direction: row-reverse;
  flex-wrap: wrap;
}
```
![wrap1](./assets/wrap1.png)

With `flex-wrap` set to `wrap` rather than the default `no-wrap`, flexboxes will automatically wrap their children onto the next row or column whenever they get too narrow/short to fit everything—kind of like how a text editor will "break up" lines of text instead of showing you everything on one super-wide page.

The narrower our window gets, the more children get wrapped:
![wrap2](./assets/wrap2.png)

Until finally we end up with a column:
![wrap3](./assets/wrap3.png)

This can be incredibly useful for situations where we have a certain number of elements to lay out, but don't know the exact shape and size of the box they're going to live in, e.g. in **responsive design,** where websites need to work on narrow cellphone screens as well as on wider desktop monitors.

## Advanced flexing: `justify-content` and `align-items`
CSS can be frustrating in many ways, but one of the things that really made beginners throw up their hands back in the day was how hard it was to align and center things. Flexbox doesn't make it _quite_ as easy as just clicking a button, but it comes close!

First, let's use some advanced selector syntax to make every other child twice as tall:

```
.child:nth-child(even){
  height: 200px;
}
```
![even-children](./assets/even-children.png)

_"From all of the elements with the class "child", select the ones with an even-numbered index (starting from 0), and give them a height of 200 pixels."_

We're using a pseudo class here—check out [Selectors 101](../intro-to-selectors/intro-to-selectors.md) to learn more about them. If you look in the stylesheet, you'll see that the `.child` class still has `height: 100px`, but the rule defined for `.child:nth-child(even)` wins because it is more specific. We'd probably want to clean up redundancies like this if we were writing a real stylesheet, but it's a nice illustration of the cascade algorithm at work. For more on specificity and the CSS cascade, take a look at the [Why Cascading?](../why-cascading/why-cascading.md) tutorial.

Every flexbox has two important axes:
- The **main axis** is the one defined by `flex-direction`
  - Since our `flex-direction` is `row-reverse`, our main axis is **horizontal**
- The **cross-axis** is perpendicular to the main axis
  - Here, our cross-axis is **vertical**

`justify-content` controls how children are laid out along the main axis. By default, flexboxes try to pack all of their children towards the beginning of the main axis. Since our `flex-direction` is reversed, the main axis begins from the right side of the screen and points to the left, which is why everything looks right-aligned. We can override this by explicitly specifying a different `justify-content` value for `.parent`:

```
.parent {
  display: flex;
  flex-direction: row-reverse;
  flex-wrap: wrap;
  justify-content: center;
}
```
![justify-center](./assets/justify-center.png)

_"Position all the children of `.parent` at the center of `.parent`'s main axis'"_


Centered, just like that! But everyone's looking a little squished in there. Remember I told you flexboxes have their own laws of physics? By default, children of a flexbox attract one another and cluster together. We _could_ tell the children to push each other away a little bit by setting a margin on them:
```
.child {
  height: 100px;
  width: 100px;
  margin: 10px;
}
```
![justify-center-margin](./assets/justify-center-margin.png)

**Or** we can tell `.parent` to make its children repel one another by setting `justify-content` to one of the following:
- `space-between`: children repel each other evenly, but can touch the borders of the parent element.
- `space-around`: children repel each other _and_ the borders of the parent element, with equal space on both sides of each child.
- `space-evenly`: same as `space-around`, but each gap contains the same amount of space.
```
.parent {
  display: flex;
  flex-direction: row-reverse;
  flex-wrap: wrap;
  justify-content: space-between;
}
```
![justify-space-between](./assets/justify-space-between.png)

The difference between these three options is kind of subtle and hard to describe—try them out yourself!

`align-items` does the same thing as `justify-content`, but for the cross-axis instead of the main axis:
```
.parent {
  display: flex;
  flex-direction: row-reverse;
  flex-wrap: wrap;
  justify-content: space-between;
  align-items: center;
}
```
![align-center](./assets/align-center.png)

Why "align" vs "justify", and "items" vs "content"? **WHO KNOWS?**

In practice, you'll often find yourself combining `justify-content` and `align-items` values on the parent with `margin` and `padding` values on the children, to control what happens when children *do* come into contact with one another, e.g. when the window gets resized.

Happy flexing!
