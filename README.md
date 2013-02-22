# Description

This repository contains files needed to generate a presentation for the SIAM CSE 2013 Meeting in Boston, MA.

## Dependencies

- Pandoc

## Instructions

### Generating a pretty-printed version of this README

Use the command:

    pandoc -t html README.md -o README.html
    
I use Pandoc to convert Markdown to HTML, but for this README, any Markdown to HTML converter should suffice.

### Generating slide shows:

Sizing of images varies based on format. For instance, 150 pixel by 200 pixel images fill space nicely in Beamer slides, but look tiny in S5 slides (as would be expected).

To generate an barebones S5 presentation from the talk notes, use the command:

    pandoc -t s5 talk-sketch.md --self-contained -o talk-sketch.html
    
To customize the S5 talk, it is probably better to modify the base command

    pandoc -t s5 talk-sketch.md -o talk-sketch.html
    
and add stylesheets, and so forth.

To generate a beamer presentation in PDF format from the talk notes, use the command:

    pandoc -t beamer talk-sketch.md -o talk-sketch.pdf

