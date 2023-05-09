# Utility_tools_notes 
This is a repo to save my notes on some utility tools

Now the notes include `Shell`, `Git`, `Markdown`

- [Utility\_tools\_notes](#utility_tools_notes)
  - [Tutorial and Docs](#tutorial-and-docs)
  - [Tools website](#tools-website)
  - [Extensions on VScode](#extensions-on-vscode)
  - [Shell](#shell)
    - [Shell Basics](#shell-basics)
  - [Git](#git)
    - [Git Basics](#git-basics)
    - [Initialization and Configuration](#initialization-and-configuration)
    - [Storage](#storage)
    - [Ignore](#ignore)
    - [Commit](#commit)
    - [Commit Angular](#commit-angular)
    - [Version control](#version-control)
    - [Branch](#branch)
    - [Merge](#merge)
    - [Amend](#amend)
    - [Remote](#remote)
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
    - [Footnote](#footnote)
    - [Task lists(ChatBox)](#task-listschatbox)
    - [Math Formula](#math-formula)
    - [Flow Chart/Sequence diagram/Gantt Chart](#flow-chartsequence-diagramgantt-chart)


## Tutorial and Docs
[missing-semester-hp](https://missing.csail.mit.edu/)<br>
[missing-semester-notes](https://github.com/piaoliangkb/missing-semester-2020)</br>
[markdown-official-docs](https://markdown.com.cn/)</br>
[markdown-tutorial](https://www.markdowntutorial.com/)</br>

## Tools website
[tablesGenerator](https://www.tablesgenerator.com/)
+ create table in LaTeX/HTML/Markdown

[mermaid.js](https://mermaid.js.org/intro/)
+ create diagram/chart in Markdown

[hexo](https://hexo.io/)
+ build your own blog.

[overleaf](https://www.overleaf.com)
+ LaTeX online editor
+ It has some templates
+ recommend: elegantbook
## Extensions on VScode
Github Copilot<br>
Markdown all in one<br>
Markdown Preview Enhance<br>

## Shell
### Shell Basics
```bash
#shell

$ date
$ echo hello
$ echo "hello world"
$ echo hello\ world
$ echo $PATH #environment arguments
$ pwd ##current absolute path
$ cd  ##go to
$ cd .. #go to parent directory
#cd is used to switch directory，. is current directory，.. is parent
$ ls #list all files in current directory
$ ls -a #list all
$ ls -l #list detail
$ mv #rename or move
$ cp #copy
$ cp -r #recursively copy
$ rm #remove
$ rmdir #remove directory
$ mkdir #make a directory
$ man #manual #example man ls #or press Q in keyboard
ctrl+l #or input clear #clear the board
$ find path -name pattern #search
```
```bash
$ whoami #current user
$ ps #view the process
$ clear #clear the shell
$ kill #kill the process
$ diff #compare the files
$ ln
$ curl --head --silent google.com
HTTP/1.1 301 Moved Permanently
Location: http://www.google.com/
Content-Type: text/html; charset=UTF-8
Date: Fri, 10 Mar 2023 13:43:43 GMT
Expires: Sun, 09 Apr 2023 13:43:43 GMT
Cache-Control: public, max-age=2592000
Server: gws
Content-Length: 219
X-XSS-Protection: 0
X-Frame-Options: SAMEORIGIN

$ curl --head --silent google.com | grep Location
Location: http://www.google.com/

$ whereis #find the command
$ which #find the command

$ wget <link> #download from internet

$ echo hello > hello.txt #put 'hello' into hello.txt
$ cat <filename> #print
$ cat < <filename> #another version
$ cat hello.txt
$ cat hello.txt > hello2.txt #single > will overwrite
hello
$ cat hello.txt >> hello2.txt #append
hello
hello

$ tail -n #output last n lines
$ tail -n+<N+1> #output n lines from N+1 line
$ head -n #front n lines

$ sudo echo 3 > brightness
open: Permission denied
#sudo is super user do, it gives the root authority
$ echo 3 | sudo tee brightness
3
#tee will write input to the file and print in stdout
#tee equals >
#tee -a equals >>

$ diff <file1> <file2>  > <file3>#将diff的输出写入文件
./a.out < <file> #file as input of this program

#pipe '|' #output from left program as input in right program
$<command> | tail -n lines
$<command> | less #output by pages
$<command> | grep <pattern>
#often combined with cut/sort/uniq/awk
$ cat <filename> | cut -d '' -f 1 |sort | uniq -c |tail -n 1

```
```bash
$ echo $ <var>
$ echo $PATH

$ env #check current environment variable
$ export <var> =value #set environment variable
$ unset <var> #delete environment variable

#check shell configuration
$ ~/.bashrc
$ ~/.zshrc
```

## Git
### Git Basics

file manage, commit, branch, merge
tag, version, Git commit message

common workflow to update to github
```bash
#if need to get repo from github
$ git clone

$ git checkout <workspace>
#modify your file
$ git merge <branch>
$ git add .
$ git commit -m <message>
$ git push
#if need to check the file is added
$ git status
```
if first time to connect remote repo:
```
$ git push -u origin main
```

### Initialization and Configuration
```bash
$ git init <folder name> #create a new repo
$ git config --global user.name <>
$ git config --global user.email <> #global config
#if not type global, for some version.
```
### Storage
```bash
#file storage
$ git add <file/folder>
$ git add . #add all your modification
$ git status #check the status
$ git rm #remove
$ git rm --cached #cancel this remove
$ git mv #rename
```
### Ignore
```bash
#file ignore
# .gitignore is a config file
# filename ignore the file
# dirname/ ignore the directory
# *.log ignore all the files with the extension '.log'
$ vim .gitignore
$ git check-ignore -v <filename>
```
### Commit
```bash
#commit the modification
$ git commit #get into the 
$ git commit -m <message>
$ git log #check the commit history
$ git log --oneline #show as one line
$ git log --graph #show the branch
$ git log --oneline --graph #often combined
$ git log -p #detail
$ git log -stat #status
#the 40 alphabets is hash code
$ git show <id> #show the id
$ git checkout <id> #check previous version
```

### Commit Angular
```bash
$ git add .
$ git commit

#add below at the head of file
<type>([scope]): <summary>
[body]
[footer]
```
type: (fix/feat/docs/refactor/perf/test/ci/…)
BREAKING CHANGE/ DEPRECATED
scope<br>
summary<br>
body<br>
footer: fix some issues

### Version control
```bash
$ git tag <tag id> #git tag v0.0.1
$ git tag -a tag -m <message> <id>
$ git tag #check the tag
$ git show v0.0.1

#v主版本号.次版本号.修订号[-预发布版本号]
#修订号：兼容修改，修正不正确的行为
#次版本号：添加新功能，但是保持兼容
#主版本号：不兼容的API修改，0时为开发阶段
#预发布版本号 alpha/beta/rc.1/rc.2/..

```

### Branch
```bash
#create branch
$ git branch <name> #current HEAD
$ git branch <name> <id> #some version

#check the branch
$ git branch
$ git show-branch

#switch the branch
$ git checkout <name>
$ git checkout -b <name> #create and switch

#differentiate
$ git diff <branch1> <branch2>
$ git diff branch #compare the workspace and branch
$ git diff #compare the workspace and storage

#locate the commit
$ git show master~
$ git show master^
#这两个表示第一个父提交
#~2表示第一个父提交的第一个父提交
#^2表示第二个父提交
```
### Merge
```bash
$ git merge <branch1> <branch2> #merge some branch to current branch
```
### Amend
```bash
$ git revert <id> #cancel some sommit
$ git commit --amend #amend the latest commit
$ git reset #go back
$ git rebase -i <id> #amend history of a commit
#pick reserve
#edit reserve and edit
#squash merge and commit
#drop delete the line
```
### Remote
```bash

$ git clone #clone the remote repo to local
$ git remote #manage
$ git push #put the local commit to remote repo
$ git pull #get the remote commit 
```

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

### Footnote
    [^fs]: Fourier Series
    [^ft]: Fourier transform

    footnote[^fs] and note[^ft]


[^fs]: Fourier Series
[^ft]: Fourier transform

text1[^fs] and text2[^ft]

the footnote shows at the end of the page. 

### Task lists(ChatBox)
    - [ ] task to do
       - [ ] subtask
    - [x] completed

- [ ] task to do
  - [ ] subtask
- [x] completed

### Math Formula
markdown cannot do the operation, this is for LaTeX grammar

    $inline math$

    $$
    block math
    $$

$H(X)=-\sum p_ilogp_i$

$$
H(X)=-\sum p_ilogp_i
$$

### Flow Chart/Sequence diagram/Gantt Chart

common extension but not markdown grammer<p>

[mermaid.js](https://mermaid.js.org/intro/) is useful to create these charts
