# Latex

## Packages

### TeX Live

- TeX-related programs, packages, fonts, softwares...

## Useful

- Fit width: `\includegraphics[width=\linewidth]{...}`
- Footnote: `\footnote{\url{}}`
- Scale: `\usepackage[scale=0.78]{geometry}`
- Make index: 
	- `pdflatex text.tex`
	- `makeindex text.tex` 
	- `pdflatex text.tex`

## Bibtex

Suppose you have article.tex and article.bib. You need to run:

`latex article.tex` (this will generate a document with question marks in place of unknown references)
`bibtex article` (this will parse all the .bib files that were included in the article and generate metainformation regarding references)
`latex article.tex` (this will generate document with all the references in the correct places)
`latex article.tex` (just in case if adding references broke page numbering somewhere)
