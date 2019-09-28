# thesis

Do you hate wasting time doing exactly the same thing that every other person
in your office has to do? Me too! I wasted at least a solid week typesetting my
thesis, despite the fact that every single phd student has had to do the same
thing. Least. Efficient. Thing. Ever. To try to break this endless cycle, I've
put together a simple template that typesets your thesis for you! Here are some
of my favorite features:
* Edit individual files for each chapter instead of one monster file.
* Build with a single command... so easy!
* Maintain one bibliography, because you cite the exact same people every time.
Feel free to modify this as you wish, but hopefully you won't spend as much time
as I did.

## Installation

Over the years I did horrible things to my latex installation, so I found it
easiest to re-install Texlive from scratch. Steps to do this are [described here](https://www.tug.org/texlive/quickinstall.html).
It's not the clearest, but it's not that tough when you get there. If you do this
you will not need to install any additional packages to compile the thesis... yay!
If not, good luck.

I personally like working in a virtual environment, so if you do too you can use
the user mode from tlmgr:
```{bash}
tlmgr init-usertree --usertree ~/test-tree^C
export TEXMFHOME=~/test-tree
tlmgr update --all
```
If you don't always want to export the user profile, add it to your `.bashrc`.

## Use

You can compile the example by cd'ing into the directory and running `./build.sh`.
If this compiles correctly, great! If not, you'll need to debug to figure out what's
wrong. Here are some points about how to use the template:
* The main file is `thesis.tex`, which defines all of the packages and user defined functions. If you use special packages, add them here.
* Modify the title `pages.tex`, `sommaire.tex`, `acknowledgements.tex`, and `introduction.tex` as you need to.
* Copy and paste the body of your papers into the chapter files (package includes should be placed in `thesis.tex`).
* Change all of your `\cite` calls to `\citeIntro`, `\citeSomm`, `\citeOne`, `\citeTwo`, or `\citeThree`, depending on what section they are in.
* Place all your bibliography entries in the `mybib.bib` file.