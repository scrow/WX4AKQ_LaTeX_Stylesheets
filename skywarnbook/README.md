# SKYWARN LaTeX Template #

This repo provides a standard template for SKYWARN Operations Manuals, training manuals, and other book or manual-style documentation.  Refer to the comments in the `skywarnbook.sty` file for configuration options and provided commands.

## Modifying the Master Template ##

Clone the repository to a new Git workspace:

```
mkdir -p ~/projects/doc-template
git clone ssh://wx4akq@sdf.org/~/git/doc-template ~/projects/doc-template
git fetch origin master

```

Create a new branch for your changes:

```
git checkout -b newupdates
```

Perform your edits, commit, and push to the repo:

```
git commit -a -m 'various updates'
git push --set-upstream origin newchanges
```

When ready to merge and delete the branch:

```
git checkout master
git merge newchanges
git branch -d newchanges
```

## Using the Template ##

Clone the repository into the appropriate TeX folder, then run `texhash`:

* Windows XP: `C:\Documents and Settings\<user name>\texmf\tex\latex\local`
* Windows Vista/7: `C:\Users\<user name>\texmf\tex\latex\local`
* Linux: `~/texmf/tex/latex/local`
* Mac OS X: `~/Library/texmf/tex/latex/local`

Note:  Using MacTeX, it may be necessary to drop out to terminal and run:

```
mkdir -p ~/texmf/tex/latex/local
sudo tlmgr conf texmf TEXMFHOME "~/Library/texmf:~/texmf"
```

To perform the clone:

```
git clone ssh://wx4akq@sdf.org/~/git/doc-template <tex path>/skywarnbook
cd <tex path>/skywarnbook
git fetch origin master
texhash  // not necessary on all systems
```

Create your LaTeX document:

```
\documentclass[pdflatex,letterpaper,twoside,12pt]{book}

\title             {Sample Document}
\author            {John Doe}
\date              {24-Jan-2014}
\newcommand\docver {Version 1.0}

\usepackage{skywarnbook}
\skywarnFormat{printing}
\disableAutoNumbering
\useColorLinks

\begin{document}
\skywarnTitlePage
\skipToTOC
\skywarnTOC

\chapter{Chapter One}
\section{Section One}
Sample text.

\chapter{Chapter Two}
\section{Section Two}
Sample text.

\end{document}
```

## Updating the Template Version ##

Use these commands if you have __not__ made any changes to the template file.  This will discard any local changes and pull the newest version:

```
cd <tex path>/skywarnbook
git stash; git stash drop
git fetch origin master
```

The re-compile your document(s).

## Modifying the Template for Local Use ##

To modify your copy of the template:

```
cd <tex path>/skywarnbook
checkout -b myversion
```

Commit your changes to the `myversion` branch.

__IMPORTANT:  Do not push your changes to the `master` branch!__

To pull down and merge changes in the upstream version:

```
git fetch origin master
git merge master
get commit -a -m 'merged with master'
```

## Code Maintainer ##

This project is maintained by Steve Crow KG4PEQ, <kg4peq@wx4akq.org>.
