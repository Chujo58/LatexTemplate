This is a custom Latex template based of the Latex template of SeniorMars: https://github.com/SeniorMars/dotfiles/tree/master/latex_template.
I have simply added a list of equations and some customs commands used in some of my mathematics and physics courses.

## Importing the package into latex

To import the common.sty, you can use `one`, `two` or `three` as a package option. This will simply let the common.sty know how far the current latex file you are working on is. (Basically how many `cd ..` should you do to reach common.sty). You can also use the argument `extra-page` to have extra pages after the end of each problem.

```
\documentclass{report}
\def\package_import{..}
\usepackage[one]{\package_import/common}
```

## Setting up the table of equations

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

## Using the homework boxes template

The homework template is pretty simple. It allows to copy the question and then answer them right after, making for a nice and easy to read document. To create the question box the command `\hwq{Name of the question}{Question text}` is what you use. If the question/problem doesn't have subquestions, you can directly use the `\sol{Solution text}` command to enter your solution. For subquestions, use `\hwsq{Current section number}{Subquestion text}{Subquestion solution text}`.

Now to setup the header of your pdf: (You will need to add a space after the course name if you want it to look nice!)

```
\defcourse{Name of the course }
\defassignnum{Number of the assignment}
\startassign{Your name}
```
