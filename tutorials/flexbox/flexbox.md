# Boxes II: Flexbox

Much like `margin`, `display:inline` and `display:block` affect elements **outside** the element they are set on. Though conceptually important, their usefulness as layout tools is pretty limited—you can only accomplish so much compositionally by making rules to tell boxes when and how they're allowed to push other boxes around.

In the bad old days, designers used to resort to all kinds of hacky solutions to accomplish what you'd think would be incredibly straightforward layout tasks. Centering elements often involved setting symmetrical **negative margins,** the idea being that if you told something it had to be pulled equally in two opposite directions, it would end up exactly in the middle. Minimizing contrivance passed for something like elegance—designers would brag about how their layout solution was ever-so-slightly less hacky than the next person's.

Fortunately for you, **Flexbox** came along in 2009, and all manner of once-difficult layout tasks have been a total breeze ever since.

## How to flex

Like `padding`, `display:flex` controls how elements **inside** an element behave. More than that, `flex` actually creates a miniature universe inside its host element, complete with its own laws of physics.

Consider this:
```
.parent {
  display: flex;
}
```
