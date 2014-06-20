Making life easier
==========

If you write manuscripts usind [LaTex](http://www.latex-project.org/), then you must submit unprocessed source code + image files to [arXiv](http://arxiv.org).  The process can be frustrating, and the following tips/tricks have made life easier for us:

1. arXiv does allow you to upload a zip file of all of your files.  I include the following: all tex files, the .bib, .bbl, .bst files if they are custom (e.g., you are using a journal's .bst file).
2. If you are using [natbib](http://merkel.zoneo.net/Latex/natbib.php), then include the natbib.sty from your system with your upload.  arXiv/natbib is a common source of [issues](http://arxiv.org/help/faq/texlive).

Details
=====

1.  If using an editor like emacs, you may have file names like foo.tex~ in your folder.  Get rid of these.  I have seen arXiv process these instead of the main .tex file!!!.  To remove:
```{sh}
find . -name "*~" | xargs rm -f
```
2.  It is best to stage a "clean" set of files to upload.  The easiest way to do this is to use a version control system like [github](github.com).  Simply clone your repo, zip it up, and upload it.
