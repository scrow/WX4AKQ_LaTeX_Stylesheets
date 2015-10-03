# Synopsis

This repository contains LaTeX stylesheets and other supporting resources to be used in documentation produced and published by the NWS Wakefield SKYWARN Amateur Radio Support Team.  The LaTeX stylesheets in this repo can be used to generate manuals and other reference materials using a LaTeX compiler.

# Installation

The use of these stylesheets currently requires the following packages are available on the LaTeX system at compile time:

	babel
	everypage
	extsizes
	fancyhdr
	float
	geometry
	graphicx
	hyperref
	ifthen
	moreverb
	parskip
	ragged2e
	tcolorbox
	titlesec
	upquote
	url
	xcolor

If these packages are not available, compilation will fail.

# Usage

For Git-managed projects, these files should be included as a Git submodule:

	git submodule add git://github.com/scrow/wx4akq-latex-stylesheets.git sty
	git submodule update
	git add sty

All other projects may either clone the files or download directly from Github:

	git clone git://github.com/scrow/wx4akq-latex-stylesheets.git sty

Here is a code example using the "book" format:

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
	\end{document}

# Contributors

This code is maintained by [Steve Crow](mailto:scrow@sdf.org).

# License

This work is Copyrighted and is licensed under GPLv3.  Please see the separate LICENSE.txt file for license information.