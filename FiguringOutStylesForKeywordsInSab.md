## A methodology for understanding \w keyword\w* styling for SAB

- [Readme](README.md)

### Introduction

I'd love to say I have documentation to help understand SAB syles, but I don't. So I have to try from what we know. I have written this as a training exercise for other tinkerers. The success is at the end.

When testing selectors I set **background-color: red** so I know when I have the correct selector. Selector is a CSS term. SAB styles are CSS. By default they are presented as Style Properties but can also be viewed as CSS. I will use the CSS form as it is more compact to write.

Currently keywords (like footnotes) have text decoration of an underline. Underline is a default way of signaling a link in HTML

### First experiment
- First try **span.w** since the keyword is marked up by `\k keyword\k\*` and is character styling not a paragraph.
  - That does not work.
  - Conclusion the keywords are not handled this way in the App.
  
### Second experiment
- Second look at the HTML output, how is that marked up. It may be the same.

  USFM: 
  ```
  \v 1 The book of the \w genealogy\w* of Jesus Christ,\f + Messiah (Hebrew) and Christ (Greek) both mean “Anointed One”\f* the \w son of David\w*, the son of Abraham.
  ```
  HTML: 
  ```html
  <span class="v">1</span><span class="vsp">&nbsp;</span>The book of the <span class="footnote selectable" id="G-0">genealogy</span> of Jesus Christ,<span class="footnote selectable" id="F-0"><sup>a</sup></span> the <span class="footnote selectable" id="G-2">son of David</span>, the son of Abraham.<span id="bookmarks1"></span>
  ```

  So we can see that the HTML uses two class names. So we can try our modifying **span.footnote**. In this case I add a Custom Style with the same selector.
  ```css
  span.footnote {
    font-weight: bold;
    background-color: red;
  }
  ```
  In the HTML we have some success.<br/>
  ![image|648x37](images/zD8YwYISeRG1yNuXDFNW6FN97k9.png) 
  Note the original styling has the color navy.

  In the App the story is different.
  ![image|485x105](images/tH6iAu9VJiJRjEzoz2vauH4UM3D.png) 
  Only the footnote has the red background.

  Trying **span.selectable** also made changes in the HTML but no difference in the App.

  I also tried **span.keyword** it too produced no result.

  So my conclusion is that keywords can't be selected in the styles.

### Third experiment

You can style all **a:link** to remove the underscore and and change the background color. But 
  that will affect all links. But we can conclude from that unlike the HTML the App keywords and footnotes are **a** hyperlinks not spans.

I tried **a:active** and it works, but does so only while it is being touched.

So maybe we should try **a:hover**  a **success**. But there is a catch. You can create a custom style with **div.class** or **span.class** but you can't create an **a:hover**.  It gets converted to **.a:hover** when you say OK. 

#### Workaround: 
- Close SAB.
- Open the .appdef file in a txt or XML editor. (Never in Word)
- Look for the miss named style
```xml
  <style name=".a:hover" type="character" category="custom">
    <style-decl property="background-color" value="TextHighlightColor" />
    <style-decl property="font-style" value="italic" />
    <style-decl property="font-weight" value="bold" />
  </style>
```
And correct the first line to:
```xml
<style name="a:hover" type="character" category="custom">
 ```
Outcome:
![image|690x474](images/aHqnilO8OI5umrakgbvjMUOawb9.png) 

The text change goes away after a  touch or two on the screen. I'd add the **text-decoration:none** attribute as well.

Just remember that this affects all links not just the ones you asked about. It also affects the footnote callers. I did not check what it did to the HTML output.