# Description

This repository contains files needed to generate a presentation for the SIAM CSE 2013 Meeting in Boston, MA.

## Dependencies

- Pandoc

## Instructions

### Generating a pretty-printed version of this README

Use the command:

    pandoc -t html README.md -o README.html
    
I use Pandoc to convert Markdown to HTML, but for this README, any Markdown to HTML converter should suffice.

### Generating the presentation

To generate an S5 presentation from the talk notes, use the command:

    pandoc -t s5 talk-sketch.md -o talk-sketch.html
    
To generate a beamer presentation in PDF format from the talk notes, use the command:

    pandoc -t beamer talk-sketch.md -o talk-sketch.pdf
