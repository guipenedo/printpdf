# printpdf
Simple script to make my life easier when I need to prepare multiple pdfs for printing.

## Requirements
 - texlive-extra-utils 
 - ghostscript

## Usage
```
usage: printpdf [-h] [--output OUTPUT] [--gray] [--nup NUP] [--scale] pdfs [pdfs ...]

Prepare documents for printing

positional arguments:
  pdfs                  a list of pdf files (ordered) to merge

optional arguments:
  -h, --help            show this help message and exit
  --output OUTPUT, -o OUTPUT
                        output file
  --gray, -g            convert to grayscale
  --nup NUP, -n NUP     1, 2 or 4
  --scale, -s           super scale
```

### Options description
- -o is the output file location, defaults to `output.txt`
- -g will turn the pdf into grayscale
- -n will n-up the image. For example, `-n 4` will yield a 4 pages per sheet pdf
- -s will "aggressively" scale up the pdf up to the margin, useful for wide margin pdfs that you want to n-up

## Behaviour
All the pdfs provided are first merged, then, by this order (if selected):
1. scaled
1. converted to grayscale
1. n-uped

To simply merge the pdfs, do not use any additional options.

## Example
Merging 3 pdfs, turning them into grayscale, scaling and n-uping (2 pages per sheet):
```
printpdf -g -s -n 2 problems_fourier_transform_correction.pdf tutorial1-correction-2020-2021.pdf tutorial2-correction-2020-2021.pdf Tutorial_3_corrige.pdf -o tutorials.pdf
```
