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

All slides are at "level 2", which is to say that headings beginning with "##" in Markdown (or within h2 tags in HTML) are slide titles. The only level 1 heading is used for the presentation title.

To generate an barebones S5 presentation from the talk notes, use the command:

    pandoc -t s5 talk-sketch.md --slide-level 2 --self-contained -o talk-sketch.html
    
To customize the S5 talk, it is probably better to modify the base command

    pandoc -t s5 talk-sketch.md --slide-level 2 -o talk-sketch.html
    
and add stylesheets, and so forth.

To generate a beamer presentation in PDF format from the talk notes, use the command:

    pandoc -t beamer talk-sketch.md --slide-level 2 -o talk-sketch.pdf

