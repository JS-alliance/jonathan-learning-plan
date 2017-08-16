


##### [Babelmark 2](https://johnmacfarlane.net/babelmark2/)
##### [CSS Tricks: Choosing the Right Markdown Parser](https://css-tricks.com/choosing-right-markdown-parser/)
##### [GitHub: Mastering Markdown](https://guides.github.com/features/mastering-markdown/)
##### [Treehouse: Mastering Markdown](https://teamtreehouse.com/library/github-basics/working-by-yourself/mastering-markdown)
##### [CommonMark](http://commonmark.org/)

https://guides.github.com/features/mastering-markdown

https://guides.github.com/pdfs/markdown-cheatsheet-online.pdf

http://www.emoji-cheat-sheet.com/




# Markdown Basics

## Headlines, Paragraphs, and Basic Formatting

### Headlines

Type a single hash (AKA pound symbol) and a space to create the largest or first-level heading. A second-level heading uses two hashes next to each other followed by a space and text. The rest of the headline levels just add another hash.

#### Heading Level 4
##### Heading Level 5
###### Heading Level 6

### Paragraphs and Line Breaks

We create paragraphs by typing the way we would in any other program. Just hit return twice to start another paragraph.

Where you see empty space between blocks of text in your Markdown document, you will see empty space separating those blocks of text in your formatted HTML document.

You don’t always want that space that appears between one line of text and another: for example, lines of poetry or song lyrics don't have spaces between them. To add just a line break without a space, type two spaces at the end of a line, then press return once.

I love you without knowing how, or when, or
from where
I love you directly without problems or pride:
I love you like this because I don't know any
other way to love    

Neruda, Pablo. "Sonnet 17" The Poetry of Pablo Neruda, edited by Ilan Stavans, translated by Mark Eisner, Farrar, Straus and Giroux, 2005, p. 514.

### Emphasis and Bolding

#### Italics

Emphasis can be added with either the asterisk or the underscore characters.

This *works*, and this _works_ too

#### Bolding

Bolding is easy too. Just add an extra asterisk or underscore.

This **works**, and this __works__ too

#### Bolding and Emphasis Together

You can even bold and italicize text like ***this*** or ___this___

### Blockquotes

A blockquote sets text apart from the rest of the document. It indicates that the text is quoted from another source.

You format a blockquote using the greater than symbol. If you want a blockquote to span multiple paragraphs, add the greater than symbol to the empty space between paragraphs too.

> Markdown is intended to be as easy-to-read and easy-to-write as is feasible.
>
> Readability, however, is emphasized above all else. A Markdown-formatted document should be publishable as-is, as plain text, without looking like it’s been marked up with tags or formatting instructions. — [John Gruber](https://daringfireball.net/projects/markdown/ "The Creator of Markdown")

### Horizontal Rule

OK, that’s a good start. We can separate this from our next section with a horizontal rule, which is just a line used to separate sections of a document.

You can use three or more underscores, asterisks, or hyphens. I prefer hyphens.

___

***

---

## Lists

You can write both numbered and bulleted lists with Markdown.

### Numbered Lists

You create numbered lists like you do in other writing programs. Type the number, a period, a space, and the item label.

1. Item One
2. Item Two

To nest an item, indent it with a tab or at least two spaces beneath the item above it.

1. Item One
  1. Nested Level Two
  2. Nested Level Two
      1. Nested Level Three
      2. Nested Level Three

#### Bulleted Lists

Bulleted lists work like numbered lists, but you use the asterisk character, a space, and no period.

* Item One
* Item Two

You can nest bulleted items too. We just indent our item below another item like we did with our numbered list.

* Item One
  * Nested Item One
  * Nested Item Two

##### Asterisk Gotchas

Because the asterisk is used for bolding, italicizing, and creating bulleted lists, it's easy to make mistakes. Check your spacing, and use a preview to ensure you are formatting text the way you intend.

*Italicized Item*  
*Not Formatted
* Bulleted Item

What if you do want a bulleted item that is bold and italicized? Type an asterisk and a space. This will create the bulleted item. Then use two asterisks for the bolding and a third for the italicizing on both sides of the text.

* ***Bold Italicized Bulleted Item***

#### Mixed Lists

You can mix the two list styles too. Just use the numbers or asterisks where you want them.

1. Item One
  * Nested Item
  * Nested Item
2. Item Two
  * Nested Item
  * Nested Item
    1. Deep Nested Item One
    2. Deep Nested Item Two
      * Super Deep Nested Item
      * Super Deep Nested Item

---

## Code

We format code using the backtick character. The backtick is on the same key as the tilde on a U.S. English keyboard, which is usually to the left of the number 1 and above the tab key.

You can use a single backtick to create inline code. For example, you may type something like this:

To install the latest version of NPM, you can type,  `npm install npm@latest -g`

For multiple lines of code, you'll usually create a code block. Instead of one backtick, use three backticks above and below the code block.

```JavaScript
let exampleFunction = () => {
  let foo = 'foo';
  let bar = 'bar';

  return foo + bar;
}
