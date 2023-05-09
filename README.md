# Utility_tools_notes 
This is a repo to save my notes on some utility tools

Now the notes include `Shell`, `Git`, `Markdown`

- [Utility\_tools\_notes](#utility_tools_notes)
  - [Tutorial and Docs](#tutorial-and-docs)
  - [Tools website](#tools-website)
  - [Extensions on VScode](#extensions-on-vscode)
  - [Shell](#shell)
  - [Git](#git)
  - [Markdown](#markdown)
    - [Head/Title](#headtitle)
    - [Line wrap](#line-wrap)
    - [Space](#space)
    - [Quote](#quote)
    - [List](#list)
    - [Segment line](#segment-line)
    - [Code Block](#code-block)
    - [Font](#font)
    - [Insert image](#insert-image)
    - [Insert URL](#insert-url)
    - [Table](#table)
    - [footnote](#footnote)


## Tutorial and Docs
[missing-semester-hp](https://missing.csail.mit.edu/)<br>
[missing-semester-notes](https://github.com/piaoliangkb/missing-semester-2020)</br>
[markdown-official-docs](https://markdown.com.cn/)</br>
[markdown-tutorial](https://www.markdowntutorial.com/)</br>

## Tools website
[tablesGenerator](https://www.tablesgenerator.com/)
+ create table in LaTeX/HTML/Markdown


## Extensions on VScode
Github Copilot<br>
Markdown all in one<br>


## Shell


## Git

## Markdown
cmd/ctrl + shift + p and input "markdown all in one: create tables of content"<p>
"markdown all in one: update tables of content"

### Head/Title
    # header1
    ## header2
    ### header3
    #### header4
    ##### header5
    ###### header6
at most 6 levels


### Line wrap
    para1<p>
    para2

    para1<br> #line wrap in paragraph
    para2
para1<p>
para2

para1<br>
para2 
### Space
    text1 &nbsp; or &emsp; text2

text1 &nbsp; or &emsp; text2
### Quote
    > ###Quote
    > >
    >
    > back to first layer
> Quote
> >more detail

### List
    + - * and space
    if embedding, indent is necessary

    number + . + content is ordered list
- node1
  - node2

1. node3
2. node4
### Segment line
    ---
    #enough '-'
---

### Code Block
    '''language name
    content
    '''
```python
import torch as tf
```
### Font
    *italic*
    **bold*
    ***italic bold***
    `inline code`</br>
    ~~delete line~~</br>
    <u>underline</u>
*italic*</br>
**bold*</br>
***italic bold***</br>
`inline code`</br>
~~delete line~~</br>
 <u>underline</u>

if you need to use tag inline, don't forget add / left.

### Insert image
    ![img_desc](image URL)
    
    <img src="image.png" width="100" height="100" />
 commonMarkdown can not adjust the size of image, at this time we need HTML.

### Insert URL
    [text_desc](URL)

    <URL>

[This repo](https://github.com/Yomikoooo/utility_tools_notes)

https://github.com/Yomikoooo/utility_tools_notes

### Table
    |first|first|first|
    |:--|:--:|--:|
    |left|center|right|
    |ML|DL|NN|
|first|first|first|
|:--|:--:|--:|
|left aligned|center|right aligned|
|ML|DL|NN|

### footnote
    [^note]: note content
    [^1]: footnote content
    footnote[^1] and note[^note]

[^note]: note content</br>
[^1]: footnote content</br>
footnote[^1] and note[^note]