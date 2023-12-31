This is a custom Latex template based of the Latex template of SeniorMars: https://github.com/SeniorMars/dotfiles/tree/master/latex_template.
I have simply added a list of equations and some customs commands used in some of my mathematics and physics courses. 

To import the common.sty, you can use `one`, `two` or `three` as a package option. This will simply let the common.sty know how far the current latex file you are working on is. (Basically how many `cd ..` should you do to reach common.sty):
```
\documentclass{report}
\def\package_import{..}
\usepackage[one]{\package_import/common}
```

For the equation list to appear properly, you first need to have `\let\cleardoublepage=\clearpage` before creating the document. After, inside the `\begin{document}` block use:
```
\maketitle
\newpage

\begingroup
\let\cleardoublepage\relax
\let\clearpage\relax
\tableofcontents
\endgroup
\newpage
\begingroup 
\let\cleardoublepage\relax
\let\clearpage\relax
\listofmyequations
\endgroup
```
You will then be able to use `\tonote{equation}{Name of equation}` to add equations to the equation list.
