# Utility_tools_notes 
This is a repo to save my notes on some utility tools

Now the notes include `Shell`, `Git`, `Markdown`, `LaTeX`, `Docker`,`SSH`, `Makefile`
brief introduction:
+ Shell: a command-line interpreter (command line interface in terminal)
+ Git: a version control system (save code and other files in a repository in github)
+ Markdown: a markup language (write README.md and take notes)
+ LaTeX: a document preparation system (write paper and slides)
+ Docker: a containerization platform (build a virtual environment)
+ SSH: a secure shell protocol (connect to remote server)
+ Makefile: a build automation tool (build a project)

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
    - [Code Chunk](#code-chunk)
    - [Import](#import)
  - [LaTeX](#latex)
    - [Package](#package)
    - [Basic](#basic)
    - [Title](#title)
    - [Section](#section)
    - [Font](#font-1)
    - [Size](#size)
  - [Docker](#docker)
    - [Install](#install)
    - [Basic](#basic-1)
    - [Dockerfile](#dockerfile)
    - [Docker Compose](#docker-compose)
    - [Docker Hub](#docker-hub)
  - [SSH](#ssh)
    - [Install](#install-1)
    - [Basic](#basic-2)
    - [login without password and username](#login-without-password-and-username)
    - [Keep the program running after logout](#keep-the-program-running-after-logout)
  - [Cmake](#cmake)
    - [Install](#install-2)
    - [Basic](#basic-3)
    - [CMakeLists.txt](#cmakeliststxt)


## Tutorial and Docs
[missing-semester-hp](https://missing.csail.mit.edu/)<br>
[missing-semester-notes](https://github.com/piaoliangkb/missing-semester-2020)</br>
MIT course on shell, git, vim, debugging, security, etc.
[markdown-official-docs](https://markdown.com.cn/)</br>
[markdown-previewed-enhance](https://shd101wyy.github.io/markdown-preview-enhanced/#/)
+ (Recommend), it supports math, flowchart, plot, auto TOC, code chunk </br>

[LaTeX tutorial in overleaf](https://www.overleaf.com/learn)
- [beamer](https://www.overleaf.com/learn/latex/Beamer)

[Docker docs](https://docs.docker.com/)
[Docker -从入门到实践](https://yeasy.gitbook.io/docker_practice/)
[SSH基本用法](https://zhuanlan.zhihu.com/p/21999778)
## Tools website
[tablesGenerator](https://www.tablesgenerator.com/)
+ create table in LaTeX/HTML/Markdown

[mermaid.js](https://mermaid.js.org/intro/)
+ create diagram/chart in Markdown

[mkdocs](https://www.mkdocs.org/)
+ build your own website.

[reveal-md](https://github.com/webpro/reveal-md)
+ build your own slide.

[hexo](https://hexo.io/)
+ build your own blog.

[overleaf](https://www.overleaf.com)
+ LaTeX online editor
+ beamer editor
+ It has some templates
+ What I use: elegantbook(for book)

[mathcha.io](https://www.mathcha.io/)
+ create math formula in LaTeX quickly

[LaTeX cheatsheet](https://wch.github.io/latexsheet/)
[LaTeX mathmatical symbols](https://oeis.org/wiki/List_of_LaTeX_mathematical_symbols)


## Extensions on VScode
Github Copilot<br>
Markdown all in one<br>
Markdown Preview Enhance<br>
Remote - SSH<br>
Remote Explorer<br>

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

$ diff <file1> <file2>  > <file3> #write output of diff into file
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

```bash
# create a new repo on command line
echo "#filename" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin <link>
git push -u origin main
```
```bash
# push an existing repo from the command line
git remote add origin <link>
git branch -M main
git push -u origin main
```

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

#vMajor verision number.Minor version number.revised version number[-version to be released]
#revised：compatible，revise some incorrect behavior
#Minor version number：append some new functions and compatible
#Major version number：incompatible modification, usually breaking update
#to be released version alpha/beta/rc.1/rc.2/..

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
#the two lines means the first parent commit
#~2 means the first parent commit of the first parent commit
#^2 means the second parent commit
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
print('hello,world')
```
Code Chunk is also available

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

    text1[^fs] and text2[^ft]


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

### Code Chunk
you need to open the setting of MPE and enableScriptExecution

    ```language {cmd="path of interpreter"}
    content
    ```


[mermaid.js](https://mermaid.js.org/intro/) is useful to create these charts

### Import
    @import 'your file'

## LaTeX
latex code is also available in markdown
I recommend [overleaf](https://www.overleaf.com/) to write latex code
the tutorial is [here](https://www.overleaf.com/learn/latex/Learn_LaTeX_in_30_minutes)

and cheatsheet is [here](https://wch.github.io/latexsheet/)

[mathcha.io](https://www.mathcha.io/) is useful to create math formula

mathmatical symbols is [here](https://oeis.org/wiki/List_of_LaTeX_mathematical_symbols)
### Package
```latex
\usepackage{package name}

%common used packages
\usepackage{amsmath} %math
\usepackage{amssymb} %math
\usepackage{amsthm} 
\usepackage{mathrsfs}
\usepackage{mathtools}
\usepackage{bm}
\usepackage{graphicx} %figure
\usepackage{subfigure}
\usepackage{float} 
\usepackage{geometry} %page
\usepackage{fancyhdr}
```

### Basic
    \documentclass{article}
    \begin{document}
    Hello, world!
    \end{document}

### Title
    \title{title}
    \author{author}
    \date{date}
    \maketitle

### Section
    \section{section}
    \subsection{subsection}
    \subsubsection{subsubsection}
    \paragraph{paragraph}
    \subparagraph{subparagraph}

### Font
    \textbf{bold}
    \textit{italic}
    \underline{underline}
    \emph{emph}
    \texttt{typewriter}
    \textsf{sans serif}
    \textsc{small caps}
    \textsl{slanted}
    \textmd{medium}
    \textrm{roman}
    \textup{upright}
    \textnormal{normal}

### Size
    \tiny
    \scriptsize
    \footnotesize
    \small
    \normalsize
    \large
    \Large
    \LARGE
    \huge
    \Huge

## Docker
docker is a tool to create, deploy, and run applications by using containers.
### Install
manual install from [here](https://docs.docker.com/engine/install/ubuntu/)
```bash
$ curl https://get.docker.com | sh \
  && sudo systemctl --now enable docker
```
### Basic
```bash
$ docker --version #check version
$ docker ps #check running container
$ docker ps -a #check all container
$ docker images #check images
$ docker run hello-world #run hello-world
$ docker run -it ubuntu bash #run ubuntu, -it means interactive mode
$ docker run -d -p 80:80 docker/getting-started #run docker/getting-started, -d means run in background, -p means port mapping
$ docker stop container_id #stop container
$ docker rm container_id #remove container
$ docker rmi image_id #remove image
$ docker exec -it container_id bash #enter container
$ docker cp container_id:/path/to/file /path/to/file #copy file from container to host
$ docker cp /path/to/file container_id:/path/to/file #copy file from host to container
$ docker commit container_id image_name #commit container to image
$ docker login #login docker hub
$ docker push image_name #push image to docker hub
```
### Dockerfile
dockerfile is a text document that contains all the commands a user could call on the command line to assemble an image.
```dockerfile
FROM ubuntu:latest #base image
RUN apt-get update && apt-get install -y python3 python3-pip #install python3 and pip
COPY . /app #copy current directory to /app
WORKDIR /app #set working directory
RUN pip3 install -r requirements.txt #install requirements
EXPOSE 80 #expose port 80
ENTRYPOINT ["python3"] #entrypoint
CMD ["app.py"] #command
```

deep learning nvidia pytorch install
```bash
docker run --gpus all -it --rm -p 8888:8888 -v /home/yomiko:/workspace nvcr.io/nvidia/pytorch:23.04-py3
#--gpus all means use all gpu
#-it means interactive mode
#--rm means remove container after exit
#-v means volume mapping
#-p means port mapping
nvidia -smi #check gpu
```
```python
import torch
torch.cuda.is_available() #check cuda
torch.version.cuda
torch.__version__
torch.cuda.device_count() #check gpu count
torch.cuda.get_device_name(0) #check gpu name
torch.cuda.get_device_name(1)
torch.cuda.current_device() #check current gpu
```
load local file
```bash
docker load < file.tgz #tgz is the 
```

### Docker Compose
docker compose is a tool for defining and running multi-container docker applications.
```bash
$ docker-compose --version #check version
$ docker-compose up #run docker-compose.yml
$ docker-compose up -d #run docker-compose.yml in background
$ docker-compose down #stop docker-compose.yml
$ docker-compose ps #check running container
$ docker-compose ps -a #check all container
$ docker-compose images #check images
$ docker-compose exec container_name bash #enter container
$ docker-compose logs container_name #check logs
$ docker-compose build #build docker-compose.yml
$ docker-compose push #push docker-compose.yml
```
### Docker Hub
docker hub is a cloud-based registry service which allows you to link to code repositories, build your images and test them, stores manually pushed images, and links to Docker Cloud so you can deploy images to your hosts.
```bash
$ docker login #login docker hub
$ docker tag image_id username/repository:tag #tag image
$ docker push username/repository:tag #push image
$ docker run username/repository:tag #run image
```

## SSH
ssh is a cryptographic network protocol for operating network services securely over an unsecured network.
### Install
```bash
$ sudo apt-get install openssh-server
```
### Basic
```bash
$ ssh username@ip #connect to server
$ ssh -p port username@ip #connect to server with port
```
```bash
#for not input password and username
$ ssh-keygen #generate public key and private key for prevent password
$ ssh-copy-id username@ip #copy public key to server
$ vim ~/.ssh/config
Host server
    HostName ip
    Port port
    User username
    IdentityFile ~/.ssh/id_rsa
```
### login without password and username
```bash
#for transfer file
#where username@ip can be replaced by server 
$ scp file username@ip:/path/to/file #copy file from host to server
$ scp username@ip:/path/to/file /path/to/file #copy file from server to host
$ scp -r file username@ip:/path/to/file #copy directory from host to server
```
### Keep the program running after logout
```bash
#tmux
remote$ tmux #create tmux
#temporarily detach #ctrl+b d
remote$ tmux attach #attach tmux
#if macOS, use iTerm2 and tmux -CC
```

## Cmake
cmake is an open-source, cross-platform family of tools designed to build, test and package software.
**gcc** is a compiler system produced by the GNU Project supporting various programming languages.

### Install
```bash
$ sudo apt-get install cmake
```
### Basic
```bash
$ cmake --version #check version
$ cmake . #generate makefile
$ make #compile
$ make install #install
```
### CMakeLists.txt
```cmake
cmake_minimum_required(VERSION 3.10) #cmake version
