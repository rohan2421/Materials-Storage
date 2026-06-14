# 📚 BCA Semester - 1

## 💻 Basics Of Web Page Development

> **Course:** Bachelor of Computer Applications (BCA)  
> **Semester:** 1

---

# 📑 Unit 2 : Advance HTML 5

Welcome to the simplified, detailed study guide for Unit 2: Advance HTML 5. This guide explains every topic in easy words, with clear definitions, syntax, attributes, and simple examples that you can run directly in your browser.

---

# 🗺️ Syllabus Table of Contents

1. **HTML 5 Document Structure & Syntax**
   * HTML5 Document Structure Rules (Easy concept)
   * Semantic Tags (Explained one-by-one):
     1. `<header>`
     2. `<nav>`
     3. `<section>`
     4. `<article>`
     5. `<aside>`
     6. `<footer>`
     7. `<dialog>`
2. **Attributes of HTML 5**
   * Global Attributes:
     1. `contenteditable`
     2. `draggable`
     3. `spellcheck`
     4. `tabindex`
     5. `hidden`
     6. `data-*` (Custom data)
3. **Web Form Input Types**
   * Form inputs explained one-by-one:
     1. `datetime-local`
     2. `date`
     3. `month`
     4. `week`
     5. `time`
     6. `number`
     7. `range`
     8. `email`
     9. `url`
4. **Audio / Video**
   * `<audio>` Tag (Definition, Syntax, Attributes, Code Example)
   * `<video>` Tag (Definition, Syntax, Attributes, Code Example)
   * Native JavaScript Media Controls (Simple way)

---

# 🏛️ Section 1: HTML 5 Document Structure & Syntax

## 1.1 HTML 5 Document Structure & Syntax Rules

### Easy Definition:
In older HTML versions, creating a layout required using many generic `<div>` boxes. HTML5 introduced **semantic tags**. A "semantic tag" is a tag that has a clear name that tells both the developer and the browser exactly what content is inside it (e.g., `<header>` is for the top, `<footer>` is for the bottom).

### Syntax Rules in Simple Words:
1. **The Doctype (`<!DOCTYPE html>`):** This must be at the very first line of your HTML document. It tells the browser that this page is written in HTML5.
2. **Case Insensitivity:** Tags can be written in capital letters (`<BODY>`) or small letters (`<body>`). However, always use small letters because it is neat and standard.
3. **Self-closing tags:** Tags like `<br>`, `<img>`, and `<input>` do not need a closing tag like `</br>`.
4. **Simple Encoding:** You only need `<meta charset="UTF-8">` inside the `<head>` to support all languages and characters.

---

## 1.2 The 7 Semantic Layout Tags (Explained One-By-One)

---

### 1. `<header>`

#### Easy Definition:
The `<header>` tag is like the cover of a book or the top banner of a newspaper. It is used to hold the introductory content, website logo, main title, or navigation links at the top of a webpage.

#### Syntax:
```html
<header>
    <!-- Logo, Title, and Nav links go here -->
</header>
```

#### Attributes:
* Supports all **Global Attributes** (like `id`, `class`, `style`).

#### Simple Code Example:
```html
<header style="background-color: lightblue; padding: 15px; text-align: center;">
    <h1>Welcome to BCA Academy</h1>
    <p>Learn Web Development the Easy Way</p>
</header>
```

---

### 2. `<nav>`

#### Easy Definition:
`<nav>` stands for **navigation**. It is a block that contains links to help users move to different pages of your website (like Home, About, Contact) or different parts of the same page.

#### Syntax:
```html
<nav>
    <a href="URL">Link Text</a>
</nav>
```

#### Attributes:
* Supports all **Global Attributes**.

#### Simple Code Example:
```html
<nav style="background-color: #333; padding: 10px;">
    <a href="#home" style="color: white; margin-right: 15px; text-decoration: none;">Home</a>
    <a href="#about" style="color: white; margin-right: 15px; text-decoration: none;">About</a>
    <a href="#contact" style="color: white; text-decoration: none;">Contact Us</a>
</nav>
```

---

### 3. `<section>`

#### Easy Definition:
A `<section>` tag is like a chapter in a textbook. It is used to group together related content. For example, a page might have an "Introduction" section, a "Features" section, and a "Pricing" section. Every section should normally have its own heading (`<h2>`, `<h3>`, etc.).

#### Syntax:
```html
<section>
    <h2>Section Title</h2>
    <p>Section content...</p>
</section>
```

#### Attributes:
* Supports all **Global Attributes**.

#### Simple Code Example:
```html
<section style="margin: 20px 0; border-left: 5px solid blue; padding-left: 10px;">
    <h2>Course Details</h2>
    <p>BCA Semester 1 covers Basic HTML, CSS, C Language, and Office Tools.</p>
</section>
```

---

### 4. `<article>`

#### Easy Definition:
An `<article>` tag is like an individual news story in a newspaper, a single blog post, or a forum comment. The content inside an `<article>` is independent, meaning if you copy just this section and paste it on another website, it would still make complete sense by itself.

#### Difference between `<section>` and `<article>`:
* Use `<section>` to group parts of a page together.
* Use `<article>` for a single block of content that can stand completely alone.

#### Syntax:
```html
<article>
    <h2>Article Title</h2>
    <p>Article body...</p>
</article>
```

#### Attributes:
* Supports all **Global Attributes**.

#### Simple Code Example:
```html
<article style="border: 1px solid #ccc; padding: 15px; border-radius: 5px; margin: 10px 0;">
    <h2>HTML5 Released!</h2>
    <p>HTML5 became a standard in 2014, bringing native audio, video, and drag-and-drop features to the web.</p>
</article>
```

---

### 5. `<aside>`

#### Easy Definition:
An `<aside>` tag is like a sidebar or a "Did You Know?" box in a textbook. It holds content that is extra or indirectly related to the main content (like advertisements, list of links, or secondary information).

#### Syntax:
```html
<aside>
    <!-- Sidebar links, ads, or quick facts go here -->
</aside>
```

#### Attributes:
* Supports all **Global Attributes**.

#### Simple Code Example:
```html
<aside style="background-color: #f4f4f4; padding: 10px; width: 250px; float: right; border: 1px dashed gray;">
    <h3>Quick Reference</h3>
    <p>HTML stands for HyperText Markup Language.</p>
</aside>
```

---

### 6. `<footer>`

#### Easy Definition:
The `<footer>` tag is like the last page of a letter. It is placed at the very bottom of a webpage or section. It contains copyright notices, contact details, site maps, or privacy policy links.

#### Syntax:
```html
<footer>
    <!-- Copyright info or links go here -->
</footer>
```

#### Attributes:
* Supports all **Global Attributes**.

#### Simple Code Example:
```html
<footer style="background-color: #222; color: white; text-align: center; padding: 15px; margin-top: 20px;">
    <p>&copy; 2026 BCA Portal. All Rights Reserved.</p>
    <p>Contact: info@bcaportal.edu</p>
</footer>
```

---

### 7. `<dialog>`

#### Easy Definition:
A `<dialog>` tag is used to create a popup window or modal box directly inside the HTML without needing complex external CSS frameworks. It remains hidden unless you tell it to show using JavaScript.

#### Syntax:
```html
<dialog id="myDialog">
    <p>This is a popup message!</p>
    <button onclick="closeDialog()">Close</button>
</dialog>
```

#### Methods to Control (JavaScript):
1. `dialogElement.show()`: Opens the dialog as a simple popup.
2. `dialogElement.showModal()`: Opens the dialog as a modal (dims/blurs everything else on the page so the user must interact with the dialog).
3. `dialogElement.close()`: Closes the dialog box.

#### Attributes:
* `open`: A boolean attribute. If written (e.g., `<dialog open>`), the popup will be visible on page load. If not written, it stays hidden.

#### Simple Code Example:
```html
<!-- The Dialog Box -->
<dialog id="alertBox" style="padding: 20px; border-radius: 8px; border: 2px solid blue;">
    <h3>Important Notice</h3>
    <p>Your admission form has been saved successfully!</p>
    <button onclick="document.getElementById('alertBox').close()">OK</button>
</dialog>

<!-- Button to Open the Dialog -->
<button onclick="document.getElementById('alertBox').showModal()">Show Alert Popup</button>
```

---

# 🏛️ Section 2: Attributes of HTML 5

Global Attributes are attributes that can be used on **any** HTML element. Here are the 6 major HTML5 global attributes:

---

### 1. `contenteditable`

#### Easy Definition:
This attribute makes any element's text editable by the user directly on the web browser, like a text editor word file.

#### Syntax:
```html
<element contenteditable="true|false">
```

#### Example:
```html
<p contenteditable="true" style="border: 1px solid gray; padding: 5px;">
    You can click here and edit this paragraph text yourself!
</p>
```

---

### 2. `draggable`

#### Easy Definition:
Specifies whether an element can be dragged by the mouse (used in drag-and-drop features).

#### Syntax:
```html
<element draggable="true|false|auto">
```

#### Example:
```html
<div draggable="true" style="width: 100px; padding: 10px; background-color: yellow; border: 1px solid black; cursor: move;">
    Drag Me!
</div>
```

---

### 3. `spellcheck`

#### Easy Definition:
Tells the browser whether it should check the spelling and grammar of the text inside editable elements.

#### Syntax:
```html
<element spellcheck="true|false">
```

#### Example:
```html
<p contenteditable="true" spellcheck="true">
    This line contains spelling misstakes. Click to see red lines.
</p>
```

---

### 4. `tabindex`

#### Easy Definition:
Controls which element gets focused when you press the **Tab** key on your keyboard to navigate the webpage.

#### Values:
* `0`: Normal focus order.
* `-1`: The element cannot be focused using the Tab key (but can be clicked).
* `1, 2, 3...`: Explicit order of focus (1 is first, 2 is second, etc.).

#### Syntax:
```html
<element tabindex="number">
```

#### Example:
```html
<input type="text" placeholder="First Input" tabindex="1">
<input type="text" placeholder="Third Input" tabindex="3">
<input type="text" placeholder="Second Input" tabindex="2">
```

---

### 5. `hidden`

#### Easy Definition:
A simple attribute to hide any element from the screen completely. It is like CSS `display: none`.

#### Syntax:
```html
<element hidden>
```

#### Example:
```html
<p>This line is visible.</p>
<p hidden>This line is hidden and will not be displayed!</p>
```

---

### 6. `data-*` (Custom Data Attributes)

#### Easy Definition:
Allows you to store extra information (metadata) inside an HTML tag. This data is invisible to the user but can be read and used by JavaScript. The `*` can be replaced with any lowercase word you choose.

#### Syntax:
```html
<element data-yourword="value">
```

#### Example:
```html
<!-- HTML -->
<div id="courseInfo" data-subject="BCA" data-semester="1" data-code="BCA102">
    Basics of Web Development
</div>

<!-- JavaScript to read data -->
<script>
    var element = document.getElementById("courseInfo");
    var code = element.dataset.code; // Reads "BCA102"
    alert("Subject Code is: " + code);
</script>
```

---

# 🏛️ Section 3: Web Form Input Types

HTML5 added several input types to the `<input>` element so that browsers can validate text structures automatically and display user-friendly pickers.

---

### 1. `datetime-local`

#### Easy Definition:
Allows the user to select both a **Date** (year, month, day) and a **Time** (hours, minutes) in their local time zone.

#### Syntax:
```html
<input type="datetime-local" name="event-time">
```

#### Example:
```html
<label for="meet">Schedule Interview:</label>
<input type="datetime-local" id="meet" name="meet">
```

---

### 2. `date`

#### Easy Definition:
Displays a calendar dropdown where users can click to select a specific date (Year, Month, and Day).

#### Syntax:
```html
<input type="date" name="birthdate">
```

#### Attributes:
* `min`: Minimum date allowed.
* `max`: Maximum date allowed.

#### Example:
```html
<label for="birthday">Select Date of Birth:</label>
<input type="date" id="birthday" name="birthday" min="1995-01-01" max="2010-12-31">
```

---

### 3. `month`

#### Easy Definition:
Allows the user to select only a specific **Month** and **Year** (does not show individual days).

#### Syntax:
```html
<input type="month" name="start-month">
```

#### Example:
```html
<label for="expiry">Card Expiry Month:</label>
<input type="month" id="expiry" name="expiry">
```

---

### 4. `week`

#### Easy Definition:
Allows the user to select a specific **Week number** and **Year** (e.g., Week 26 of 2026).

#### Syntax:
```html
<input type="week" name="target-week">
```

#### Example:
```html
<label for="delivery">Select Delivery Week:</label>
<input type="week" id="delivery" name="delivery">
```

---

### 5. `time`

#### Easy Definition:
Allows the user to select a specific **Time** (Hours and Minutes). It usually shows an AM/PM toggle or clock spinner.

#### Syntax:
```html
<input type="time" name="class-time">
```

#### Example:
```html
<label for="lecture">Lecture Start Time:</label>
<input type="time" id="lecture" name="lecture">
```

---

### 6. `number`

#### Easy Definition:
An input field that allows **only numbers** to be typed. It displays up/down arrows (spinners) on the side.

#### Syntax:
```html
<input type="number" name="quantity">
```

#### Attributes:
* `min`: Minimum value allowed.
* `max`: Maximum value allowed.
* `step`: Incremental jumps (e.g., `step="2"` allows only 2, 4, 6...).

#### Example:
```html
<label for="age">Enter Age (18 to 60):</label>
<input type="number" id="age" name="age" min="18" max="60" step="1">
```

---

### 7. `range`

#### Easy Definition:
Displays a **slider bar** widget. Users slide a knob left or right to choose a value between a minimum and maximum number.

#### Syntax:
```html
<input type="range" name="slider">
```

#### Attributes:
* `min`: Start value.
* `max`: End value.
* `value`: Starting default position of the slider knob.

#### Example:
```html
<label for="volume">Volume Control:</label>
<input type="range" id="volume" name="volume" min="0" max="100" value="50" oninput="valDisplay.value=this.value">
<output id="valDisplay">50</output>%
```

---

### 8. `email`

#### Easy Definition:
A text field specifically for entering email addresses. The browser automatically checks if the text has an `@` sign and a domain name before submitting.

#### Syntax:
```html
<input type="email" name="user-email">
```

#### Example:
```html
<label for="myEmail">Enter Email Address:</label>
<input type="email" id="myEmail" name="myEmail" required placeholder="example@gmail.com">
```

---

### 9. `url`

#### Easy Definition:
A text field for web addresses. The browser validates that the input starts with a web protocol like `http://` or `https://`.

#### Syntax:
```html
<input type="url" name="website">
```

#### Example:
```html
<label for="blog">Portfolio Website URL:</label>
<input type="url" id="blog" name="blog" placeholder="https://mywebsite.com">
```

---

# 🏛️ Section 4: Audio / Video

HTML5 makes it easy to embed multimedia directly into web pages without using any software plugins like Flash.

---

### 4.1 The `<audio>` Tag

#### Easy Definition:
The `<audio>` tag is used to add audio tracks (songs, lectures, speech podcasts) to a webpage.

#### Syntax:
```html
<audio controls>
    <source src="file.mp3" type="audio/mpeg">
    Your browser does not support the audio tag.
</audio>
```

#### Attributes:
* `controls`: Displays play, pause, volume, and seek buttons. **Without this, the audio player will be invisible!**
* `autoplay`: Starts playing the music automatically when the webpage loads.
* `loop`: Restarts the music from the beginning automatically when it finishes.
* `muted`: Mutes the audio default output.

#### Code Example:
```html
<h3>Play Sample Lecture</h3>
<audio controls loop preload="metadata">
    <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mpeg">
    Your browser does not support HTML5 audio.
</audio>
```

---

### 4.2 The `<video>` Tag

#### Easy Definition:
The `<video>` tag is used to play video files or movies directly on a webpage.

#### Syntax:
```html
<video width="320" height="240" controls>
    <source src="movie.mp4" type="video/mp4">
    Your browser does not support the video tag.
</video>
```

#### Attributes:
* `controls`, `autoplay`, `loop`, `muted`: (Same functions as in the `<audio>` tag).
* `width` & `height`: Sets the width and height of the video player screen.
* `poster`: Points to an image file that will be displayed on the screen before the video starts playing.

#### Code Example:
```html
<h3>Watch Tutorial Video</h3>
<video width="480" height="270" controls poster="https://via.placeholder.com/480x270?text=HTML5+Video+Poster">
    <source src="https://www.w3schools.com/html/mov_bbb.mp4" type="video/mp4">
    Your browser does not support HTML5 video.
</video>
```

---

### 4.3 Media API Controls (JavaScript)

You can use simple JavaScript functions to control your audio or video tags using native HTML DOM commands.
* `mediaElement.play()`: Plays the media.
* `mediaElement.pause()`: Pauses the media.
* `mediaElement.volume`: Adjusts sound levels between `0.0` (silent) and `1.0` (loudest).

#### Simple Control Example Code:
```html
<!DOCTYPE html>
<html>
<head>
    <title>Simple Custom Video Control</title>
</head>
<body>

    <video id="demoVideo" width="300">
        <source src="https://www.w3schools.com/html/mov_bbb.mp4" type="video/mp4">
    </video>

    <div style="margin-top: 10px;">
        <button onclick="playVid()">Play Video</button>
        <button onclick="pauseVid()">Pause Video</button>
    </div>

    <script>
        var myVideo = document.getElementById("demoVideo");

        function playVid() {
            myVideo.play();
        }

        function pauseVid() {
            myVideo.pause();
        }
    </script>

</body>
</html>
```
