# Comprehensive Notes: Hyperlinks, URLs, Lists & Related Topics

---

# 1. Hyperlinks

## 1.1 What Is a Hyperlink?

A **hyperlink** (or link) is a reference from one document to another (or to another part of the same document). It is the defining feature of the web—it enables **browsing/surfing** by allowing users to jump from page to page.

> Book reference (page 75): *"Links are the defining feature of the web because they allow you to move from one web page to another — enabling the very idea of browsing or surfing."*

## 1.2 The Anchor Element

Links are created with the `<a>` (anchor) element:

```html
<a href="https://www.example.com">Visit Example</a>
```

- **`<a>`** — the anchor element.
- **`href`** — Hypertext REFerence. The value is the URL of the destination.
- The **text between** the opening and closing tags is the **link text**.

## 1.3 Link Text Best Practices

- Link text should **describe the destination** ("hotels in New York" not "click here").
- Clear link text helps:
  - Users who **scan** pages for links.
  - People using **screen readers** (who may navigate link-by-link).
  - **Search engines** (SEO — keywords in link text matter).

## 1.4 Types of Links (Common Uses)

- Links from one website to another.
- Links from one page to another on the same site.
- Links to a specific part of the same page.
- Links that open in a new browser window/tab.
- Links that start up an email program.
- Links that download a file.
- Links that dial a phone number or send an SMS (on mobile).

---

# 2. Absolute vs. Relative URLs

## 2.1 URL — Uniform Resource Locator

Every web page and image on a website has a **URL** — the web address. It consists of:

```
scheme://domain:port/path?query#fragment
```

Example:

```
https://www.example.com:443/products/index.html?id=5#reviews
```

| Part | Example | Meaning |
| ------ | --------- | --------- |
| Scheme (protocol) | `https` | How to communicate |
| Domain | `www.example.com` | Where the server is |
| Port | `:443` | Which service (usually omitted) |
| Path | `/products/index.html` | Which file/page |
| Query | `?id=5` | Parameters |
| Fragment | `#reviews` | A specific part of the page |

## 2.2 Absolute URLs

An **absolute URL** includes the **full address** — the domain name, path, and (optionally) protocol:

```html
<a href="https://www.example.com/products/index.html">Products</a>
```

- Always starts with a **domain name** (and often `https://`).
- Works **anywhere** — in a document, email, or from any site.
- Required when linking to **another website**.

## 2.3 Relative URLs

A **relative URL** is a shortcut that describes where a file is **relative to the current page**. It does **not** include the domain name.

Relative URLs are useful because:

- You can link pages **before** the site goes live (on your local machine).
- They are **shorter** and **quicker to write**.
- They "travel with" your site if the domain changes.

The same link may need **different relative URLs** depending on which page you're linking from.

### Directory Structure (Folder Hierarchy)

To understand relative URLs, think of the site's folders as a family tree:

```
root/ (called examples)
├── index.html                 (homepage)
├── images/
│   └── logo.gif
└── movies/
    ├── index.html
    ├── reviews.html
    └── dvd/
        └── reviews.html
```

- The **root folder** contains everything.
- **Parent, child, grandchild, grandparent** relationships are used.

### Relative URL Rules (Book pages 83–84)

| Relation | How to write | Example |
| ---------- | ------------- | --------- |
| **Same folder** | Just the file name | `href="reviews.html"` |
| **Child folder** | Folder name + `/` + file | `href="movies/reviews.html"` |
| **Grandchild folder** | Folder `/` folder `/` file | `href="movies/dvd/reviews.html"` |
| **Parent folder** | `../` + file name | `href="../index.html"` |
| **Grandparent folder** | `../../` + file name | `href="../../index.html"` |

### Other Relative URL Shortcuts (Live Sites Only)

- `href="/"` → homepage of the **entire site** (root).
- `href="/images/"` → a folder (server may serve its `index.html`).
- `href="movies/"` → the homepage of the movies section (server-dependent).

> These trailing-slash shortcuts often depend on the web server's configuration and may not work when viewing files locally.

## 2.4 When to Use Which

| Use Absolute When… | Use Relative When… |
| -------------------- | -------------------- |
| Linking to **another website** | Linking to **another page on your own site** |
| Email signatures, external references | Internal navigation |
| Linking to CDNs / external assets | Images, CSS, scripts on your own server |

---

# 3. Link Targets

## 3.1 The `target` Attribute

The `target` attribute specifies **where** the linked document should be opened.

| Value | Behavior |
| ------- | ---------- |
| `_self` | Opens in the **same tab/window** (default) |
| `_blank` | Opens in a **new tab/window** |
| `_parent` | Opens in the **parent frame** (relevant with `<iframe>`) |
| `_top` | Opens in the **full body of the window** (breaks out of all frames) |
| *custom name* | Opens in the **named frame/window** if it exists |

Example:

```html
<a href="https://www.imdb.com" target="_blank">IMDb</a>
```

## 3.2 Best Practices for `_blank`

- Use `_blank` **sparingly** — it can be disorienting for users.
- When you do, **inform the user** the link opens in a new window (in the link text or adjacent text).
- Common use case: linking to **external websites** — so the user's site stays open behind it.

---

# 4. Link Security & Performance

## 4.1 The `_blank` Vulnerability — `rel="noopener"`

**Security issue:** Modern browsers allow a page opened with `target="_blank"` to access the referring page via `window.opener`. A malicious site can redirect the original tab (a "reverse tabnabbing" attack).

**Fix: add `rel="noopener"`:**

```html
<a href="https://untrusted-site.com" target="_blank" rel="noopener">Link</a>
```

- `noopener` — prevents the new page from accessing `window.opener`.
- In modern browsers, `target="_blank"` **implicitly** gets `noopener` behavior, but adding it explicitly supports older browsers.

## 4.2 `rel="noreferrer"`

```html
<a href="https://example.com" target="_blank" rel="noreferrer">Link</a>
```

- Prevents the browser from sending the **`Referer` header** (so the destination doesn't know where the user came from).
- Also implies `noopener`.
- Use when privacy is a concern or when you don't want the destination to see your URL.

## 4.3 `rel="nofollow"` (SEO)

```html
<a href="https://example.com" rel="nofollow">Link</a>
```

- Tells search engines **not to "follow"** the link for ranking purposes — i.e., don't pass "link juice."
- Commonly used for: user-generated content, paid links, untrusted sites.

Related values: `sponsored` (paid links), `ugc` (user-generated content).

## 4.4 Performance-Related Link Hints

These are `<link>` hints in `<head>` (not `<a>` links), but related to "link performance":

| Attribute | Purpose |
| ----------- | --------- |
| `rel="preload"` | Fetch a resource **early**, high priority (fonts, key CSS, scripts) |
| `rel="prefetch"` | Fetch a resource **in advance** for likely future navigation (low priority) |
| `rel="preconnect"` | Establish a **connection** to an origin early (saves DNS/TCP/TLS time) |
| `rel="dns-prefetch"` | Resolve **DNS** early |
| `rel="prerender"` | Render a page in the background (deprecated in many browsers) |

Example:

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preload" href="fonts/myfont.woff2" as="font" type="font/woff2" crossorigin>
```

**`a` element hint attributes:**

- **`rel="external"`** — indicates the destination is a different site.
- **`rel="help"`, `rel="next"`, `rel="prev"`** — navigational semantics.
- **`rel="author"`** — link to the author.

## 4.5 Performance: Reduce Redirects & Link to Fast Resources

- Each link that redirects adds latency.
- Prefer direct, final URLs.
- Avoid linking to bloated resources where possible.

---

# 5. Anchor Links & Page Jumps

## 5.1 Linking to a Specific Part of the Same Page

To jump to a section **within the same page**:

1. Give the target element an **`id`**:

   ```html
   <h2 id="reviews">Reviews</h2>
   ```

2. Link using `#` + the id:

   ```html
   <a href="#reviews">Go to Reviews</a>
   ```

The URL fragment (`#reviews`) tells the browser to scroll that element into view.

**Rules for `id`:**

- Must be **unique** on the page.
- Should start with a letter or underscore (not a number).
- Case-sensitive (in practice, HTML5 ids are case-sensitive).
- No spaces (use `-` or `_` if needed).

## 5.2 Linking to a Specific Part of Another Page

```html
<a href="products.html#reviews">See Reviews</a>
<a href="https://www.example.com/faq.html#shipping">Shipping FAQ</a>
```

Combines the page's URL + `#` + the id of the target element.

## 5.3 "Back to Top" Links

```html
<a href="#top">Back to top</a>
<!-- And at the top: -->
<h1 id="top">Title</h1>
```

**Modern alternative:** the special fragment **`#top`** scrolls to the top of the document **even without an element with `id="top"`**.

## 5.4 Table of Contents (TOC) Pattern

Long pages often use a list of anchor links at the top:

```html
<nav>
  <ul>
    <li><a href="#intro">Introduction</a></li>
    <li><a href="#features">Features</a></li>
    <li><a href="#pricing">Pricing</a></li>
  </ul>
</nav>
...
<h2 id="intro">Introduction</h2>
```

## 5.5 CSS `:target`

You can style the element that has been targeted via fragment:

```css
:target {
  background-color: yellow;
  scroll-margin-top: 80px; /* leave space for sticky header */
}
```

**`scroll-behavior: smooth`** enables smooth scrolling:

```css
html {
  scroll-behavior: smooth;
}
```

---

# 6. Download Links

## 6.1 The `download` Attribute

The `download` attribute on `<a>` tells the browser to **download** the linked resource rather than navigate to it:

```html
<a href="files/report.pdf" download>Download Report</a>
```

## 6.2 Specifying a Filename

```html
<a href="files/report.pdf" download="annual-report-2024.pdf">Download</a>
```

- The value is the **suggested filename** in the save dialog.
- The browser **may ignore** it for **cross-origin** links (security restriction—only same-origin downloads can rename files).
- The server's `Content-Disposition` header (e.g., `attachment; filename="..."`) is another way to force downloads server-side.

## 6.3 Best Practices

- Use `download` **only when a download is intended** — not for normal navigation.
- Provide the file type and size in the link text where useful:

  ```html
  <a href="report.pdf" download>Download report (PDF, 2 MB)</a>
  ```

- Don't rely on `download` alone — the server should also send appropriate headers (`Content-Type`, `Content-Disposition`).

---

# 7. Protocol Links

These are links whose `href` starts with a **protocol scheme** other than `http`/`https`. They trigger OS/browser actions.

## 7.1 Email — `mailto:`

```html
<a href="mailto:someone@example.com">Email us</a>
```

**Add subject, body, CC, BCC (query parameters):**

```html
<a href="mailto:someone@example.com?subject=Hello&body=Hi%20there&cc=team@example.com">
  Email us
</a>
```

- URL-encode values (`%20` for space, `&` for ampersand when needed).
- Opens the user's **default email client**.
- Does **not** send email by itself (needs the client).

## 7.2 Telephone — `tel:`

```html
<a href="tel:+15555550123">Call us</a>
```

- On mobile devices, opens the **phone dialer**.
- On desktop, may trigger a calling app or do nothing.
- Use international format (`+1...`).

## 7.3 SMS — `sms:`

```html
<a href="sms:+15555550123?body=Hello">Text us</a>
```

- Opens the **messaging app** with an optional pre-filled body (support varies).

## 7.4 `javascript:` URIs (Legacy — Avoid)

```html
<a href="javascript:void(0)">Do nothing</a>
```

- Executes JavaScript instead of navigating.
- **Discouraged** — breaks accessibility, security (CSP), and separation of concerns.
- Use `<button>` + event listeners instead.

## 7.5 `data:` URIs

Embeds small data directly in a link (e.g., base64-encoded image or text):

```html
<a href="data:text/plain;charset=utf-8,Hello%20World" download="hello.txt">Download text</a>
```

- No network request needed.
- Not ideal for larger files (URL length limits, no caching).

## 7.6 `ftp:` — Legacy

```html
<a href="ftp://ftp.example.com/file.zip">Download</a>
```

- Largely **obsolete** — most browsers have dropped FTP support. Use HTTPS.

---

# 8. Navigation Sections

## 8.1 The `<nav>` Element (HTML5)

The `<nav>` element defines a **major block of navigation links**:

```html
<nav>
  <ul>
    <li><a href="index.html">Home</a></li>
    <li><a href="about.html">About</a></li>
    <li><a href="contact.html">Contact</a></li>
  </ul>
</nav>
```

- Use for **primary site navigation** (not every link list).
- Screen readers can **jump to `<nav>`** (landmark).
- You can have **multiple `<nav>` elements** (e.g., primary + footer), and label them with `aria-label`:

```html
<nav aria-label="Main">
  ...
</nav>
<nav aria-label="Footer">
  ...
</nav>
```

## 8.2 Navigation Best Practices (Book pages 471–472)

| Principle | Description |
| ----------- | ------------- |
| **Concise** | Limit primary links (ideally ≤ 8) |
| **Clear** | Users should predict where a link goes |
| **Selective** | Primary nav = sections; keep logins/search/legal separate |
| **Context** | Highlight the **current page** (e.g., `.current` class) |
| **Interactive** | Links big enough to tap; hover/focus styles |
| **Consistent** | Primary nav should be the **same** across pages |

## 8.3 Types of Navigation

- **Primary** — top or left side (main sections).
- **Secondary** — sub-navigation (under primary or sidebar).
- **Tertiary** — footer (privacy, terms, etc.).
- **Breadcrumbs** — path from homepage to current page.
- **Skip links** — "Skip to content" for keyboard/screen-reader users.

## 8.4 Accessibility: Skip Navigation

```html
<a href="#main" class="skip-link">Skip to main content</a>
...
<main id="main">...</main>
```

This lets keyboard users bypass the nav.

## 8.5 Styling Links with `:link`, `:visited`, `:hover`, `:focus`, `:active`

Must appear in this order (LVHA-ish, with focus before active):

```css
a:link    { color: blue; }
a:visited { color: purple; }
a:hover   { text-decoration: underline; }
a:focus   { outline: 2px solid; }
a:active  { color: red; }
```

- `.current` class for the active page:

```css
nav a.current {
  color: #000;
  font-weight: bold;
  border-bottom: 2px solid;
}
```

---

# 9. Unordered Lists

## 9.1 The `<ul>` Element

A **bullet list** — items that do **not** need to be in order:

```html
<ul>
  <li>Milk</li>
  <li>Bread</li>
  <li>Eggs</li>
</ul>
```

- `<ul>` = unordered list container.
- `<li>` = list item (one per `<li>`).

## 9.2 When to Use

- Items whose order doesn't matter (shopping list, menu items, navigation).
- Groups of related items.

## 9.3 Styling Bullets

```css
ul {
  list-style-type: disc;   /* disc (default), circle, square, none */
}
```

## 9.4 Using Images as Bullets

```css
ul {
  list-style-image: url("images/star.png");
}
li {
  margin: 10px 0 0 0;
}
```

## 9.5 List Marker Position

```css
ul.outside { list-style-position: outside; } /* default */
ul.inside  { list-style-position: inside; }
```

## 9.6 List Style Shorthand

```css
ul {
  list-style: inside circle;
}
```

## 9.7 Nested Unordered Lists

```html
<ul>
  <li>Mousses</li>
  <li>Pastries
    <ul>
      <li>Croissant</li>
      <li>Mille-feuille</li>
      <li>Palmier</li>
    </ul>
  </li>
  <li>Tarts</li>
</ul>
```

- Nested lists are indented further; browsers often change the bullet style (e.g., disc → circle → square).

## 9.8 Removing Bullets (Navigation Pattern)

```css
ul {
  list-style: none;
  padding: 0;
  margin: 0;
}
```

Then style `<a>` as buttons.

---

# 10. Ordered Lists

## 10.1 The `<ol>` Element

A **numbered list** — items whose order matters:

```html
<ol>
  <li>Chop potatoes into quarters</li>
  <li>Simmer in salted water for 15–20 minutes</li>
  <li>Heat milk, butter and nutmeg</li>
  <li>Drain potatoes and mash</li>
  <li>Mix in the milk mixture</li>
</ol>
```

## 10.2 When to Use

- Steps that must be performed **in order** (recipes, instructions).
- Legal contracts / numbered clauses.
- Ranking / priority lists.

## 10.3 Styling Number Types

```css
ol {
  list-style-type: decimal;            /* 1, 2, 3 (default) */
  /* decimal-leading-zero: 01, 02, 03 */
  /* lower-alpha: a, b, c */
  /* upper-alpha: A, B, C */
  /* lower-roman: i, ii, iii */
  /* upper-roman: I, II, III */
}
```

## 10.4 The `start` and `reversed` Attributes

```html
<ol start="5">...</ol>
<ol reversed>...</ol>
```

## 10.5 The Old `type` Attribute (Deprecated)

Old code may use `<ol type="a">`; modern practice is CSS (`list-style-type`).

---

# 11. Description (Definition) Lists

## 11.1 The `<dl>` Element

A **description list** pairs **terms** with their **definitions/descriptions**:

```html
<dl>
  <dt>Sashimi</dt>
  <dd>Sliced raw fish served with condiments such as shredded daikon, wasabi and soy sauce</dd>

  <dt>Scale</dt>
  <dd>A device used to accurately measure the weight of ingredients</dd>
  <dd>A technique by which the scales are removed from the skin of a fish</dd>

  <dt>Scamorze</dt>
  <dt>Scamorzo</dt>
  <dd>An Italian cheese usually made from whole cow's milk</dd>
</dl>
```

| Tag | Meaning | Role |
| ----- | --------- | ------ |
| `<dl>` | Description list | Container |
| `<dt>` | Definition term | The **term** being defined |
| `<dd>` | Definition description | The **definition/explanation** |

## 11.2 Key Features

- One term can have **multiple** `<dd>` (multiple definitions).
- **Multiple `<dt>`** can share one `<dd>` (synonyms, like "Scamorze"/"Scamorzo").
- Browsers typically **indent** `<dd>` by default.

## 11.3 When to Use

- Glossaries, dictionaries, terminology lists.
- **Metadata pairs** — e.g., product name / price / description.
- **FAQ** items (question / answer).
- Not for navigation — use `<ul>` / `<ol>` for menus.

## 11.4 Styling

```css
dd { margin-left: 40px; }
```

You can create a two-column definition layout using `display: flex` or `grid` (modern practice).

---

# 12. Open Graph and Social Media Tags

## 12.1 The Problem

When a link is shared on **Facebook, Twitter/X, LinkedIn, Slack, WhatsApp**, etc., how does the platform know what **title, image, and description** to display? It relies on **meta tags**.

## 12.2 Open Graph (OG) — Introduced by Facebook in 2010

Place these **inside `<head>`**:

```html
<meta property="og:title"       content="Awesome Article">
<meta property="og:description" content="Learn about hyperlinks and lists.">
<meta property="og:image"       content="https://example.com/images/preview.jpg">
<meta property="og:url"         content="https://example.com/article">
<meta property="og:type"        content="article"> <!-- website, article, video, product, etc. -->
<meta property="og:site_name"   content="My Site">
<meta property="og:locale"      content="en_US">
```

**Required/recommended core OG properties:**

- `og:title` — page title (often ~60 chars).
- `og:description` — summary (~1–2 sentences).
- `og:image` — image URL (**absolute URL required**, recommended 1200×630 px, 1.91:1 ratio).
- `og:url` — the canonical URL of the page.
- `og:type` — `website`, `article`, `video.movie`, `product`, etc.

## 12.3 Twitter/X Cards

```html
<meta name="twitter:card"        content="summary_large_image">
<meta name="twitter:title"       content="Awesome Article">
<meta name="twitter:description" content="Learn about hyperlinks and lists.">
<meta name="twitter:image"       content="https://example.com/images/preview.jpg">
<meta name="twitter:site"        content="@mysite">     <!-- account name -->
<meta name="twitter:creator"     content="@author">     <!-- author -->
```

Card types:

- `summary` — small image on side.
- `summary_large_image` — big image on top.
- `player`, `app`.

**Note:** X/Twitter also reads OG tags as fallbacks.

## 12.4 Other Platforms

- **LinkedIn** uses OG primarily.
- **Pinterest** uses OG + its own `pinterest:description`.
- **WhatsApp, Slack, Telegram** generally read OG tags.

## 12.5 Testing & Validation

- **Facebook Sharing Debugger**: `developers.facebook.com/tools/debug/`
- **X/Twitter Card Validator**: `cards-dev.twitter.com/validator`
- **LinkedIn Post Inspector**: `linkedin.com/post-inspector/`

## 12.6 Best Practices

- **`og:image` must be an absolute URL** (not relative).
- Include **width/height hints** where supported: `og:image:width`, `og:image:height`, `og:image:type`, `og:image:alt`.
- Set a **fallback** for platforms that don't support OG (`<title>`, `<meta name="description">`).
- Ensure the image is publicly accessible.
- Use **`og:url` = canonical URL** so shares consolidate.

**Example full block:**

```html
<meta property="og:type"        content="website">
<meta property="og:url"         content="https://example.com/">
<meta property="og:title"       content="Example – Learn Web Development">
<meta property="og:description" content="Tutorials on HTML, CSS, and JavaScript.">
<meta property="og:image"       content="https://example.com/og.png">
<meta property="og:image:width" content="1200">
<meta property="og:image:height" content="630">
<meta property="og:image:alt"   content="Example site logo and tagline">
<meta name="twitter:card"       content="summary_large_image">
```

---

# 13. Canonical Links

## 13.1 The Problem: Duplicate Content

The **same content** can be reachable via **multiple URLs**:

- `https://example.com/page`
- `https://example.com/page/`
- `https://example.com/page?utm_source=twitter`
- `http://example.com/page`
- `https://www.example.com/page`

Search engines may treat these as **different pages** — diluting ranking signals.

## 13.2 The `rel="canonical"` Link

Placed in `<head>`:

```html
<link rel="canonical" href="https://example.com/page">
```

Tells search engines: **"This is the preferred (canonical) URL for this content."**

- Should be **absolute URL**.
- Should be the **https** version, **without query strings** (unless the query is part of the canonical content).
- Should point to **itself** on the primary version of the page.

## 13.3 Why Use Canonical Links

- Consolidate ranking signals.
- Avoid duplicate-content penalties.
- Ensure the right URL appears in search results.
- Handle:
  - Trailing slash variants.
  - `www` vs non-`www`.
  - `http` vs `https`.
  - Tracking parameters (UTM).
  - **Printer-friendly** or **AMP** versions.
  - Paginated pages (`?page=2` can self-canonicalize).
  - Syndicated content.

## 13.4 Canonical vs. Redirect

- If two URLs are duplicates **and one is definitely wrong**, use a **301 redirect** (permanent, server-side) — stronger signal.
- If both URLs should remain accessible (e.g., tracking params), use **canonical**.

## 13.5 Related: Pagination with `rel="next"` / `rel="prev"`

```html
<link rel="next" href="https://example.com/page/3">
<link rel="prev" href="https://example.com/page/1">
```

> Google deprecated `next`/`prev` as indexing signals in 2019, but they remain useful for other crawlers and for browsing.

## 13.6 Common Mistakes

- Pointing canonical to a **different** page with different content.
- Using a **relative** URL.
- Multiple conflicting canonicals.
- Canonical to a **404** or **noindex** URL.

## 13.7 Redirect vs. `noindex` vs. Canonical

| Tool | Best for |
| ------ | ---------- |
| **301 redirect** | Old URL **should never** be indexed; permanent move |
| **`rel="canonical"`** | Content exists at multiple URLs; you want one indexed |
| **`noindex`** | Page should **not** be indexed at all |

---

# 14. Base URL

## 14.1 The `<base>` Element

Placed inside `<head>`, the `<base>` element sets a **default URL** (and optionally a default target) for all relative URLs in the document:

```html
<head>
  <base href="https://example.com/shop/" target="_blank">
</head>
```

- Now `<a href="products.html">` resolves to `https://example.com/shop/products.html`.
- `target="_blank"` becomes the default for all links without an explicit target.

## 14.2 The `href` Attribute

Sets the base URL that relative URLs are resolved against:

```html
<base href="https://cdn.example.com/assets/">
```

- All relative URLs in the page are resolved against this.
- Images, links, scripts, stylesheets — all affected.

## 14.3 The `target` Attribute

Sets the **default `target`** for all links on the page:

```html
<base target="_self">
```

- Saves you from writing `target="_blank"` on every link (or forces `_self` even if something else is set).

## 14.4 Rules & Constraints

- **Only one `<base>` per page.**
- Must be inside `<head>` and appear **before** any element that contains a relative URL.
- `<base>` has **no closing tag** (empty element).
- It affects **all** relative URLs — links, images, CSS files, scripts, forms — not just `<a>`.

## 14.5 When to Use `<base>`

Good use cases:

- **Single-page sites / apps** whose pages share a common asset prefix.
- Documents generated from another location (e.g., PDFs saved as HTML) where assets need a common origin.
- A template where every page links to the same CDN.

Risks / cautions:

- **Global effect** — a single `<base>` can break relative links on a complex page.
- **Fragments alone** (`href="#section"`) still work, but a `<base>` changes how other relative URLs resolve.
- Historically exploited in **HTML injection** attacks (an injected `<base>` could redirect all links to a malicious site). Use CSP + sanitization.
- **`document.baseURI`** in JavaScript reflects the resolved base.

## 14.6 Example

```html
<head>
  <base href="https://example.com/app/">
  <link rel="stylesheet" href="css/main.css"> <!-- resolves to https://example.com/app/css/main.css -->
</head>
<body>
  <img src="images/logo.png">                  <!-- https://example.com/app/images/logo.png -->
  <a href="about.html">About</a>               <!-- https://example.com/app/about.html -->
  <a href="/root.html">Root</a>                <!-- https://example.com/root.html -->
  <a href="https://other.com">Other</a>        <!-- absolute — unaffected -->
</body>
```

> **Best practice:** Avoid `<base>` unless you truly need it. Most modern projects manage paths with bundlers, environment variables, and explicit URLs.

---

# 15. Putting It All Together: A "Complete" `<head>` Example

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">

  <!-- Titles & descriptions -->
  <title>My Site – Learn Web Development</title>
  <meta name="description" content="Tutorials on HTML, CSS, and JavaScript.">

  <!-- Canonical -->
  <link rel="canonical" href="https://example.com/">

  <!-- Open Graph -->
  <meta property="og:type"        content="website">
  <meta property="og:url"         content="https://example.com/">
  <meta property="og:title"       content="My Site – Learn Web Development">
  <meta property="og:description" content="Tutorials on HTML, CSS, and JavaScript.">
  <meta property="og:image"       content="https://example.com/og.png">
  <meta property="og:image:width" content="1200">
  <meta property="og:image:height" content="630">

  <!-- Twitter Card -->
  <meta name="twitter:card"        content="summary_large_image">
  <meta name="twitter:title"       content="My Site – Learn Web Development">
  <meta name="twitter:description" content="Tutorials on HTML, CSS, and JavaScript.">
  <meta name="twitter:image"       content="https://example.com/og.png">

  <!-- Performance hints -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preload" href="/fonts/main.woff2" as="font" type="font/woff2" crossorigin>

  <!-- Styles -->
  <link rel="stylesheet" href="/css/main.css">
</head>
<body>
  <nav aria-label="Main">
    <ul>
      <li><a href="/" class="current">Home</a></li>
      <li><a href="/about.html">About</a></li>
      <li><a href="/contact.html">Contact</a></li>
    </ul>
  </nav>

  <main id="main">
    <h1 id="top">Welcome</h1>
    <p>
      See our <a href="/products.html#reviews">reviews</a>, or
      <a href="report.pdf" download>download the report</a>.
    </p>
    <p>
      <a href="mailto:hello@example.com?subject=Hi">Email us</a> or
      <a href="tel:+15555550123">call us</a>.
    </p>
    <p><a href="#top">Back to top</a></p>
  </main>
</body>
</html>
```

---

# 16. Quick Reference Cheat Sheet

| Topic | Key Tag / Attribute |
| ------- | ---------------------- |
| Hyperlink | `<a href="...">…</a>` |
| Absolute URL | `https://example.com/page.html` |
| Relative URL (same folder) | `page.html` |
| Relative URL (child) | `folder/page.html` |
| Relative URL (parent) | `../page.html` |
| Open in new tab | `target="_blank"` (+ `rel="noopener"`) |
| External site hint | `rel="external"` |
| SEO no-follow | `rel="nofollow"` |
| Anchor to same page | `href="#id"` |
| Anchor to other page | `href="page.html#id"` |
| Download file | `download` (optionally `download="name.ext"`) |
| Email link | `mailto:user@example.com` |
| Phone link | `tel:+1...` |
| SMS link | `sms:+1...` |
| Navigation | `<nav aria-label="Main">…</nav>` |
| Unordered list | `<ul><li>…</li></ul>` |
| Ordered list | `<ol><li>…</li></ol>` |
| Description list | `<dl><dt>term</dt><dd>def</dd></dl>` |
| Open Graph | `<meta property="og:…">` |
| Twitter Card | `<meta name="twitter:…">` |
| Canonical | `<link rel="canonical" href="…">` |
| Base URL | `<base href="…" target="…">` |
| Preconnect | `<link rel="preconnect" href="…">` |
| Preload | `<link rel="preload" href="…" as="…">` |
| Prefetch | `<link rel="prefetch" href="…">` |

---

# 17. Common Pitfalls to Remember

1. **`target="_blank"` without `rel="noopener"`** → reverse tabnabbing vulnerability (older browsers).
2. **Relative URL wrong direction** — `../` goes **up**, not down.
3. **Same anchor `id` used twice** → invalid; browser picks first.
4. **`download` on cross-origin link** → filename hint may be ignored.
5. **`og:image` relative URL** → many platforms fail to load it.
6. **Missing `<base>` before relative links** → base must come first in `<head>`.
7. **Canonical pointing to a different page** — must be the **preferred version of the same content**.
8. **Multiple `<base>` elements** — only the first counts.
9. **Relying on `javascript:` URIs** — breaks CSP and accessibility.
10. **Link text "click here"** — bad for SEO and screen readers.

---

That covers all the requested topics with both foundational explanations and modern best-practice details. Let me know if you'd like deeper dives into any specific area — for example, handling link states in CSS, building accessible nav patterns, or server-side redirect strategy for SEO.
