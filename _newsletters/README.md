# Newsletter archive

Store each newsletter's final HTML source in this directory so git retains its
revision history. Use a date-first filename, for example:

```text
2026-09-03-rentree.html
```

GitHub Pages' default Jekyll build ignores directories whose names begin with an
underscore, so these HTML files are not published as website pages. They remain
visible in the public GitHub repository and must never contain secrets, private
subscriber data, or credentials.

Put images referenced by newsletters in `images/newsletters/`. Reference them
with an absolute public URL so email clients can load them, for example:

```html
<img src="https://www.negitachi.fr/images/newsletters/2026-09/rentree.jpg"
     alt="Les Negitachi sur scène">
```

Group assets by issue or month to prevent filename collisions. After deployment,
open every image URL in a private browser window before sending the newsletter.
