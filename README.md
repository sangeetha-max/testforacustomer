# Beamer `iframe` opaque background bug reproduction

See documentation on the `color-scheme` meta attribute here:
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta/name#color-scheme

Beamer needs to advertise that its `iframe` for announcements supports
`color-scheme: dark;`, otherwise browsers will force a white/opaque background
for the `iframe` box and will not respect the `background: transparent;` CSS
rule. To reproduce this bug, the parent page needs to have `color-scheme:
dark;` in its rules.

To fix this bug, Beamer needs to add this meta tag to their `iframe`:

```html
<meta name="color-scheme" content="dark light" />
```

See a screenshot of the bug in action here:

<img src="./screenshot.png" />
