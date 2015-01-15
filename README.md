# Hacking the LaTeX source for the leaflet

This is my attempt at documenting some basics that will enable non LaTeX users to tinker with the flyers. It is not meant to be an exhaustive tutorial on LaTex. I've collected some general resources for LaTeX at the end of this document.

## Environment setup
This document assumes you're using a [stable version of Fedora](http://getfedora.org). To set up LaTeX, you can use your favourite package manager (yum/dnf/yumex/packagekit) to install the texlive suite:

### LaTeX bits
```
    sudo dnf install texlive-latex
```

For the leaflet, we need to install a couple of other LaTeX packages too:

```
    sudo dnf install texlive-{leaflet,fancyhdr,graphics,comfortaa,hyperref,latex-bin-bin}
```

If you need others, you can always use:

```
    sudo dnf install 'tex(package.sty)'
```

for example, we could've also done:

```
    sudo dnf install 'tex(comfortaa.sty)'
```

### Editor 
Use whatever editor you like. I use vim with vim-latex.

#### With vim and vim-latex

```
    sudo dnf install vim vim-latex
```

Add this to your `~/.vimrc`:

```
    " latex stuff
    let g:tex_flavor='latex'
    " indentation for tex files
    au FileType tex set sw=2
    "Spell check
    au FileType tex setlocal spell spelllang=en_gb
    " Vim-latex rules: 
    " to enable \ll to run automatically for pdfs
    let g:Tex_DefaultTargetFormat='pdf'
    let g:Tex_MultipleCompileFormats='dvi,pdf'
```

After this it's rather simple. Open the file in vim, make changes, save and use `\ll` to compile and `\lv` to view the file in the default pdf viewer.

#### Other editors
Most of them have plugins, but I don't know about them. You can even use something like gedit and then use a terminal to compile the tex into pdf using pdflatex. That's effectively what `\lv` in vim-latex does.

## Getting started
To clone my repo, you should first [fork it on github and then clone it](https://guides.github.com/activities/forking/).
Then, get started!

You need to have git installed, of course:

```
    sudo dnf install git
```

LaTeX commands are fortunately quite self-explanatory. For example, some commands used in the leaflet are:

* `\section{foo}` - starts a new section called "foo"
* `\subsection{bar}` - starts a new subsection called "bar"
* `\includegraphics{something.png}` - includes an image called something.png
* `\begin{itemize}` - starts an unordered list while `\end{itemize}` ends it.
* `\item xxx` - is an item in the ordered list
* `\newpage` - forces the text after the command to start from a new page
* `\href{http://fedoraproject.org}{Fedora project}` - adds links the text "Fedora project" to http://fedoraproject.org.

## Other resources
### VIM
You should first go through the `vimtutor`. In a terminal:

```
    vimtutor
```

It teaches you basic navigation commands etc. Then, you should just Google what you want to do and you'll probably find a blog post or a stackexchange link with an answer.

### LaTeX
The wikibook can be used as a reference especially - just look for the specific task that you're trying to complete.

* [http://www.maths.tcd.ie/~dwilkins/LaTeXPrimer/](http://en.wikibooks.org/wiki/LaTeX)
* [http://en.wikibooks.org/wiki/LaTeX](http://en.wikibooks.org/wiki/LaTeX)

## More help?
Just e-mail me or catch me on the IRC sometime. I hang around in a couple of Fedora channels.
