# 📚 BCA Semester - 1

## 💻 Basics Of Web Page Development

> **Course:** Bachelor of Computer Applications (BCA)  
> **Semester:** 1

---

# 📑 Unit 1 : Basic of HTML

## Topics
### Basic of HTML

- Fundamental of HTML
- Basic Tag and Attribute
- The Formatting Tags
- The List Tags & Link Tag
- Inserting special characters
- Adding images and Sound
- Table & Frame in HTML
- Forms

## Basic of HTML

HTML stands for **HyperText Markup Language**. It is the standard language used to create and design web pages. HTML describes the structure of a web page using elements called tags.

HTML is not a programming language; it is a markup language used to display content in browsers like Chrome, Firefox, etc.

---

## Fundamental of HTML

### Definition
HTML works on a structure of **tags and elements**. Each HTML document is made up of elements that tell the browser how to display content.

---

### Basic Structure of HTML Document

```html
<!DOCTYPE html>
<html>
<head>
    <title>My First Page</title>
</head>
<body>
    <h1>Hello World</h1>
    <p>This is a paragraph.</p>
</body>
</html>
```

---

### Explanation of Structure

- `<!DOCTYPE html>` → Declares HTML5 version
- `<html>` → Root element of HTML page
- `<head>` → Contains metadata (title, links, etc.)
- `<title>` → Title shown in browser tab
- `<body>` → Main content of webpage
- `<h1>` → Heading tag
- `<p>` → Paragraph tag

---

### Diagram (HTML Page Structure)

```
HTML Document
│
├── HEAD (metadata)
│     └── TITLE
│
└── BODY (content)
      ├── Heading
      ├── Paragraph
      └── Images / Links / Text
```

---

## Basic Tags and Attributes

---

## What is a Tag?

A tag is a keyword enclosed in angle brackets `< >` used to define elements in HTML.

### Types of Tags

- Opening tag: `<tag>`
- Closing tag: `</tag>`
- Self-closing tag: `<tag />`

---

## Example Tags

```html
<h1>This is Heading</h1>
<p>This is Paragraph</p>
<br>
<hr>
```

---

## What is an Attribute?

Attributes provide additional information about HTML elements. They are always written inside the opening tag.

---

### Syntax

```html
<tag attribute="value">Content</tag>
```

---

## Common Attributes

| Attribute | Description |
|-----------|------------|
| id        | Unique identifier |
| class     | Group elements |
| style     | CSS styling |
| src       | Source file (images/videos) |
| href      | Link reference |
| alt       | Alternative text for images |

---

## Example of Attributes

```html
<a href="https://example.com">Click Here</a>

<img src="image.jpg" alt="My Image">

<p style="color:red;">This is red text</p>
```

---

## Diagram (Tag + Attribute)

```
<tag attribute="value">Content</tag>

Example:
<a href="link">Visit Site</a>
```

---

## Key Points

- Tags define structure of webpage
- Attributes provide extra information
- HTML is case-insensitive (but lowercase is recommended)
- Every HTML document starts with `<!DOCTYPE html>`

## The Formatting Tags

### Definition
Formatting tags in HTML are used to change the appearance of text such as bold, italic, underline, highlight, and more. They help in improving readability and structure of content.

---

### Common Formatting Tags

| Tag | Description |
|-----|------------|
| `<b>` | Bold text |
| `<strong>` | Important bold text |
| `<i>` | Italic text |
| `<em>` | Emphasized text |
| `<u>` | Underlined text |
| `<mark>` | Highlight text |
| `<small>` | Smaller text |
| `<del>` | Deleted (strikethrough) text |
| `<ins>` | Inserted text |
| `<sub>` | Subscript text |
| `<sup>` | Superscript text |

---

### Example

```html
<p><b>Bold Text</b></p>
<p><i>Italic Text</i></p>
<p><u>Underlined Text</u></p>
<p><mark>Highlighted Text</mark></p>
<p>H<sub>2</sub>O</p>
<p>X<sup>2</sup></p>
```

---

### Output (Conceptual)

```
Bold Text
Italic Text
Underlined Text
Highlighted Text
H2O
X²
```

---

## The List Tags

### Definition
List tags are used to display data in ordered or unordered format. They help in structuring items in a proper sequence or bullet format.

---

### Types of Lists

---

## 1. Ordered List

### Definition
An ordered list displays items in a numbered format.

### Tag
```html
<ol>
```

### Example

```html
<ol>
    <li>Apple</li>
    <li>Banana</li>
    <li>Mango</li>
</ol>
```

### Output
```
1. Apple
2. Banana
3. Mango
```

---

## 2. Unordered List

### Definition
An unordered list displays items with bullets.

### Tag
```html
<ul>
```

### Example

```html
<ul>
    <li>Apple</li>
    <li>Banana</li>
    <li>Mango</li>
</ul>
```

### Output
```
• Apple
• Banana
• Mango
```

---

## 3. Description List

### Definition
A description list is used to display terms and their descriptions.

### Tags
```html
<dl>, <dt>, <dd>
```

### Example

```html
<dl>
    <dt>HTML</dt>
    <dd>HyperText Markup Language</dd>

    <dt>CSS</dt>
    <dd>Cascading Style Sheets</dd>
</dl>
```

---

## The Link Tag

### Definition
The link tag (`<a>`) is used to create hyperlinks that connect one page to another page or website.

---

### Syntax

```html
<a href="URL">Link Text</a>
```

---

### Example

```html
<a href="https://www.google.com">Go to Google</a>
```

---

### Attributes of Link Tag

| Attribute | Description |
|-----------|------------|
| href | Specifies URL |
| target | Defines where to open link |
| title | Tooltip text |

---

### Example with Attributes

```html
<a href="https://example.com" target="_blank" title="Open Website">
    Visit Website
</a>
```

---

### Output (Conceptual)

```
Clicking link opens new webpage
```

---

## Key Points

- Formatting tags change text appearance
- List tags organize data in structured form
- Link tag connects web pages using hyperlinks

## Inserting Special Characters in HTML

### Definition
Special characters are symbols that are not directly available on the keyboard or may conflict with HTML syntax. In HTML, they are written using **HTML entities**.

---

### Syntax

```html
&entity_name;
```

or

```html
&#entity_number;
```

---

### Common Special Characters

| Character | Entity Name | Description |
|----------|-------------|-------------|
| <        | &lt;        | Less than |
| >        | &gt;        | Greater than |
| &        | &amp;       | Ampersand |
| "        | &quot;      | Double quote |
| '        | &apos;      | Single quote |
| ©        | &copy;      | Copyright |
| ₹        | &#8377;     | Indian Rupee |
| ™        | &trade;     | Trademark |

---

### Example

```html
<p>5 &lt; 10</p>
<p>AT&amp;T Company</p>
<p>&copy; 2026 My Website</p>
<p>Price: &#8377;500</p>
```

---

### Output (Conceptual)

```
5 < 10
AT&T Company
© 2026 My Website
Price: ₹500
```

---

## Adding Images in HTML

### Definition
Images are added in HTML using the `<img>` tag. It is a self-closing tag used to display pictures on a web page.

---

### Syntax

```html
<img src="image_path" alt="description">
```

---

### Attributes

| Attribute | Description |
|----------|------------|
| src      | Image path (URL or file location) |
| alt      | Alternate text if image not loaded |
| width    | Image width |
| height   | Image height |

---

### Example

```html
<img src="photo.jpg" alt="My Photo" width="200" height="200">
```

---

### Diagram

```
Web Page
   ↓
<img> tag
   ↓
Displays Image
```

---

### Key Points

- Image must be in correct path
- `alt` is important for accessibility
- Images improve webpage design

---

## Adding Sound in HTML

### Definition
Sound can be added in HTML using the `<audio>` tag. It allows users to play audio files on a web page.

---

### Syntax

```html
<audio controls>
    <source src="audio.mp3" type="audio/mpeg">
</audio>
```

---

### Attributes

| Attribute | Description |
|----------|------------|
| controls | Shows play/pause buttons |
| autoplay | Plays audio automatically |
| loop     | Repeats audio |
| muted    | Mutes audio by default |

---

### Example

```html
<audio controls>
    <source src="music.mp3" type="audio/mpeg">
    Your browser does not support audio.
</audio>
```

---

### Output (Conceptual)

```
Audio player with play / pause button
```

---

### Key Points

- `<audio>` tag is used for sound
- `controls` is required for user interaction
- Multiple formats can be added for compatibility

## Table in HTML

### Concept of Table
An HTML table is used to arrange data in **rows and columns** format. It is mainly used to represent structured data like student records, marksheets, timetables, etc.

A table is made using a combination of rows and columns where:
- Each **row** contains data horizontally
- Each **column** contains data vertically

---

### Table Structure Diagram

```
+------+--------+-------+
| ID   | Name   | Marks |
+------+--------+-------+
| 1    | Rahul  | 85    |
| 2    | Amit   | 90    |
+------+--------+-------+
```

---

### Basic Tags Used in Table

- `<table>` → Defines table
- `<tr>` → Table row
- `<th>` → Table heading (bold + center)
- `<td>` → Table data

---

### Syntax

```html
<table>
    <tr>
        <th>Column 1</th>
        <th>Column 2</th>
    </tr>

    <tr>
        <td>Data 1</td>
        <td>Data 2</td>
    </tr>
</table>
```

---

### Example with Explanation

```html
<table border="1">
    <tr>
        <th>ID</th>
        <th>Name</th>
        <th>Marks</th>
    </tr>

    <tr>
        <td>1</td>
        <td>Rahul</td>
        <td>85</td>
    </tr>

    <tr>
        <td>2</td>
        <td>Amit</td>
        <td>90</td>
    </tr>
</table>
```

---

### Output (Concept)

```
ID   Name   Marks
1    Rahul  85
2    Amit   90
```

---

### Key Points of Table

- Used for structured data representation
- `<tr>` creates row structure
- `<th>` is used for headings
- `<td>` is used for actual data
- Can be styled using CSS for better design

---

---

## Frame in HTML

### Concept of Frame
Frames in HTML are used to **divide a browser window into multiple sections**, where each section can load a different webpage.

Each frame works independently, meaning one frame can display one page while another frame displays a different page.

---

### Frame Structure Diagram

```
+-----------------------------+
|     Frame 1 |  Frame 2     |
|   Page A    |   Page B     |
+-----------------------------+
```

---

### Basic Tags Used in Frame

- `<frameset>` → Defines how page is divided
- `<frame>` → Loads individual page inside frame

---

### Syntax

```html
<frameset cols="50%,50%">
    <frame src="page1.html">
    <frame src="page2.html">
</frameset>
```

---

### Example

```html
<html>
    <frameset rows="50%,50%">

        <frame src="top.html">
        <frame src="bottom.html">

    </frameset>
</html>
```

---

### Explanation

- `rows="50%,50%"` → divides page horizontally
- `cols="50%,50%"` → divides page vertically
- Each `<frame>` loads separate HTML file

---

### Types of Frame Layout

- Rows Frame → Horizontal division
- Columns Frame → Vertical division
- Mixed Frame → Combination of rows and columns

---

### Key Points of Frame

- Used to divide web page into multiple parts
- Each frame loads different HTML document
- Helps in navigation-based layout
- Now deprecated in HTML5
- Replaced by `<iframe>` and CSS layout techniques

## Forms in HTML

---

## Concept of Forms

An HTML form is used to collect user input and send it to a server for processing. Forms are widely used in websites for login, registration, surveys, feedback, and data entry.

A form acts as a **bridge between user and server**.

---

### Form Working Diagram

```
User Input → HTML Form → Server → Database → Response
```

---

## Basic Structure of Form

```html
<form action="server_page.php" method="POST">
    <!-- input elements -->
</form>
```

---

## Important Attributes of `<form>`

| Attribute | Description |
|----------|------------|
| action   | Specifies where form data will be sent |
| method   | Defines HTTP method (GET or POST) |
| name     | Name of the form |
| target   | Where to display response (_blank, _self) |

---

## Input Elements in Form

Forms use different input elements to collect data.

---

## Common Form Tags

- `<input>`
- `<label>`
- `<textarea>`
- `<select>`
- `<option>`
- `<button>`
- `<fieldset>`
- `<legend>`

---

## Types of Input Fields

| Type | Description |
|------|------------|
| text | Single line text |
| password | Hidden text input |
| email | Email input validation |
| number | Numeric input |
| radio | Select one option |
| checkbox | Select multiple options |
| submit | Submit form |
| reset | Clear form |

---

## Example 1: Simple Registration Form

```html
<form action="submit.php" method="POST">

    <label>Name:</label>
    <input type="text" name="name"><br><br>

    <label>Email:</label>
    <input type="email" name="email"><br><br>

    <label>Password:</label>
    <input type="password" name="password"><br><br>

    <input type="submit" value="Register">

</form>
```

---

## Output (Concept)

```
Name: [_________]
Email: [_________]
Password: [_________]
[Register Button]
```

---

## Example 2: Radio Button Form

```html
<form>

    <p>Select Gender:</p>

    <input type="radio" name="gender" value="male"> Male
    <input type="radio" name="gender" value="female"> Female

</form>
```

---

## Example 3: Checkbox Form

```html
<form>

    <p>Select Skills:</p>

    <input type="checkbox" name="skill" value="HTML"> HTML
    <input type="checkbox" name="skill" value="CSS"> CSS
    <input type="checkbox" name="skill" value="JS"> JavaScript

</form>
```

---

## Example 4: Dropdown List

```html
<form>

    <label>City:</label>

    <select name="city">
        <option>Rajkot</option>
        <option>Ahmedabad</option>
        <option>Surat</option>
    </select>

</form>
```

---

## Example 5: Textarea (Multi-line Input)

```html
<form>

    <label>Message:</label><br>

    <textarea rows="4" cols="30"></textarea>

</form>
```

---

## Fieldset Example (Grouping Form Data)

```html
<form>

    <fieldset>
        <legend>Login Details</legend>

        Username: <input type="text"><br><br>
        Password: <input type="password">

    </fieldset>

</form>
```

---

## Key Points of Forms

- Used for user data collection
- Sends data to server using GET/POST
- Contains multiple input types
- Important for login, registration, feedback systems
- Can be validated using HTML or JavaScript

## HTML Form with JavaScript (Full Example)

---

## Concept

This example shows how an HTML form collects user data and JavaScript processes it using the **name attribute**. The `name` attribute is used to access form values inside JavaScript.

---

## Working Flow

```
User Input → HTML Form → JavaScript (Validation + Display) → Output
```

---

## Full Example Code

```html
<!DOCTYPE html>
<html>
<head>
    <title>Form with JavaScript</title>

    <script>
        function showData()
        {
            // Accessing values using name attribute
            var name = document.myForm.username.value;
            var email = document.myForm.email.value;
            var password = document.myForm.password.value;

            // Display output
            alert("Name: " + name + "\nEmail: " + email + "\nPassword: " + password);
        }
    </script>
</head>

<body>

<h2>Registration Form</h2>

<form name="myForm">

    Name:
    <input type="text" name="username"><br><br>

    Email:
    <input type="email" name="email"><br><br>

    Password:
    <input type="password" name="password"><br><br>

    <input type="button" value="Submit" onclick="showData()">

</form>

</body>
</html>
```

---

## Explanation

### 1. `name="myForm"`
- Gives name to form
- Used in JavaScript to access form

---

### 2. `name="username"`
- Input field name
- Used to get value:
```javascript
document.myForm.username.value
```

---

### 3. JavaScript Function

```javascript
function showData()
```

- Runs when button is clicked
- Collects form data
- Shows output using alert box

---

## Output Example

When user enters:

```
Name: Rahul
Email: rahul@gmail.com
Password: 1234
```

### Alert Output:

```
Name: Rahul
Email: rahul@gmail.com
Password: 1234
```

---

## Key Points

- `name` attribute is very important in JavaScript form handling
- JavaScript is used for validation and processing
- `onclick` event triggers function
- Data is accessed using:
  ```
  document.formName.fieldName.value
  ```

---

