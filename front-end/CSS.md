## Cascading

The order that stylesheets are used. These stylesheets can be grouped into three main categories:
1.  ﻿﻿﻿User Agent Stylesheets: Contain browser defaults for styles, these get the lowest level of precedence
2.  ﻿﻿﻿User Stylesheets: Contain user preferences saved in the browser, which override user agent stylesheets
3.  ﻿﻿﻿Author Stylesheets: Contain the CSS code we write, these get the highest level of precedence (assuming important has not been used)

## Selectors

- Type selector: h1
- Class selector: .foo
- ID selector: \#bar
- Attribute selector:
	- \[type="submit"\]: Selects all elements with a specific HTML attribute set to a specific value
	- \[type\]: Selects all elements with the type attribute set, regardless of the value
	- \[href^=foobar.com\]: Selects all elements with a href attribute value that starts with "foobar.com"
	- \[href$=foobar.com\]: Selects all elements with a href attribute value that ends with "foobar.com"
	- \[href*=foobar.com\]: Selects all elements with a href attribute value that has "foobar.com" at any location
- Combinator:
	- footer p {}: Descendant combinator: Selects all paragraphs inside the footer.
	- footer > p {}: Child combinator: Selects all paragraphs that are a direct child of the footer
	- h2 ~ p {}: Selects all paragraphs that are siblings of a h2
	- h2 + p {}: Selects all paragraphs that are adjacent siblings of a h2

### Pseudo-Classes
Select elements based on theirs current state. These start with ":".
- a:link
- a:visited
- input:focus
- input:invalid
- input:invalid:not(:focus)
- p:first-of-type, :last-of-type (first of a set of siblings)
- p:nth-of-type(1), :nth-of-type(odd), :nth-of-type(even), :nth-of-type(2n -1)
- p:first-child, :last-child, :nth-child()

### Pseudo-Elements
Selects portions of elements
- p::first-letter, ::first-line
- p::before, ::after