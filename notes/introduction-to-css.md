# Notes: Chapter 10 – Introducing CSS (from *HTML & CSS: Design and Build Websites* by Jon Duckett)

## 1. What CSS Does

- CSS (Cascading Style Sheets) controls how the content of an element should appear.
- You can specify: background colors, text colors, fonts, sizes, spacing, borders, layout, etc.
- CSS separates **presentation** (how it looks) from **structure** (HTML).

## 2. How CSS Works: “Thinking Inside the Box”

- Imagine every HTML element has an **invisible box** around it.
- CSS rules control the appearance of each box (and its contents).
- **Block-level elements** (e.g., `<h1>`, `<p>`, `<div>`) start on a new line.
- **Inline elements** (e.g., `<b>`, `<i>`, `<img>`, `<em>`, `<span>`) flow within text and do not start on a new line.

## 3. CSS Rules

A CSS rule consists of:

- **Selector**: indicates which element(s) the rule applies to.
- **Declaration block**: contains one or more declarations inside curly braces `{ }`.
- Each **declaration** is a **property** and a **value** pair, separated by a colon and ending with a semicolon.

Example:

```css
p {
  font-family: Arial;
  color: yellow;
}
```

- `p` is the selector.
- `font-family` and `color` are properties.
- `Arial` and `yellow` are values.

### Multiple Selectors

- You can apply the same rule to multiple elements by separating selectors with commas:

```css
h1, h2, h3 {
  font-family: Arial;
  color: yellow;
}
```

## 4. CSS Selectors (Common Types)

- **Universal selector** `*` – targets all elements.
- **Type selector** `h1, p` – targets element names.
- **Class selector** `.note` – targets elements with `class="note"`.
- **ID selector** `#intro` – targets the element with `id="intro"`.
- **Child selector** `li > a` – targets direct children.
- **Descendant selector** `p a` – targets any `<a>` inside a `<p>`.
- **Adjacent sibling** `h1 + p` – targets the first `<p>` after an `<h1>`.
- **General sibling** `h1 ~ p` – targets all `<p>` siblings after an `<h1>`.

> More selectors (attribute selectors) are covered later (page 292).

## 5. How to Add CSS to a Page

### a) External CSS (recommended)

- Place CSS rules in a separate `.css` file.
- Link it using the `<link>` element inside `<head>`:

```html
<link href="css/styles.css" type="text/css" rel="stylesheet" />
```

- Attributes:
  - `href`: path to the CSS file.
  - `type`: should be `text/css`.
  - `rel`: should be `stylesheet`.

**Advantages**:

- All pages can share the same stylesheet.
- Content stays separate from presentation.
- Change one file to update the whole site.
- Smaller HTML files, faster loading after first download.

### b) Internal CSS

- Place rules inside a `<style>` element inside `<head>`:

```html
<style type="text/css">
  body { font-family: Arial; }
</style>
```

- Useful for a single page, but not ideal for multi-page sites.

### c) Inline CSS (avoid)

- Use the `style` attribute on a specific element:

```html
<p style="color:red;">Text</p>
```

- Applies only to that element; not recommended for new sites.

## 6. Inheritance

- Some properties (e.g., `font-family`, `color`) are inherited by child elements from their parent.
- Others (e.g., `background-color`, `border`) are not inherited by default.
- You can force inheritance using `inherit` as a value.

## 7. The Cascade

- When multiple rules apply to the same element, the browser decides which takes precedence based on:
  1. **Last rule**: If selectors are identical, the later rule wins.
  2. **Specificity**: More specific selectors take precedence.
     - `*` (universal) is least specific.
     - Type selectors are more specific.
     - Class selectors are more specific than type.
     - ID selectors are more specific than class.
     - Inline styles are most specific.
  3. **`!important`**: Adding `!important` after a value makes that rule override others (use sparingly).

## 8. Browser Quirks and Testing

- Different browsers may render CSS slightly differently.
- Older browsers may not support all properties.
- Test your site in multiple browsers (and versions) and operating systems.
- Tools: BrowserCam, BrowserLab, BrowserShots, CrossBrowserTesting.
- Check for known CSS bugs on sites like PositionIsEverything.net and QuirksMode.org.

## 9. Summary (from page 243)

- CSS treats each HTML element as if it appears inside its own box.
- Rules consist of selectors and declarations.
- Declarations are property/value pairs.
- CSS rules usually live in a separate document (external stylesheet).

---

**Note:** The first CSS topic in the book (Chapter 10) is an introduction. Subsequent chapters cover specific properties: Color (Ch. 11), Text (Ch. 12), Boxes (Ch. 13), Lists/Tables/Forms (Ch. 14), Layout (Ch. 15), Images (Ch. 16), and HTML5 Layout (Ch. 17).
