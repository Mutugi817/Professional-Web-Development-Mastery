# Summary: Chapter 1 – Structure (from *HTML & CSS: Design and Build Websites* by Jon Duckett)

## 1. Why Structure Matters

- Documents (newspapers, insurance forms, catalogues) use structure—headlines, subheadings, paragraphs, lists—to help readers understand and navigate content.
- Web pages are similar: structure helps users (and browsers, screen readers, search engines) understand the page.

## 2. How HTML Describes Structure

- HTML pages are **text documents**.
- You add **tags** (markup) to content to give it meaning and structure.
- Tags sit inside **angle brackets** `< >`.
- Most elements have an **opening tag** and a **closing tag** (with a forward slash `/`).
- Example: `<h1>This is a Main Heading</h1>`, `<p>This is a paragraph.</p>`.
- Tags act like containers and tell the browser what the content between them is.

## 3. Elements and Tags

- An **element** comprises the opening tag, closing tag, and the content between them.
- Common structural elements:
  - `<h1>` to `<h6>`: headings (h1 largest, h6 smallest).
  - `<p>`: paragraph.
  - `<html>`: contains the whole page.
  - `<body>`: everything shown in the browser window.
  - `<head>`: information about the page (not shown in the main window).
  - `<title>`: shown in the browser tab/title bar.

## 4. Attributes

- Attributes provide extra information about an element.
- They appear in the **opening tag** only.
- Made of a **name** and a **value**, separated by an equals sign, e.g., `<p lang="en-us">`.
- Attribute names should be lowercase; values in double quotes.
- Example: `lang` specifies the language of the element’s content.

## 5. Basic Page Skeleton

```html
<html>
  <head>
    <title>This is the Title of the Page</title>
  </head>
  <body>
    <h1>This is the Body of the Page</h1>
    <p>Anything within the body is displayed in the browser window.</p>
  </body>
</html>
```

## 6. Creating a Web Page

- Use a plain text editor (Notepad on PC, TextEdit on Mac, or editors like Notepad++/TextWrangler).
- Save the file with an `.html` extension (e.g., `first-test.html`).
- Open the file in a browser to view the result.
- If saved as `.txt`, the browser will show the code instead of rendering it.

## 7. Viewing Source Code

- You can learn from other sites by viewing their source code (View → Source in the browser).
- Code may look complex at first, but it becomes understandable as you learn HTML.

## 8. Content Management Systems (CMS)

- In a CMS (e.g., WordPress, e-commerce platforms), you often edit parts of a page rather than the full HTML.
- CMSs use templates; you can sometimes edit template files or switch to an HTML/code view in the editor.
- Caution: editing template code incorrectly can break the site.

## 9. Key Takeaway

- HTML uses **tags** (elements) to describe the **structure** of a page.
- Tags usually come in pairs (opening and closing).
- Opening tags can carry **attributes** (name/value pairs) to provide more information.
- The `<html>`, `<head>`, `<title>`, and `<body>` elements form the foundation of every web page.
- To learn HTML, you need to know what tags are available, what they do, and where they can go.

---

**From the book’s summary (page 45):**

- HTML pages are text documents.
- HTML uses tags to give information special meaning.
- Tags are often called elements.
- Tags usually come in pairs (opening and closing).
- Opening tags can carry attributes.
- Attributes require a name and a value.
- Learn which tags exist, what they do, and where they can go.
