---
layout: post
title: Markdown Cheatsheet
---

Just another markdown syntax reference.

## Paragraphs and Text Formatting
#### Syntax
```
This is a paragraph.

**Lorem ipsum** dolor sit amet, an sit voluptua luptatum, _at mea platonem adversarium_. Te laudem cetero nec, ea ~~timeam evertitur~~ nec.
```
#### Output
This is a paragraph.

**Lorem ipsum** dolor sit amet, an sit voluptua luptatum, _at mea platonem adversarium_. Te laudem cetero nec, ea ~~timeam evertitur~~ nec.

## Headings
#### Syntax
```
# Heading 1
## Heading 2
### Heading 3
#### Heading 4
```
#### Output
# Heading 1
## Heading 2
### Heading 3
#### Heading 4

## Links and Link Placeholders
#### Syntax
```
[This is a link](https://kennyalmendral.github.io/)

[This is a link with a title attribute](https://kennyalmendral.github.io/ "Link Title")

[This link will open in a new tab](https://kennyalmendral.github.io/ "Link Title"){:target="blank"}

[Lorem ipsum][google_url] dolor sit amet, an sit voluptua luptatum, at [mea platonem adversarium][google_url]. Te laudem cetero nec ea [timeam evertitur][google_url] nec.

[google_url]: https://google.com
```
#### Output
[This is a link](http://sample.com)

[This is a link with a title attribute](https://kennyalmendral.github.io/ "Link Title")

[This link will open in a new tab](https://kennyalmendral.github.io/ "Link Title"){:target="blank"}

[Lorem ipsum][google_url] dolor sit amet, an sit voluptua luptatum, at [mea platonem adversarium][google_url]. Te laudem cetero nec ea [timeam evertitur][google_url] nec.

[google_url]: https://google.com

## Images and Image Placeholders
#### Syntax
```
![Image](https://picsum.photos/180/?random)

![Image](https://picsum.photos/180/?random "Image with title attribute")

[<img src="https://picsum.photos/80">](https://picsum.photos/200 "This will link to the larger image")

![Image 1][image_url]

![Image 2][image_url]

[image_url]: https://picsum.photos/180
```
#### Output
![Image](https://picsum.photos/180/?random)

![Image](https://picsum.photos/180/?random "Image with title attribute")

[<img src="https://picsum.photos/80">](https://picsum.photos/200 "This will link to the larger image")

![Image 1][image_url]

![Image 2][image_url]

[image_url]: https://picsum.photos/180

## Lists
#### Syntax
```
- Item 1
	- Item 1a
	- Item 1b
- Item 2
	- Item 2a

		This is an inline paragraph

		![Image](https://picsum.photos/100/?random)
- Item 3
	- Item 3a
	- Item 3b
	- Item 3c

1. Step 1
2. Step 2
	- Step 2a
	- Step 2b
3. Step 3
```

#### Output
- Item 1
	- Item 1a
	- Item 1b
- Item 2
	- Item 2a

		This is an inline paragraph

		![Image](https://picsum.photos/100/?random)
- Item 3
	- Item 3a
	- Item 3b
	- Item 3c

1. Step 1
2. Step 2
	- Step 2a
	- Step 2b
3. Step 3

## Line Breaks, Horizontal Rules and Blockquotes
#### Syntax
```
The quick brown<br>
fox jumps over<br>
the lazy dog

- - -

> Lorem ipsum dolor sit amet, an sit voluptua luptatum, at mea platonem adversarium. Te laudem cetero nec, ea timeam evertitur nec.
>
> **John Doe**
```

#### Output
The quick brown<br>
fox jumps over<br>
the lazy dog

- - -

> Lorem ipsum dolor sit amet, an sit voluptua luptatum, at mea platonem adversarium. Te laudem cetero nec, ea timeam evertitur nec.
>
> **John Doe**

## Code and Code Blocks
To specifiy a single line of code, enclose it with an opening and closing backtick, like so:

`$greeting = 'Hello';`

To specifiy lines of code, enclose it with three opening and closing backticks, like so:

```
$greeting = 'Hello';
echo "$greeting World!";
```

To specifiy the language, add the language name (all lowercase, i.e., `php`, `javascript`, etc.) after the opening three backticks, for example:

**PHP**

```php
$greeting = 'Hello';
echo "$greeting World!";
```

**JavaScript**

```javascript
var greeting = 'Hello';
console.log(greeting + 'World!');
```

## Table
#### Syntax
```
Name | Gender | Age | Savings
:---|:---|:---:|---:
John Doe | Male | 30 | $2000.00
Jane Doe | Female | 26 | $1000.00
```

#### Output

Name | Gender | Age | Savings
:---|:---|:---:|---:
John Doe | Male | 30 | $2000.00
Jane Doe | Female | 26 | $1000.00

## Checkboxes
#### Syntax
```
* [ ] Item 1
* [x] Item 2
* [ ] Item 3
```

#### Output
* [ ] Item 1
* [x] Item 2
* [ ] Item 3

---
