-------------------------------

# How to Remove Content Using RegEx in Sigil

This guide assumes you've already added your HTML files into Sigil.

1. Double-click into first HTML file
2. Click top line of file
3. Click "Find & Replace"
4. Select "Regex" and "All HTML Files" at the bottom
5. Paste Regex line into "Find" field
6. Select options, if necessary
7. Click "Replace All"
8. Repeat Steps 5-7 for each desired operation

NOTE: Unless otherwise specified, the "Replace" field is always left blank

### Resources for RegEx

* Online RegEx reference and playground: https://regexr.com/
* Excellent text editor that supports RegEx: https://www.sublimetext.com/3

-------------------------------

# Expressions I've Figured Out So Far

### Remove Homepage line
DotAll = OFF | Wrap = ON

`<p class="ctr"><img.*</p>`


### Remove Nav
DotAll = OFF | Wrap = ON

`<p class="ctr f2">.*</p>`


### Remove Boilerplate
DotAll = ON | Wrap = ON

`<h4 class="ctr.*</span></h4>`


### Remove Footers A
DotAll = ON | Wrap = ON

`<p class="ctr"><a href="\.\.\/\.\.\/\.\.\/backmatter.*Statement<\/a><\/p>`


### Remove Footers B
DotAll = ON | Wrap = ON

`<p class="fine ctr c">.*Statement<\/a><\/p>`


### Remove License Links
DotAll = ON | Wrap = ON

`Commercial.*Use</a>\.</p>`


### Remove Translation Links
DotAll = OFF | Wrap = ON

`<span class="f3">\[<a .*\]</span>`


### Remove Inline Images
DotAll = OFF | Wrap = ON

`<p><img src="\..*</p>`


### Remove Other Text Links (MUST BE DONE LAST)
DotAll = OFF | Wrap = ON

Find:

`<a href="\.\.\/\.\.\/\.\.\/.*>(\w.*)<\/a>`

Replace:

`\1`


### Fix Most External Links
_(alternative to removal, doesn't work for all though)_
DotAll = OFF | Wrap = ON

Find:

`\.\.\/\.\.\/\.\.\/`

Replace:

`http://www.buddhadust.net/`
