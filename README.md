There are two directories in ctex named TEX and texmf.

texmf containing the ctex configure files and some sty packages.
TEX containing the preamble.tex, Makfile and template

Usage: 

Step-1:

    Put TEX and texmf in your home directory. Be sure you have installed
    texlive and corresponding chinese fonts(check them in texmf/tex/latex/ctex/fontset/).
    
Step-2:

     Writing a latex file(like main.tex in TEX)
     
Step3:

    Copy the Makefile in TEX to your current work directory, naming the latex source file main.tex
    and running:
    $make


Notices: ctex and some templates coming from the Internet.
