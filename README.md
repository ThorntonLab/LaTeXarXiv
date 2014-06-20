Making life easier
==========
__(Any commands used in this document assume a Unix-like operating system.)__

If you write manuscripts usind [LaTex](http://www.latex-project.org/), then you must submit unprocessed source code + image files to [arXiv](http://arxiv.org).  The process can be frustrating, and the following tips/tricks have made life easier for us:

1. arXiv does allow you to upload a zip file of all of your files.  I include the following: all tex files, the .bib, .bbl, .bst files if they are custom (e.g., you are using a journal's .bst file).
2. If you are using [natbib](http://merkel.zoneo.net/Latex/natbib.php), then include the natbib.sty from your system with your upload.  arXiv/natbib is a common source of [issues](http://arxiv.org/help/faq/texlive).

Details
=====

If using an editor like emacs, you may have file names like foo.tex~ in your folder.  Get rid of these.  I have seen arXiv process these instead of the main .tex file!!!.  To remove:
```{sh}
find . -name "*~" | xargs rm -f
```

It is best to stage a "clean" set of files to upload.  The easiest way to do this is to use a version control system like [github](github.com).  Simply clone your repo, zip it up, and upload it.

If you need to locate the natbib.sty that you used, you should use the "locate" command.  (Sadly, OS X's finder does not index /usr where your [MacTex](https://tug.org/mactex/) installation is sitting.  The first time you run locate on OS X, you may get a warning about needing to build the database--follow the instructions and wait.)  

On my OS X Mavericks system:

```{sh}
locate natbib.sty
/usr/local/texlive/2012/texmf-dist/tex/latex/natbib/natbib.sty
/usr/local/texlive/2013/texmf-dist/tex/latex/natbib/natbib.sty
```

I simply copy the latter result into my document's main folder.

Organizing a LaTeX document
====
For large/complex documents, I do not write a single .tex file.  Rather, I use the [input](http://en.wikibooks.org/wiki/LaTeX/Modular_Documents) command such that a paper will look like this

```
\begin{document}
\input{Text/Abstract}
\input{Text/Intro}
\input{Text/Methods}
\input{Text/Results}
\input{Text/Discussion}
\end{document}
```

This sort of structure allows you to re-order sections, figures, tables, etc., quickly.  The caveat is that some journals are still in the 20th century and require the submission of a single .tex file.
