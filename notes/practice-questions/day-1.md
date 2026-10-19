# Comprehensive Review Questions: Web Fundamentals, HTML Structure & CSS Introduction

These questions cover everything from today's session: the fundamentals of the web, HTML structure (Chapter 1), and introducing CSS (Chapter 10). They range from basic recall to advanced application and critical thinking.

---

# PART A: THEORY QUESTIONS

## Section 1: Fundamentals of the Web

### Basic (Recall & Understanding)

1. What is the difference between the Internet and the World Wide Web?
2. Define an IP address. What is the difference between IPv4 and IPv6?
3. What is a port number? Name the well-known ports for HTTP, HTTPS, FTP, SSH, and DNS.
4. What is a socket? How is a connection identified using sockets?
5. What does DNS stand for, and what is its primary function?
6. What is an ISP (Internet Service Provider)?
7. What is the difference between a client and a server in the client-server model?
8. What does HTTP stand for? Is HTTP stateless or stateful?
9. What is the difference between HTTP and HTTPS?
10. What is a CDN (Content Delivery Network) and why is it used?

### Intermediate (Application & Comparison)

 1. Compare TCP and UDP. Give two use cases for each.
 2. Explain the TCP three-way handshake in your own words. Why is it necessary?
 3. What is a packet? How does it relate to routers and switches?
 4. Explain the difference between a router and a switch. At which layer of the OSI model does each operate?
 5. List and describe five DNS record types. What is each used for?
 6. What is DNS propagation, and why does it take time?
 7. What is TTL in DNS? How does it affect caching and propagation?
 8. Describe the DNS resolution lifecycle step by step when a user types `www.example.com` into a browser.
 9. What is the difference between a domain registrar and a nameserver?
10. Explain the difference between public and private IP addresses.
11. What is the difference between a static and a dynamic IP address?
12. What is the difference between GET and POST HTTP methods? When should each be used?
13. List and explain the five classes of HTTP status codes (1xx–5xx). Give two examples of each.
14. What are HTTP headers? Give three examples of request headers and three examples of response headers.
15. How does HTTP manage state despite being stateless? Name three techniques.

### Advanced (Analysis & Critical Thinking)

 1. Compare HTTP/1.0, HTTP/1.1, HTTP/2, and HTTP/3. What problems did each version solve?
 2. What is head-of-line blocking? How does HTTP/2 mitigate it?
 3. What is QUIC, and how does HTTP/3 use it?
 4. Explain the TLS/SSL handshake. What is the role of certificates and Certificate Authorities (CAs)?
 5. What is the Same-Origin Policy (SOP)? Why is it important for web security?
 6. What is CORS? How does a preflight request work? Which HTTP headers are involved?
 7. What is mixed content? Why do browsers block it?
 8. What are secure cookies? Explain the `Secure`, `HttpOnly`, and `SameSite` attributes.
 9. What is the difference between browser caching and server-side caching? How does `Cache-Control` work?
10. Explain the browser rendering pipeline: parsing, DOM/CSSOM construction, style calculation, layout, paint, and composite.
11. What is the difference between parser-blocking and render-blocking resources? How do `async` and `defer` help?
12. Describe the components of a modern browser (UI, engine, rendering engine, JS engine, networking, storage).
13. Compare shared hosting, VPS, dedicated hosting, cloud hosting, and static hosting. When would you choose each?
14. What is a CSSOM? How is it constructed?
15. What is FOUC (Flash of Unstyled Content)? How does it relate to CSS rendering?

---

## Section 2: HTML Structure (Chapter 1)

### Basic (Recall & Understanding)

 1. Why is structure important in documents and web pages?
 2. What is a tag? How is a tag written in HTML?
 3. What is the difference between an opening tag and a closing tag?
 4. Define the term "element" in HTML.
 5. What is the purpose of the `<html>`, `<head>`, `<title>`, and `<body>` elements?
 6. What does the `<h1>` element represent? How is it different from `<h6>`?
 7. What is the purpose of the `<p>` element?
 8. What is an attribute? Where does it appear in an element?
 9. What two parts make up an attribute? Give an example.
10. Why should attribute names be written in lowercase?
11. What does the `lang` attribute do? Give an example of its usage.
12. What file extension must an HTML file have? Why?
13. What happens if you save an HTML file as `.txt` and open it in a browser?
14. What is the difference between the content shown in the browser window and the content in the `<head>`?
15. How can you view the source code of a web page?

### Intermediate (Application & Analysis)

 1. Write the skeleton of a basic HTML page from memory.
 2. Explain what happens if you omit the closing `</p>` tag for a paragraph. How do browsers handle it?
 3. What is the difference between `<html>` and `<body>`? Can there be content outside `<body>` that is visible?
 4. Why is the `<title>` element important for both users and search engines?
 5. In a content management system (CMS), why might you rarely see the `<html>`, `<head>`, or `<body>` elements?
 6. What are the risks of editing template files in a CMS incorrectly?
 7. Why is it good practice to use lowercase for tag names and attribute names?
 8. What is the difference between the `src` attribute and the `href` attribute (in general terms)?
 9. Explain the hierarchy of headings (`<h1>` to `<h6>`) and why you shouldn't skip levels (e.g., from `<h1>` to `<h4>`).
10. How do browsers typically display an `<h1>` element differently from a `<p>` element by default?

### Advanced (Critical Thinking & Best Practices)

 1. Why is semantic HTML important for accessibility (screen readers)?
 2. Why is semantic HTML important for SEO (search engines)?
 3. What does it mean that "HTML describes structure, not presentation"? How does this relate to CSS?
 4. What are the consequences of using multiple `<h1>` elements on a single page?
 5. Explain how the browser parses HTML into a DOM tree. What happens when it encounters malformed HTML?
 6. What is the difference between block-level and inline elements in terms of HTML structure? Give examples of each.
 7. Why is it recommended to separate content (HTML) from presentation (CSS) and behavior (JavaScript)?
 8. What is the purpose of the `<!DOCTYPE html>` declaration? What happens if you omit it?
 9. How does the browser handle an HTML file with no `<html>`, `<head>`, or `<body>` tags? (Test this to find out!)
10. Describe the evolution of HTML (HTML 4 → XHTML → HTML5) and the key differences.

---

## Section 3: Introducing CSS (Chapter 10)

### Basic (Recall & Understanding)

 1. What does CSS stand for, and what is its primary purpose?
 2. What are the three ways to add CSS to an HTML page?
 3. Which method is recommended for multi-page websites, and why?
 4. What is a CSS rule? What are its two main parts?
 5. What is a selector? Give three examples.
 6. What is a declaration? What are its two parts?
 7. What is the syntax for a CSS declaration? (Include punctuation.)
 8. What are curly braces `{ }` used for in CSS?
 9. What is the difference between a property and a value?
10. What is the universal selector? What does it do?
11. What is a class selector? How is it written?
12. What is an ID selector? How is it written?
13. What is the difference between an external stylesheet and an internal stylesheet?
14. What is the `<link>` element used for? Name its three required attributes.
15. What does the `rel="stylesheet"` attribute value mean?

### Intermediate (Application & Analysis)

1. Write a CSS rule that makes all `<p>` elements use the Arial font and have a font size of 16px.
2. Write a CSS rule that makes all `<h1>`, `<h2>`, and `<h3>` elements have a blue color.
3. Explain the difference between a type selector and a class selector. When would you use each?
4. What is the difference between `.note` and `p.note` as selectors?
5. What is the difference between `#intro` and `.intro`?
6. Explain the child selector (`li > a`) and how it differs from the descendant selector (`p a`).
7. What is the adjacent sibling selector (`h1 + p`)? Give a practical example.
8. What is the general sibling selector (`h1 ~ p`)? How does it differ from the adjacent sibling selector?
9. What is inheritance in CSS? Name two properties that are inherited and two that are not.
10. What does the `inherit` value do? Give an example.
11. Explain the cascade in CSS. What are the three factors that determine which rule wins?
12. What is specificity? Rank the following from least to most specific: `*`, `p`, `.note`, `#intro`, inline style.
13. What does `!important` do? Why should it be used sparingly?
14. If two rules have the same selector, which one wins?
15. If a type selector and a class selector apply to the same element, which wins?

### Advanced (Critical Thinking & Best Practices)

  1. Why is it generally better to use external stylesheets rather than internal or inline styles?
  2. What are the advantages and disadvantages of using a CSS framework?
  3. Explain the concept of "separation of concerns" as it applies to HTML, CSS, and JavaScript.
  4. What is a browser quirk or CSS bug? Give an example. How can you find solutions?
  5. Why should you test your site in multiple browsers? Name two online tools for cross-browser testing.
  6. What is the difference between `display: none` and `visibility: hidden`? (Note: This is from later chapters, but worth knowing.)
  7. What is the CSS box model? (Preview from Chapter 13.)
  8. How does the order of CSS rules in a stylesheet affect the final appearance of a page?
  9. What happens if you link two stylesheets and both have rules for the same element? How does the browser decide?
 10. Explain how CSS specificity works with inheritance. Does an inherited style override a directly applied style?
 11. What is the difference between `em`, `rem`, `px`, and `%` units? (Preview from Chapter 12.)
 12. Why is it recommended to avoid inline styles? Give three reasons.
 13. What is a pseudo-class? Give two examples. (Preview from Chapter 12.)
 14. What is a pseudo-element? Give two examples. (Preview from Chapter 12.)
 15. How does the `@import` rule work? Why is it generally discouraged in favor of `<link>`?

---

# PART B: CODING PRACTICE QUESTIONS

## Section 1: HTML Structure

### Basic

**B1.** Write a complete HTML document that includes:

- A `<title>` reading "My First Page"
- An `<h1>` reading "Welcome"
- A `<p>` reading "This is my first web page."

**B2.** Create an HTML page with:

- A main heading "My Favorite Books"
- A subheading "Fiction"
- Two paragraphs under the subheading describing two fictional books.

**B3.** Write HTML that includes:

- An `<h1>` with the text "About Me"
- A `<p>` with an attribute `lang="en"` and the text "I am learning web development."
- An `<h2>` with the text "My Hobbies"
- A `<p>` with the text "I enjoy reading, coding, and hiking."

**B4.** Create an HTML page with a `<title>` of "Contact Information" and a `<body>` containing:

- An `<h1>` "Contact Us"
- A `<p>` with an email address.

**B5.** Write an HTML snippet that demonstrates the correct nesting of `<html>`, `<head>`, `<title>`, and `<body>` elements.

### Intermediate

**B6.** Create a full HTML page that uses all six heading levels (`<h1>` through `<h6>`), each with descriptive text.

**B7.** Write an HTML page with:

- A `<title>` "My Recipe"
- An `<h1>` "Chocolate Cake"
- An `<h2>` "Ingredients"
- A paragraph listing ingredients.
- An `<h2>` "Instructions"
- A paragraph describing the steps.

**B8.** Create an HTML page with three paragraphs. Give the second paragraph an `id` attribute of `"highlight"` and the third paragraph a `class` attribute of `"note"`.

**B9.** Write an HTML page where the `<html>` element has a `lang` attribute set to `"fr"` (French) and the `<body>` contains a paragraph in French.

**B10.** Create an HTML page that demonstrates the difference between a `<title>` and an `<h1>`. Explain in a comment (using `<!-- -->`) what the difference is.

### Advanced

**B11.** Write an HTML page that includes:

- A `<head>` with a `<title>` and a `<meta>` description (preview from Chapter 8).
- A `<body>` with a header section (using `<h1>`), a main content section with three paragraphs, and a footer section with copyright text.
- Use comments to label each section.

**B12.** Create a "view source" experiment: Write an HTML page with deliberate errors (e.g., missing closing tags, uppercase tags). Open it in a browser and note what the browser does. Then fix the errors and compare.

**B13.** Write an HTML page that simulates a CMS template. Include placeholders like `{{title}}` and `{{content}}` inside `<h1>` and `<p>` tags, and explain (in a comment) how a CMS would replace them.

**B14.** Create an HTML document with:

- A `<title>` of "Semantic Structure"
- An `<h1>` "My Blog"
- An `<h2>` "First Post"
- A `<p>` with a `lang` attribute of `"es"` containing Spanish text.
- An `<h2>` "Second Post"
- A `<p>` with an `id` of `"post-2"`.
- Explain (in a comment) why semantic structure matters.

**B15.** Write an HTML page that includes a `<head>` with a `<title>`, a `<meta charset="UTF-8">`, and a `<link>` to an external CSS file called `styles.css`. The `<body>` should contain an `<h1>` and a `<p>`.

---

## Section 2: CSS

### Basic

**B16.** Write a CSS rule that makes all `<h1>` elements red.

**B17.** Write a CSS rule that makes all `<p>` elements use the Verdana font.

**B18.** Write a CSS rule that applies to all elements (`*`) and sets the font-family to Arial.

**B19.** Write a CSS rule that targets elements with `class="highlight"` and gives them a yellow background color.

**B20.** Write a CSS rule that targets the element with `id="main-title"` and makes its text blue.

**B21.** Write a CSS rule that applies to `<h1>`, `<h2>`, and `<h3>` and sets their color to green.

**B22.** Write an HTML page with an internal stylesheet that makes all paragraphs have a font-size of 14px and a gray color.

**B23.** Write an HTML page that links to an external stylesheet called `style.css`. The stylesheet should make all `<h1>` elements uppercase (`text-transform: uppercase;`).

**B24.** Write a CSS rule that targets any `<a>` element inside a `<p>` and sets its color to purple.

**B25.** Write a CSS rule that targets any `<a>` element that is a direct child of an `<li>` and sets its text-decoration to none.

### Intermediate

**B26.** Write a CSS rule that targets the first `<p>` element immediately after an `<h1>` element and gives it a bold font weight.

**B27.** Write CSS that demonstrates the cascade: two rules for `p`, one setting `color: red` and the other setting `color: blue`. Which wins?

**B28.** Write CSS that demonstrates specificity: a type selector and a class selector both targeting the same `<p>`. Which wins?

**B29.** Write a CSS rule using `!important` and explain what it does.

**B30.** Create an HTML page with:

- An external stylesheet (`main.css`)
- An internal `<style>` block that overrides one rule from `main.css`
- Explain the cascade order.

**B31.** Write a CSS rule that uses the universal selector to set `box-sizing: border-box` (preview from Chapter 13).

**B32.** Write a CSS rule that targets all `<input>` elements of `type="text"` (attribute selector preview).

**B33.** Write a CSS rule that targets links (`<a>`) that have been visited (`:visited`) and changes their color (pseudo-class preview).

**B34.** Write CSS that makes all `<h2>` elements inside a `<div>` have a `border-bottom` (preview from Chapter 13).

**B35.** Write a CSS rule that demonstrates inheritance: set `font-family` on `<body>` and show that `<p>` elements inherit it.

### Advanced

**B36.** Create a complete HTML page with an external CSS file that includes:

- A reset for `margin` and `padding` on all elements.
- A body font-family of `Arial, sans-serif`.
- An `<h1>` with a custom color, font-size, and text-align.
- A paragraph with a line-height of 1.6.
- A link with a hover state (preview).

**B37.** Write CSS that uses the `:first-child` and `:last-child` pseudo-classes to style the first and last list items differently (preview).

**B38.** Write a CSS rule using the `::before` pseudo-element to insert content before an `<h1>` (preview).

**B39.** Create an HTML page with two stylesheets linked in different orders. Show how the order affects the final styles. Document your findings.

**B40.** Write CSS that demonstrates the difference between `em`, `rem`, `px`, and `%` for font sizes (preview). Create a nested structure to show how `em` compounds.

**B41.** Write a CSS rule that uses a child combinator (`>`) to style only direct `<li>` children of a `<ul>`, but not nested `<li>` items.

**B42.** Write a CSS rule that uses the general sibling combinator (`~`) to style all `<p>` elements that follow an `<h2>`.

**B43.** Create an HTML page that demonstrates the `!important` flag overriding a more specific selector. Explain why this is generally bad practice.

**B44.** Write a CSS stylesheet that uses CSS variables (custom properties) for colors (preview from modern CSS).

**B45.** Write a CSS rule that uses `@media` to apply different styles for screens wider than 768px (preview).

---

## Section 3: Combined HTML + CSS (Advanced Application)

**B46.** Create a complete "About Me" page with:

- A proper HTML5 skeleton (`<!DOCTYPE html>`, `<html>`, `<head>`, `<body>`).
- A `<title>` "About [Your Name]".
- An external CSS file.
- An `<h1>` with your name.
- A `<p>` introducing yourself.
- An `<h2>` "My Skills" with a list (preview from Chapter 3).
- CSS that styles headings in one color, paragraphs in another, and adds a background color to the page.

**B47.** Create a "CSS Zen Garden" experiment:

- Create one HTML file with semantic structure (headings, paragraphs, lists).
- Create two different CSS files that dramatically change the appearance.
- Link each CSS file in turn and observe the difference.

**B48.** Build a simple "coming soon" page:

- HTML with a centered `<h1>` and `<p>`.
- CSS that centers content vertically and horizontally (using flexbox preview).
- A background color and custom fonts.

**B49.** Create a multi-page site (3 pages) where:

- All pages share the same external stylesheet.
- Each page has a navigation bar (links to the other pages).
- The current page is highlighted using a class (e.g., `.active`).

**B50.** Debug the following CSS and explain what's wrong:

```css
h1 {
  color: blue
  font-size: 24px;
}

p {
  color: red;
  font-family: Arial
}

.intro {
  color: green;
}
```

(Note the missing semicolons and any other issues.)

---

## Section 4: Web Fundamentals in Practice

**B51.** Using browser DevTools:

- Open any website.
- Go to the Network tab.
- Reload the page.
- Identify: the HTTP status code, request headers, response headers, and the time taken for the request.
- Document your findings.

**B52.** Using DevTools:

- Inspect an element on a webpage.
- Find its CSS rules.
- Identify which stylesheet each rule comes from.
- Check if any rule is overridden (crossed out) and explain why.

**B53.** Using the terminal/command line:

- Use `ping` to find the IP address of `google.com`.
- Use `nslookup` (or `dig`) to query DNS records for a domain.
- Document the output and explain what you see.

**B54.** Explore HTTP status codes:

- Visit `https://httpstat.us/404` and `https://httpstat.us/500`.
- Use DevTools to inspect the status code and response headers.
- Document what you observe.

**B55.** DNS caching experiment:

- Use `ipconfig /flushdns` (Windows) or `sudo dscacheutil -flushcache` (Mac) to clear your DNS cache.
- Visit a website you've never visited before.
- Then visit it again and observe the difference in load time.

**B56.** Secure vs. non-secure:

- Visit an HTTP-only site (if you can find one) and an HTTPS site.
- Compare the browser warnings and the padlock icon.
- Document the differences.

**B57.** CORS experiment:

- Open the DevTools console on any page.
- Try to `fetch()` a resource from a different origin (e.g., `fetch('https://api.github.com')`).
- Observe the CORS errors in the console and explain them.

**B58.** Caching headers:

- Visit a site like `https://developer.mozilla.org`.
- In DevTools Network tab, check the `Cache-Control` and `ETag` headers for CSS files.
- Explain what the values mean.

**B59.** Browser rendering:

- Open DevTools → Performance tab.
- Record a page load.
- Identify the parsing, layout, paint, and composite phases.
- Document your findings.

**B60.** Same-Origin Policy:

- Open the console on `https://example.com`.
- Try to access `document.cookie` or make a cross-origin request.
- Explain the security implications.

---

# PART C: SHORT ANSWER / EXPLANATION QUESTIONS

**C1.** In your own words, explain how a web page gets from a server to your browser. (Include DNS, TCP, HTTP, and rendering.)

**C2.** Why is it important to separate structure (HTML), presentation (CSS), and behavior (JavaScript)?

**C3.** What does "cascading" mean in CSS? How does the cascade resolve conflicts?

**C4.** Explain the difference between a class and an ID in CSS. When would you use each?

**C5.** Why is it recommended to use external stylesheets over inline styles?

**C6.** What is the difference between the Internet and the Web?

**C7.** Explain the role of DNS in the web browsing process.

**C8.** What happens when you type a URL and press Enter? (Describe the full process.)

**C9.** Why do browsers render HTML and CSS differently? How do you handle these differences as a developer?

**C10.** What is the importance of the `<head>` element? What kinds of information go inside it?

---

# PART D: DEBUGGING & TROUBLESHOOTING

**D1.** The following HTML shows the code instead of rendering it. Why?

```html
<html>
  <head>
    <title>My Page</title>
  </head>
  <body>
    <h1>Hello World</h1>
  </body>
</html>
```

(Assume the file is saved as `page.txt`.)

**D2.** The following CSS is not being applied. Why?

```html
<link href="styles.css" type="text/css" />
```

**D3.** The following CSS rule is invalid. Fix it:

```css
p {
  color: red
  font-size: 16px;
}
```

**D4.** The following HTML has a nesting error. Find and fix it:

```html
<p>This is <strong>bold text</p></strong>
```

**D5.** You have two CSS rules:

```css
p { color: blue; }
.intro { color: green; }
```

Both apply to a paragraph with `class="intro"`. What color will the text be, and why?

**D6.** You have an external stylesheet and an internal stylesheet, both with rules for `h1`. Which one wins, and why?

**D7.** A user reports that your site looks broken in Internet Explorer 8. What could be the cause? How would you fix it?

**D8.** Your CSS file is linked correctly, but the styles aren't applying. List three possible reasons.

**D9.** You've set `font-family: Arial;` but the text is still showing in Times New Roman. Why?

**D10.** You've used an ID selector `#header` and a class selector `.header` on the same element. Which style applies?

---

# PART E: PROJECT-BASED QUESTIONS

**P1.** Build a single-page "Personal Profile" website:

- Proper HTML5 structure.
- External CSS file.
- Header with your name.
- Bio paragraph.
- Skills list.
- Contact information.
- Use semantic elements (`<header>`, `<main>`, `<footer>`).
- Style with CSS: colors, fonts, spacing.

**P2.** Build a "Recipe Page":

- HTML: recipe title, ingredients list, instructions list, and an image (preview).
- CSS: styled headings, a background color, and a centered layout.

**P3.** Build a "Multi-Page Website" (3 pages):

- Home, About, Contact.
- Shared external stylesheet.
- Navigation bar with active-state styling.
- Consistent header and footer across pages.

**P4.** Recreate a simple webpage from a screenshot:

- Pick a simple webpage (e.g., a Google search page or a Wikipedia article).
- Recreate its structure with HTML.
- Style it with CSS to match the appearance as closely as possible.

**P5.** Build a "CSS Showcase":

- One HTML file with multiple sections (headings, paragraphs, lists, links, images).
- Three different CSS files (`theme-light.css`, `theme-dark.css`, `theme-colorful.css`).
- Swap the stylesheet link to see dramatic changes.

---

# ANSWER KEY / MARKING GUIDE (For Self-Assessment)

## Theory Sections

- **Basic questions** test factual recall. You should be able to answer these from memory after reviewing notes.
- **Intermediate questions** test understanding. You should be able to explain concepts in your own words and give examples.
- **Advanced questions** test critical thinking and synthesis. You should be able to compare concepts, analyze trade-offs, and propose solutions.

## Coding Sections

- **Basic coding** should work without errors and demonstrate correct syntax.
- **Intermediate coding** should demonstrate understanding of selectors, cascade, and specificity.
- **Advanced coding** should demonstrate best practices, clean structure, and problem-solving.

## Debugging Section

- D1: The file extension is `.txt`, not `.html`. Rename it.
- D2: Missing `rel="stylesheet"` attribute.
- D3: Missing semicolon after `red`.
- D4: `<strong>` opened inside `<p>` but closed outside. Fix: `<p>This is <strong>bold text</strong></p>`.
- D5: Green, because the class selector is more specific than the type selector.
- D6: The one that appears later in the document (cascade: last rule wins if specificity is equal), OR the one with higher specificity. If both are equal, the order of the `<link>` and `<style>` elements matters—the later one wins.
- D7: IE8 doesn't support HTML5 elements by default. Use the HTML5 shiv.
- D8: (1) Incorrect path, (2) missing `rel="stylesheet"`, (3) typo in CSS or HTML.
- D9: The user's computer may not have Arial installed, or another rule with higher specificity is overriding it.
- D10: The ID selector wins (higher specificity).

---

Good luck! Work through these systematically, and don't hesitate to revisit the reference book or ask for clarification on any topic. These questions are designed to build from foundational knowledge to practical mastery.
