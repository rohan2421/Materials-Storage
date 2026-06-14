# 📚 BCA Semester - 1

## 💻 Basics Of Web Page Development

> **Course:** Bachelor of Computer Applications (BCA)  
> **Semester:** 1

---

# 📑 Unit 3 : Cascading Style Sheet & CSS 3 (Deep-Dive Guide)

This guide provides an academic, highly detailed study resource for Unit 3. It explains every single CSS topic in simple, student-friendly terms, accompanied by a Definition, Syntax, Attributes, and Complete Code Examples.

---

# 🗺️ Detailed Syllabus Table of Contents

* **Cascading Style Sheet (CSS)**
  * **Introduction to CSS**
    * History & Purpose of CSS
    * The Rule-Set Structure (Selector, Property, Value)
    * The Concept of **Cascading** (Specificity, Inheritance, Source Order)
    * The `!important` Rule (Definition, Syntax, Warning)
  * **Types of Style Sheets**
    * Inline Style Sheet (Definition, Syntax, Pros & Cons, Example)
    * Internal / Embedded Style Sheet (Definition, Syntax, Pros & Cons, Example)
    * External Style Sheet (Definition, Syntax, Pros & Cons, Example)
    * The CSS `@import` Rule vs HTML `<link>` Tag
  * **Class, ID & Advanced Selectors**
    * Element Selector
    * Class Selector (Dot notation)
    * ID Selector (Hash notation)
    * Universal Selector (`*`)
    * Grouping Selector (Comma notation)
    * **Advanced Selectors:**
      * Combinators (Descendant, Child `>`, Adjacent Sibling `+`, General Sibling `~`)
      * Attribute Selectors
      * Pseudo-Classes (`:hover`, `:active`, `:focus`, `:visited`, `:nth-child`)
      * Pseudo-Elements (`::before`, `::after`, `::first-letter`, `::first-line`)
  * **CSS Text & Font Properties**
    * Text Properties (`color`, `text-align`, `text-decoration`, `text-transform`, `text-indent`, `letter-spacing`, `word-spacing`, `line-height`)
    * Font Properties (`font-family`, `font-size`, `font-style`, `font-weight`, `font-variant`, Shorthand `font`)
    * Custom Fonts Embedding using `@font-face`
  * **CSS Background Properties**
    * `background-color`, `background-image`, `background-repeat`, `background-position`, `background-attachment`, `background-size`
    * Shorthand `background` Property
    * Layered Backgrounds (Multiple background images)
  * **CSS List Properties**
    * `list-style-type`, `list-style-image`, `list-style-position`, Shorthand `list-style`
  * **CSS Margin & Padding Properties (The Box Model)**
    * Understanding the CSS Box Model
    * Padding Properties (Individual & Shorthand)
    * Margin Properties (Individual & Shorthand)
    * `box-sizing` Property (`content-box` vs `border-box`)
    * Collapsing Margins Concept
  * **CSS Comments**
    * Syntax, Single-line, and Multi-line comment guidelines
* **CSS 3 (Advanced Properties)**
  * **Border Property**
    * `border-radius` (Rounded corners, Elliptical borders, Circles)
    * `border-image` (Slicing and rendering image borders)
  * **Background & Gradient Property**
    * Linear Gradients (Directions, Angles, Color Stops)
    * Radial Gradients (Shapes, Position, Color Stops)
  * **Drop Shadow Property**
    * `text-shadow` (Horizontal, Vertical, Blur, Color)
    * `box-shadow` (Horizontal, Vertical, Blur, Spread, Color, Inset)
  * **2D & 3D Transform Property**
    * 2D Transforms (`translate`, `rotate`, `scale`, `skew`)
    * 3D Transforms (`rotateX`, `rotateY`, `rotateZ`, `perspective`, `transform-style`, `backface-visibility`)
  * **Transition Property**
    * `transition-property`, `transition-duration`, `transition-timing-function` (linear, ease, cubic-bezier), `transition-delay`
    * Shorthand `transition` property with interactive hover triggers

---

# 🏛️ Section 1: Cascading Style Sheet (CSS)

---

## 1.1 Introduction to CSS

### 1. Definition & History:
**CSS (Cascading Style Sheets)** is a style sheet language used to describe the presentation (look and formatting) of a document written in HTML. 
* **History:** CSS was proposed by **Håkon Wium Lie** in October 18, 1994, and officially released as CSS1 in December 1996 by the World Wide Web Consortium (W3C). It was created to separate document content (HTML) from document presentation (styles like fonts, colors, and spacing).

---

### 2. The CSS Rule-Set Structure:
CSS rules target HTML tags. A rule consists of a selector and a declaration block:
```
  Selector {
      Property : Value;
  }
```
* **Selector:** Points to the HTML tag (e.g., `p`, `h1`).
* **Property:** The style attribute (e.g., `color`, `font-size`).
* **Value:** The setting for the property (e.g., `red`, `16px`).

---

### 3. The Concept of "Cascading":
The word **Cascading** means that style rules fall down (cascade) from one sheet to another in a specific priority order. If two styling rules target the same HTML element, the browser decides which rule to apply based on three rules:

#### A. Specificity (Selector Priority):
Different selectors have different weights. The browser calculates specificity to see which selector is more specific.
1. **Inline Styles** (Highest Priority) -> Specificity Weight = 1000
2. **ID Selectors** (e.g., `#main`) -> Specificity Weight = 100
3. **Classes, Attributes, and Pseudo-classes** (e.g., `.box`) -> Specificity Weight = 10
4. **Element tags and Pseudo-elements** (e.g., `p`) -> Specificity Weight = 1
5. **Universal Selector (`*`)** (Lowest Priority) -> Specificity Weight = 0

#### B. Inheritance:
Some CSS properties are passed down from parent elements to child elements. For example, if you set `color: green;` on the `<body>` tag, all paragraphs inside the body will inherit the green color, unless they have their own specific color style.

#### C. Source Order (Last Rule Wins):
If two rules have the exact same specificity weight, the one written **last** in the CSS file will override the earlier ones.

---

### 4. The `!important` Rule:
The `!important` keyword is used to force a CSS rule to override any other styles, regardless of selector specificity.
* **Warning:** Use `!important` only when absolutely necessary, as it makes debugging CSS layout overrides very difficult.

#### Syntax:
```css
selector {
    property: value !important;
}
```

#### Example:
```css
/* This paragraph will be blue, even if an inline style says red */
p {
    color: blue !important;
}
```

---

## 1.2 Types of Style Sheets

There are three ways of applying styling rules to HTML elements.

---

### 1. Inline Style Sheets

#### Definition:
Used to apply a unique style rule to a **single** HTML element. It is written directly inside the HTML opening tag using the `style` attribute.

#### Syntax:
```html
<element style="property: value;">Text</element>
```

#### Pros & Cons:
* **Pros:** Ideal for testing single changes quickly; overrides external styles instantly.
* **Cons:** Makes HTML code cluttered and messy; changes must be done manually on every single tag.

#### Code Example:
```html
<p style="color: crimson; font-weight: bold; text-decoration: underline;">
    This text is styled using Inline CSS.
</p>
```

---

### 2. Internal / Embedded Style Sheets

#### Definition:
Used to define styles for a **single web page**. The rules are placed inside a `<style>` tag, which must be nested inside the `<head>` section of the HTML document.

#### Syntax:
```html
<head>
    <style>
        selector {
            property: value;
        }
    </style>
</head>
```

#### Pros & Cons:
* **Pros:** Styles for the entire page can be managed in one place; no extra HTTP files needed.
* **Cons:** Styles cannot be reused on other pages of the website.

#### Code Example:
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Internal CSS Example</title>
    <style>
        body {
            background-color: #fafafa;
        }
        h2 {
            color: darkcyan;
            border-bottom: 2px solid darkcyan;
        }
    </style>
</head>
<body>
    <h2>Internal CSS Heading</h2>
    <p>This page styles elements via the internal header stylesheet.</p>
</body>
</html>
```

---

### 3. External Style Sheets

#### Definition:
The most efficient method. All style rules are written in a separate document with a `.css` file extension. The HTML file then links to this CSS file using the `<link>` tag inside the `<head>` block.

#### Syntax:
```html
<!-- Linked in HTML head -->
<link rel="stylesheet" type="text/css" href="style.css">
```

#### Pros & Cons:
* **Pros:** Separates content from style completely; changes in one CSS file instantly update the entire website layout.
* **Cons:** Requires the browser to download an extra external file.

#### Code Example:
```html
<!-- index.html -->
<!DOCTYPE html>
<html>
<head>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="card">
        <h3>External CSS Card</h3>
    </div>
</body>
</html>
```
```css
/* styles.css */
body {
    font-family: sans-serif;
}
.card {
    border: 1px solid #ddd;
    padding: 20px;
    border-radius: 4px;
}
```

---

### 4. The `@import` Rule:
The `@import` rule is another way to load external CSS stylesheets. It is written inside a CSS file or inside a `<style>` tag.
* **Difference from `<link>`:** The `<link>` tag is HTML and loads files in parallel, whereas `@import` is CSS and loads files sequentially (which can be slower).

#### Syntax:
```css
@import url("additional-style.css");
```

---

## 1.3 Selectors & Advanced Matchings

Selectors target HTML nodes to apply styles. Let's study the essential and advanced selectors:

---

### 1. Element Selector (Tag Selector)
* **Definition:** Selects all HTML elements with the specified tag name.
* **Syntax:** `tagname { }`
* **Example:**
  ```css
  p { color: blue; } /* Styles all paragraph tags */
  ```

---

### 2. Class Selector
* **Definition:** Selects elements that have a specific `class` attribute. You can use classes on multiple elements.
* **Syntax:** `.classname { }` (Note the dot prefix)
* **Example:**
  ```css
  .error-msg { color: red; font-size: 12px; }
  ```

---

### 3. ID Selector
* **Definition:** Selects a single unique HTML element with the specified `id` attribute.
* **Syntax:** `#idname { }` (Note the hash prefix)
* **Example:**
  ```css
  #main-nav { background-color: black; }
  ```

---

### 4. Universal Selector
* **Definition:** Selects every single element on the webpage. It is commonly used to reset default browser margins and padding.
* **Syntax:** `* { }`
* **Example:**
  ```css
  * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
  }
  ```

---

### 5. Grouping Selector
* **Definition:** Used to apply the same CSS rules to multiple selectors at once. Selectors are separated by commas.
* **Syntax:** `selector1, selector2, selector3 { }`
* **Example:**
  ```css
  h1, h2, h3 {
      font-family: serif;
      color: darkblue;
  }
  ```

---

### 6. Combinator Selectors
Combinators explain the relationship between two selectors:
* **Descendant Selector (Space):** Targets elements inside another element (e.g., `div p` matches all `<p>` inside a `<div>`).
* **Child Selector (`>`):** Targets elements that are immediate direct children of another element (e.g., `div > p` matches only direct `<p>` children, not grandchildren).
* **Adjacent Sibling Selector (`+`):** Targets the element immediately following another element on the same level.
* **General Sibling Selector (`~`):** Targets all sibling elements following another element.

#### Syntax & Examples:
```css
/* Match only direct li children of ul */
ul > li {
    list-style: circle;
}

/* Match paragraph immediately following an h2 */
h2 + p {
    font-weight: bold;
}
```

---

### 7. Attribute Selectors
* **Definition:** Targets HTML elements based on the presence or value of their attributes.
* **Syntax:** `[attribute="value"]`
* **Example:**
  ```css
  input[type="text"] { border: 1px solid blue; }
  ```

---

### 8. Pseudo-Classes & Pseudo-Elements

#### Pseudo-Classes:
A Pseudo-class is used to define a special state of an element (e.g., when a user hovers over it, clicks it, or focuses it).
* **Syntax:** `selector:pseudo-class { }`
* **Common Pseudo-classes:**
  * `:hover`: Triggers when mouse cursor rolls over the element.
  * `:active`: Triggers while the element is being clicked.
  * `:focus`: Triggers when the element receives keyboard focus.
  * `:nth-child(n)`: Matches the nth child of its parent (e.g., `:nth-child(2)` matches the second child).

#### Pseudo-Elements:
A Pseudo-element is used to style specific parts of an element (e.g., the first letter of a paragraph, or adding content before/after an element).
* **Syntax:** `selector::pseudo-element { }`
* **Common Pseudo-elements:**
  * `::first-letter`: Styles the very first letter of a text block.
  * `::before`: Injects custom content before the element's actual content.
  * `::after`: Injects custom content after the element's actual content.

#### Code Example:
```html
<!DOCTYPE html>
<html>
<head>
    <style>
        /* Pseudo-class: Hover link effect */
        a:hover {
            color: orange;
            text-decoration: underline;
        }
        /* Pseudo-class: Style odd list items */
        li:nth-child(odd) {
            background-color: #f2f2f2;
        }
        /* Pseudo-element: Add a decorative quote mark before blockquotes */
        blockquote::before {
            content: "“ ";
            font-size: 24px;
            color: gray;
        }
    </style>
</head>
<body>
    <a href="#">Hover over me!</a>
    <ul>
        <li>First item</li>
        <li>Second item</li>
        <li>Third item</li>
    </ul>
    <blockquote>BCA is an exciting career path.</blockquote>
</body>
</html>
```

---

## 1.4 CSS Text & Font Properties

---

### 1. CSS Text Properties

#### Definition:
Text properties control the appearance, alignment, decorations, casing, and spacing of text characters.

#### Key Properties & Values:
* `color`: Color of text characters.
* `text-align`: Alignment (Values: `left`, `right`, `center`, `justify`).
* `text-decoration`: Adds lines (Values: `none`, `underline`, `overline`, `line-through`).
* `text-transform`: Cases text (Values: `uppercase`, `lowercase`, `capitalize`).
* `text-indent`: Indents the first line of text (Value: pixels, e.g., `30px`).
* `letter-spacing`: Spacing between individual letters (Value: pixels, e.g., `2px`).
* `word-spacing`: Spacing between words (Value: pixels, e.g., `5px`).
* `line-height`: Spacing between text lines (Value: number multipliers like `1.5`, or percentages).

#### Syntax:
```css
selector {
    text-align: center;
    text-transform: capitalize;
}
```

#### Code Example:
```html
<p style="text-align: justify; line-height: 1.6; text-indent: 40px; word-spacing: 2px;">
    This text layout utilizes word spacing, text alignment, and line height adjustments to ensure readable print layouts inside the browser viewport.
</p>
```

---

### 2. CSS Font Properties

#### Definition:
Font properties set the font family face, font sizes, weights, and styles.

#### Key Properties & Values:
* `font-family`: List of font names. Use fallbacks (e.g., `Arial, sans-serif`).
* `font-size`: Font size dimensions (Values: `px`, `em`, `rem`, `%`).
* `font-style`: Slant level (Values: `normal`, `italic`, `oblique`).
* `font-weight`: Text thickness (Values: `normal`, `bold`, numeric weights `100` to `900`).
* `font-variant`: Standard text vs Small Capitals (Values: `normal`, `small-caps`).

#### Shorthand Syntax:
The shorthand property `font` allows you to set several font properties in a single line.
```css
font: style variant weight size/line-height family;
```

#### Code Example:
```html
<p style="font: italic small-caps bold 20px/1.5 'Courier New', Courier, monospace;">
    This text is styled using the shorthand font property.
</p>
```

---

### 3. Custom Fonts Embedding (`@font-face`)

#### Definition:
Allows you to load custom font files (such as `.woff2` or `.ttf` files) from your web server, so users do not need to have the font pre-installed on their computers.

#### Syntax:
```css
@font-face {
    font-family: "MyCustomFont";
    src: url("fonts/customfont.woff2") format("woff2"),
         url("fonts/customfont.ttf") format("truetype");
}

.custom-text {
    font-family: "MyCustomFont", sans-serif;
}
```

---

## 1.5 CSS Background Properties

#### Definition:
Background properties define background colors, render background images, control image repeat directions, size, and positions.

#### Key Properties & Values:
* `background-color`: Fills the background with color (Values: names, HEX, RGB).
* `background-image`: Embeds background image file (Value: `url('path.png')`).
* `background-repeat`: Tile repeat control (Values: `repeat`, `no-repeat`, `repeat-x`, `repeat-y`).
* `background-position`: Background position coordinates (Values: `left top`, `center`, `right bottom`, pixels, percentages).
* `background-attachment`: Fixed or scrolling background attachment (Values: `scroll`, `fixed`).
* `background-size`: Adjusts image dimensions (Values: `auto`, `cover`, `contain`, explicit pixels e.g. `200px 100px`).

#### Shorthand Syntax:
```css
background: color image repeat attachment position/size;
```

#### Code Example:
```html
<div style="height: 200px; background: lightgray url('https://picsum.photos/400/200') no-repeat center/cover fixed;">
    <h2 style="color: white; padding: 20px;">Parallax Scroll Header</h2>
</div>
```

#### Multi-background Image Syntax:
CSS3 allows you to layer multiple background images on top of each other, separated by commas. The first image listed is on top, and the last is on the bottom.
```css
background-image: url('front.png'), url('back.png');
```

---

## 1.6 CSS List Properties

#### Definition:
Used to style lists by changing the bullet markers, list numbers, or list indentation positions.

#### Key Properties & Values:
* `list-style-type`: Marker icons or numbering format.
  * *Unordered lists:* `disc`, `circle`, `square`, `none` (no bullet).
  * *Ordered lists:* `decimal`, `lower-roman`, `upper-alpha`, etc.
* `list-style-image`: Replaces bullets with a custom image (Value: `url('bullet.png')`).
* `list-style-position`: Sets if marker stays inside or outside the text indentation margin (Values: `inside`, `outside`).

#### Shorthand Syntax:
```css
list-style: type position image;
```

#### Code Example:
```html
<ul style="list-style: square inside;">
    <li>First point with square marker</li>
    <li>Second point with square marker</li>
</ul>
```

---

## 1.7 CSS Margin & Padding Properties (The Box Model)

Every element on a web page is a box. The CSS Box Model consists of:
* **Content:** The actual text or image.
* **Padding:** Clear area immediately around the content, inside the border.
* **Border:** A border line around padding and content.
* **Margin:** Clear area outside the border, creating space between boxes.

---

### 1. Padding Properties
* **Properties:** `padding-top`, `padding-right`, `padding-bottom`, `padding-left`.
* **Shorthand Syntax:**
  * `padding: 10px;` (All 4 sides = 10px)
  * `padding: 10px 20px;` (Top/Bottom = 10px, Left/Right = 20px)
  * `padding: 10px 20px 30px 40px;` (Top, Right, Bottom, Left - Clockwise)

---

### 2. Margin Properties
* **Properties:** `margin-top`, `margin-right`, `margin-bottom`, `margin-left`.
* **Shorthand Syntax:** Follows the exact same clockwise structure as padding.
* **Centering elements:** To center a block element (like a `<div>`), set `margin: 0 auto;` and define a fixed `width`.

---

### 3. Box-Sizing Property: `content-box` vs `border-box`
By default, the width of a box is calculated as: `Width = width + padding + border`. This is called **`content-box`**. It can make layout math very difficult.
* **`border-box`:** Tells the browser to include padding and border in the element's total width and height. If you set width to 200px, it stays 200px even if you add padding. This is the preferred method for modern layouts.

#### Syntax:
```css
* {
    box-sizing: border-box;
}
```

---

### 4. Collapsing Margins:
When two vertical margins touch each other (like one paragraph below another), they do not add together. Instead, they collapse into a single margin. The size of the collapsed margin is equal to the larger of the two touching margins. (Note: Horizontal margins never collapse).

#### Code Example:
```html
<!DOCTYPE html>
<html>
<head>
    <style>
        .box1 {
            background-color: lightcoral;
            margin-bottom: 30px;
            width: 200px;
            padding: 10px;
        }
        .box2 {
            background-color: lightblue;
            margin-top: 20px;
            width: 200px;
            padding: 10px;
        }
    </style>
</head>
<body>
    <!-- The actual distance between these boxes will be 30px (not 50px) because margins collapse -->
    <div class="box1">Box 1 (Margin Bottom: 30px)</div>
    <div class="box2">Box 2 (Margin Top: 20px)</div>
</body>
</html>
```

---

## 1.8 CSS Comments

#### Definition:
Comments are notes written inside the CSS stylesheet to help developers document their code. They are completely ignored by the browser parser.

#### Syntax:
```css
/* Comment goes here */
```

#### Code Example:
```css
/* ====================================
   HEADER STYLING RULES
   ==================================== */
.main-header {
    background-color: #333; /* Dark background color */
    color: #fff;            /* White text color */
}
```

---

# 🏛️ Section 2: CSS 3 (Advanced Properties)

---

## 2.1 CSS3 Border Property

CSS3 adds advanced border options, including rounded corners (`border-radius`) and using images as borders (`border-image`).

---

### 1. `border-radius` (Rounded Corners)

#### Easy Definition:
Allows you to round the corners of an element. If you set it to `50%` on a square element (where width and height are equal), it becomes a perfect circle.

#### Syntax:
```css
border-radius: top-left top-right bottom-right bottom-left;
```

#### Code Example:
```html
<div style="width: 100px; height: 100px; background-color: darkviolet; border-radius: 15px;">
    <!-- Rounded Box -->
</div>
```

---

### 2. `border-image` (Image Borders)

#### Easy Definition:
Allows you to specify an image to be used as the border around an element, instead of a solid line.

#### Syntax:
```css
border-image: url('border.png') 30 round;
```

---

## 2.2 CSS3 Background & Gradient Property

Gradients let you display smooth transitions between two or more colors.

---

### 1. Linear Gradients

#### Easy Definition:
Colors blend into each other in a straight line (left-to-right, top-to-bottom, or diagonally at an angle).

#### Syntax:
```css
background: linear-gradient(direction/angle, color-stop1, color-stop2, ...);
```

#### Code Example:
```html
<!-- Diagonal gradient transition at 45 degrees -->
<div style="height: 100px; background: linear-gradient(45deg, red, yellow, green);"></div>
```

---

### 2. Radial Gradients

#### Easy Definition:
Colors blend outward in a circular or elliptical pattern, starting from a center point.

#### Syntax:
```css
background: radial-gradient(shape position, start-color, ..., last-color);
```

#### Code Example:
```html
<!-- Circular gradient from center outward -->
<div style="width: 120px; height: 120px; border-radius: 50%; background: radial-gradient(circle, yellow, red);"></div>
```

---

## 2.3 CSS3 Drop Shadow Property

Shadows can be added to text and element boxes.

---

### 1. `text-shadow` (Shadow on Text)

#### Easy Definition:
Adds drop shadows behind text characters.

#### Syntax:
```css
text-shadow: h-shadow v-shadow blur-radius color;
```
* **h-shadow:** Horizontal shadow offset (positive moves shadow right, negative moves it left).
* **v-shadow:** Vertical shadow offset (positive moves shadow down, negative moves it up).
* **blur-radius:** Softness of the shadow (optional).
* **color:** Color of the shadow.

#### Code Example:
```html
<h1 style="color: white; text-shadow: 2px 2px 4px #000000;">
    Glow Text Shadow
</h1>
```

---

### 2. `box-shadow` (Shadow on Boxes)

#### Easy Definition:
Adds drop shadows behind an element's outer container box.

#### Syntax:
```css
box-shadow: h-shadow v-shadow blur-radius spread-radius color inset;
```
* **spread-radius:** Shrinks or grows the shadow size (optional).
* **inset:** Changes the shadow from an outer shadow to an inner shadow (optional).

#### Code Example:
```html
<div style="width: 150px; height: 100px; background-color: #fff; border: 1px solid #eee; box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);">
    Card Box Shadow
</div>
```

---

## 2.4 CSS3 2D & 3D Transform Property

Transforms allow you to move, rotate, scale, and skew HTML elements.

---

### 1. 2D Transforms

* **`translate(x, y)`:** Moves the element on the 2D X and Y axes.
* **`rotate(angle)`:** Rotates the element (e.g., `rotate(45deg)`).
* **`scale(x, y)`:** Changes the size of the element.
* **`skew(x-angle, y-angle)`:** Tilts the element on the axes.

#### Code Example:
```html
<div style="width: 100px; height: 50px; background-color: blue; color: white; transform: rotate(10deg) translate(20px, 10px);">
    2D Box
</div>
```

---

### 2. 3D Transforms

* **`rotateX(angle)` & `rotateY(angle)`:** Rotates the element in 3D space around the X or Y axis.
* **`perspective`:** Defines the 3D depth perception. Lower values create a more intense 3D effect.
* **`transform-style: preserve-3d;`:** Specifies that nested child elements should preserve their 3D placements.
* **`backface-visibility`:** Specifies whether the back side of an element should be visible when it is rotated to face away from the user (Values: `visible`, `hidden`).

#### Code Example:
```html
<!DOCTYPE html>
<html>
<head>
    <style>
        .stage-3d {
            perspective: 400px;
            margin: 50px;
        }
        .card-3d {
            width: 100px;
            height: 100px;
            background-color: darkgreen;
            color: white;
            /* Rotate along the X axis */
            transform: rotateX(60deg);
            text-align: center;
            line-height: 100px;
        }
    </style>
</head>
<body>
    <div class="stage-3d">
        <div class="card-3d">3D Box</div>
    </div>
</body>
</html>
```

---

## 2.5 CSS3 Transition Property

---

### 1. Easy Definition:
Transitions allow you to change CSS property values smoothly and gradually over a specified duration (like a fade-in or slide effect) when an element changes states (e.g., when a user hovers over a button).

---

### 2. Individual Properties:
* `transition-property`: The name of the CSS property to watch (e.g., `background-color`, `width`, `all`).
* `transition-duration`: The duration of the transition (e.g., `0.5s`, `300ms`).
* `transition-timing-function`: The speed curve of the transition.
  * **Values:** `linear` (same speed), `ease` (slow start, fast middle, slow end), `ease-in` (slow start), `ease-out` (slow end), `ease-in-out` (slow start and end).
  * **Custom Curves:** `cubic-bezier(x1, y1, x2, y2)` lets you write custom speed timing.
* `transition-delay`: Delay time before starting the transition (e.g., `0.1s`).

---

### 3. Shorthand Syntax:
```css
transition: property duration timing-function delay;
```

---

### 4. Interactive Code Example:
Below is a hover card that animates its width, background color, shadow, and rotation smoothly when the mouse floats over it:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Interactive Transition Card</title>
    <style>
        .hover-card {
            width: 200px;
            height: 150px;
            background-color: lightseagreen;
            border-radius: 8px;
            padding: 20px;
            color: white;
            box-shadow: 0 2px 4px rgba(0,0,0,0.1);
            
            /* Transition shorthand: watch all property changes over 0.6 seconds smoothly */
            transition: all 0.6s ease-in-out;
            cursor: pointer;
        }

        /* Hover style triggers when cursor moves over card */
        .hover-card:hover {
            background-color: coral;
            transform: scale(1.1) rotate(5deg);
            box-shadow: 0 10px 20px rgba(0,0,0,0.3);
        }
    </style>
</head>
<body>

    <h2>CSS3 Hover Transition Demo</h2>
    <p>Hover your cursor over the card below to see the transition animation:</p>
    
    <div class="hover-card">
        <h3>Card Title</h3>
        <p>This card changes size, color, rotation, and shadows smoothly.</p>
    </div>

</body>
</html>
```

---
*Created for BCA Semester 1 Academic Reference. Master these properties to design beautiful, professional websites.*
