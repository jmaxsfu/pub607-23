# Specificity in CSS

Complex CSS sheets (e.g., like you find in a Wordpress theme) can be challenging because they are often huge, complex messes of CSS, with more than one rule affecting the same piece of content.

The C in CSS stands for "cascading," which alludes to the structure of how stylesheet rules stack up. Earlier, more general rules will 'cascade' down and affect other elements below them, unless those lower elements are specified themselves, overriding the more general rule.

A good example is setting the basic typography for a whole page (or book) at the VERY top:

        body { font-family: Caslon; font-size: 12pt; }

Then, down below, you could override this specifically for, say, third-level headings:

        h3 { font-family: Avenir; font-size: 14pt; }

In general:
 
- a global stylesheet can be overridden by CSS rules written directly in the HTML file;

- CSS rules listed (and read) **first** can be overridden by those that are listed **later** (either further down in the file, or in a another file altogether)

- **general** selectors can be overridden by more **specific ones**:

  So, for example, here are some hypothetical selectors that might apply to the same elements, listed from most general to most specific:

	    p { color: blue;}

	    p.aParticularClass { color: blue; }

	    p#aUniqueID { color: blue; }

	    div p { color: blue; }

	    div > p { color: blue; }

	    div.someClass p { color: blue; }

	    div.someClass p.aParticularClass { color: blue; }

	    div#thisSpecificID > p#aUniqueID { color: blue; }

