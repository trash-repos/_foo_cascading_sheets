#CS
NOTE: Work in progress!

##Cascading Sheets

### Section 1 - Intro

Comments in CS have to begin with `/*` and end with `*/`, like this:
```css
/* This is a comment */
```
Comments are never parsed - they are just for you.

### Section 2 - Selectors
NOTE: Unlike CSS, in CDS space has no special meaning, descendant selector is now `>>`.
All names (tag names, namespaces, classes...) has to be in range `[^ .#:>!~*,]`.

#### Element selectors
These can be combined just by writing them consecutively (with or without spaces), AND rule is applied on them.

**Tag name selector**  
Pattern: `E`  
Meaning: An element of any namespace with tag name "E". Special tag name `*` means an element of any tag name.  

**Namespace selector**  
Pattern: `ns:E`  
Meaning: _Always followed by an Tag name selector._ An element with tag name "E" and namespace "ns". Special namespace `*` means an element that has namespace, empty namespace (like `:E`) means an element that hasn't namespace.  

**Class name selector**  
Pattern: `.bold`  
Meaning: An element that has class "bold". Classes are listed in the element's `class` attribute, separated by out-of-range characters (see heading of Section 2).  

**ID selector**  
Pattern: `#menu`  
Meaning: An element whose attribute `id` is equal to "menu".  
NOTE: Because ID is an unique identificator, there can be only one element with given id in the whole document.  

**Has attribute selector**  
Pattern: `[foo]`  
Meaning: An element that has attribute "foo", whatever value of the attribute.  

**Aproximate attribute equality selector**  
Pattern: `[foo=bar]` or `[foo="bar"]`  
Meaning: An element that has attribute "foo" equal to any case-permutation of "bar".  
NOTE: Any value that contains spaces has to be quoted.  
NOTE: This selector is not equal to CSS `[foo=bar]` selector, do not confuse!  

**Exact attribute equality selector**  
Pattern: `[foo==bar]` or `[foo=="bar"]`  
Meaning: An element that has attribute "foo" exactly equal to "bar".  


### Section 3 - At Rules
In CDS there are some special rules beginning with the "@" char.  
Here's the list of CDS's at rules:

#### @import
At import rule lets you load an external CSS or CDS file.
```css
/* Syntax */
@import url("path/to/a/file.css");
```

#### @font-face
At font face rule is here to attach special fonts to the document. Detailed specification can be found on <a href="http://www.w3.org/TR/css3-fonts/">W3C website</a>
```css
/* Syntax */
@font-face {
 font-family: Gentium;
 src: url(http://example.com/fonts/Gentium.ttf);
}
```

#### @media
At media rule is used to define responsive styles or print versions. Detailed spec <a href="http://www.w3.org/TR/CSS2/media.html">here</a>.
```css
@media print {
 font-family: "Courier New";
}
```
