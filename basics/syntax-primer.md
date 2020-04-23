# CSS Syntax Primer

If you're totally new to CSS, use this quick primer to help you identify the basic syntax of CSS. This syntax recurs in all of the tutorials in this repo, so you don't need to memorize it, but if you want a quick explainer, read on!

Here's the example CSS we'll use to look at syntax:
```css
body {
  width: 100%;
  background-color: white;
}
h1 {
  font-size: 50px;
  color: blue;
}
.caption {
  font-size: 10px;
  font-family: monospace;
}
div#heroImg {
  width: 100%;
  height: 10%;
}
div#heroImg > h2 {
  color: white;
}
```
In general, CSS stylesheets contain two things:
1. Selectors
2. Declarations

Selectors are all the names that tell your browser which HTML elements to apply which styles to. For example, `body` is a selector. Styles inside the `{}` following `body` apply to all HTML elements contained in the body of your document. In our example above, these are all selectors:
  - `body`
  - `h1`
  - `.captions`
  - `div#heroImg`
  - `div#heroImg > h2`

There are a few different types of selectors in this list:
- `body` and `h1` are standard selectors. They apply to every HTML or markdown element of that type.
- `.caption` is a class selector. We can mark elements in our HTML document as `class="caption"`, and styles listed here will apply to every element so identified.
- `div#heroImg` is an id selector. `#heroImg` is the id, and we assign it to an HTML element like so, `id="heroImg"`. Ids work a lot like classes except that an id can only attach to one element, so ids are the best way a specific item on your page.
- `div#heroImg > h2` is a nested selector. It essentially says apply these styles only to `h2` elements that are children of the hero image div. You'll see this sort of selector in our [center-text-on-image](../tutorial/center-text-on-image/center-text-on-image.md) tutorial.

At this point you might be wondering, what happens if my element is covered by more than one selector? What if, for example, there was an `h2` selector in addition to the nested one? This is where the _Cascading_ part of CSS comes in. Styles in selectors that are more specific override styles from selectors that are more general. We'll say more about this in our tutorial [Why Cascading?](../tutorials/why-cascading)

Declarations are all of the specific styles we're applying. Each declaration consists of a property and a value. For example, `font-size: 50px;` declares that for the property `font-size`, we'll use a value of `50px`. Notice that each of these declarations is formatted with a colon after the property name and a semi-colon at the end of the line. These properties and the values they accept are what we'll be exploring in all of the tutorials in this repo!
