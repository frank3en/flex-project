# flex-project

A flex box project.

## Demo of flexbox

## Project Named Trillo

- [x] Project Settings & Custom Properties
- [x] Overall Layout
- [x] Header
- [x] Navigation
- [x] Overview
- [x] Description Section
- [x] User Review Section
- [x] CTA Section (stands for call for action)
- [ ] Media query
- [ ] Deployment.

### Settings & Custom Properties

1. How the `@import`<sup>[1]</sup> keyword works in sass. Partial is connected to `\_\w+.s[ac]ss`
2. How to correctly use `min-height` property.
3. How to set all element to `box-sizing:border-box`.
4. How to define & use some **pure CSS supported** custom variables. And what the pseudo element `:root` means
5. Define `font-size` in `html` element, why _62.5%_ and the advantage of it, and what does the unit `rem` mean.
6. File structure(code split) with `_base.scss`, `_layout.scss` and `_components.scss`.

### Overall Layout

1. ❓There is an unsolved problem, or not fully understand problem, which is when header has a margin-top, the `body` element will be overflowed. The `body` element not include `header` element's `margin-top` area, which is confusing.
2. ❓The meaning of each value of `box-shadow`.
3. The elements of layout in `index.html` is nested, but the style sheet is separated. ~~It may for the readablity.~~ Nested elements with same prifix can be easily written with `sass` syntax, while elements without them have no need to be nested.
4. Setting the `max-width` propery, which let the element grow not too large, which allows the min length. In the same way, the `min-{height,width}` is to avoid too small and go through with the large number.
5. The value of property `flex` measns: `grow shrink basis`, and default to `flex:0 1 auto`.

### Header Part1.

1. Using `svg-sprites.svg` as a collection of svg icons. How to generate and how to use it. Use the hash tag to position certain icon in ther sprites file.
2. The `xlink:href` attribute in `<use />` within `<svg>` only works in a server environment like `<template />` element in HTML.
   > The effect is the same **as if** the nodes were deeply cloned into a non-exposed DOM, then pasted where the use element is, much like cloned template elements<sup>2</sup> in HTML5.
3. SVG resource website: [https://icomoon.io/](https://icomoon.io/).
4. The `bem` block, element, modifier css layout naming methodology.
5. How to format a `svg`? Setting `height` and `width` attributes for size, and `fill:color` for color;
6. A VSCode extension called **Comment Box** generates box comments in `_components.scss`.

### Header Part2.

1. ❓A diff I find is the size of **search icon** is not the same as with mentor's, and it is weird. The `svg` element is no different, it is because of the wrapper element which in this case is the `button` element. Some reasons I found: 1.`button` element has its own **user agent stylesheet**, it doesn't get style inheritance; 2. `line-heigth` and `font-size` has influence to the height of `button` element; 3.`align-items` default `stretch` will strech the button; And there must be other reason...
2. The usage of adjacent selector `+`, when **SOMEELEMENT's** sibling elements has something pseudo event, **SOMEELEMENT** wants a certain corresponding style.
3. Pseudo event of button `:focus` and `:active`.
4. Minus margin and padding for icon place wihin `<input />`: `margin-right: -num`, `padding-right:num`;
5. `input` and `button` can't get inherit `font-size`, `color`, `font-family` and other attributes, need to be manually set;

---

<!-- @TODO: to be reviewed -->

6. Pseudo event `:focus` has a `outline`, which needs to be set to `none`;
7. `justify-content: space-between` and set middle element `flex:0 0 40%` means it no grow no shrink and it has 40% of all width, the width can be used in its children elements as 100% of width.
8. Set `font-size` in `_layout.scss` for inner components to inherit.

### Header Part3

1. For layout symmetric we need to modify some early settings: `logo margin-left`.
2. `align-self:stretch` to let the certain element occupy the whole row size of flex cross axis, which is very helpful for the **pseudo event** like `:hover`,...
3. Direct children element selector `>`.
4. Setting `svg` element's color: `fill:{some rbag/}`,
5. Why setting `border-raidus` a very high value? differ from `50%`.
6. Why only set the height of the `<img />` element, is it because of the origin size is square or the stardard force the height and width to be equal, or is for the `border-raidus` let it be a square-like.

### Nav Part

1. The cubic bezier function website [https://cubic-bezier.com](https://cubic-bezier.com/)
2. The navigation item often used with the `<ul>` and `<li>` item within `<nav />`, and the link it's a `<a />`.
3. The order of pseudo element and pseudo event. `.class:hover::before` means diff with `.class::before:hover`.
4. Multipule transition effects separate with `,`, and the Their sequence is the same with the start sequence.
5. Use `transform:scaleY()/scaleX()` not width, why? It's easy to set the animation origin.
6. There is a deley for different transition effect.
7. The common case for `<a />` style, `:link`,`:visited`,and attribute is `text-decoration`.
8. The common case for `<ul />` style: `list-style`.
9. `z-index` only works when the element is assigned a specific position.
10. The `:active` pseudo event. When does it triggered and can it put on any element? Often triggered when mouse left click.
    > To style links appropriately, put the :active rule after all other link-related rules, as defined by the LVHA-order: :link — :visited — :hover — :active.
11. **`currentColor`** is useful. gives the element color of its own or of its parent.

### Hotel Overview

1. Why add a `<figure>` over `<img>`, for a figure caption then what is a figure caption?
2. In responsible web design, always remember to assign a percentage size(`width`,`height`) value of img, so that the image layout stays fluid.
3. The `<img>` element need to be a `block` or `inline-block` if the **wide space** is not needed.
4. `margin:auto` with `flexbox` layout can occupy white space and avoid the size of element grow!
5. For `svg` elements, they act like pure-text, there is space below them. change the `display` of their parent element, or change parent element `font-size:0`.
6. Remember to group selector together with different names.
7. `letter-spacing:size` is for letter space as the name descripted.
8. Setting `align-self:self` of a flex item to make element cross axis space occupies whole row.
9. Setting `marin-bottom:-2px` to move its below element a bit close to it.
10. To make `inline-button` component more modular, set its `font-size:inherit`, `background-color:transparent`.
11. To make other colors follow event and avoid too many code in pseudo event, setting other color value to `currentColor`.
12. Setting button `display:inline-block`.
13. When does the pseudo event `:focus` triggered.
14. Did `box-shadow` has a `none` value?


### Description

1. Keep parent box padding the same as between children's margin.
2. pure css variable can be used by another variable.
3. Use `<p>`, `<ul>`, `<li>` semantic elements.
4. `:last-of-type` and `:last-child`?
5. How to use `flex-wrap:wrap` to align? with the help of `flex` to flex item to asign the size in their main axis.
6. use `<svg>` in css is like other image with `background-image` and `background-size`.
7. use new feature of `mask-image` to use svg. The anatomy of it is to set a mask and a background color, then we see bg color through the mask.
8. we also need to set `mask-size`.
9. Set the `margin-right:auto` to two flex item in a flex row, which will get the effect of `justify-content:space-between`.
10. In this project, only set `border width` value causes the img size shrink, set `box-sizing:content-box` to fix it.
11. What is the diff between `:last-child` and `:last-of-type`?
12. What does `border-radius:<percentage>` mean?


### User Review / `flex box` review

1. `<figure />` element is not only for pic/img but also for text/description for images.
2. There is a `<blockquote>`, `<figcaption>` using inside of `<figure>` block.
3. `z-index` always shows with a `position`.
4. A html entity cheatsheet website:  https://css-tricks.com/snippets/html/glyphs/
5. The `font-family:sans-serif` shows different in different OS.
6. Setting `line-height:1` to erase extra height.
7. How to create big question mark as background-color?


### CTA 

1. CTA is short for 'call for action'.
2. The best way to hide an invisible element using `over-flow:hidden`;
3. The difference with 2 different `padding` setting in `Button` component, which meant to handle two string with two different string.
4. The pseudo event sequence: **LVHA-order**.

## About Responsive Design

### Design

1. How to set the breakpoints? To where the design start to break
2. As a `browser-fisrt` project, when always use `max-width` for media query. And put the small size below the large size.
3. Media query can't use css custom properties as variable? why?
4. Use `media query` in each selector and pseudo event / element that will imporve the code readablity.
5. The keyword of `@supports` and the usage of it.
6. In `@supports`, we should solve the repeat style outside of it.
7. **Stay focus on the whole page layout instead of just some certain elements**, sometimes you can fix these certain elements in other way rather than set specific break-points. In the project, like the `.recommend__photo`.
8. The meanings of `only` and `and` in `media-query`.

## Component List

- [x] Header-nav-content layout
- [x] Input search
- [x] Notification with number
- [x] Side navigation layout
- [x] Side navigation item with animation
- [x] Button inline with infinite animation
- [x] Avatars overlap layout
- [x] A main Button with 2 text on hover

## Docs

[1]. [https://sass-lang.com/documentation/at-rules/import](https://sass-lang.com/documentation/at-rules/import)

[2]. [https://developer.mozilla.org/en-US/docs/Web/HTML/Element/template](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/template)

## Errors

1. `node-sass version 4.5.3` with node `version >=16`,install `npm i -D node-sass` with command-line syntax `node-sass [options] <input> [output]`.
 
## Dev & Package TODO list

- [x] Update all developement dependencies.
- [ ] Add a deps watcher.
- [ ] Abstract the deps
- [ ] Display some kind of user menu when hovering the username in `.user-nav`
- [ ] Display a message when hovering over the chat icon in `.user-nav` (maybe like facebook)
- [ ] Create a caption for the `.gallery__item` with a nice hover effect.
- [ ] Display a box with search suggestions as soon as the user starts typing in the search field;
- [ ] Make the page 100% responsive even for viewport sizes below 500px, maybe even responsive images.

## My customed own project associated with atelier
