clean:
	latexmk -C

all:
	presentation

presentation:
	pandoc \
		--slide-level 2 \
		--from markdown+yaml_metadata_block+table_captions \
		--to beamer \
		--include-in-header presentation-header.tex \
		--listings \
    	--highlight-style espresso \
		--include-before-body presentation-toc.tex \
		--natbib \
		--bibliography bibliography.bib \
		--csl citation.csl \
		--output presentation.tex \
		presentation*.md
	latexmk -pdflatex="pdflatex --shell-escape %O %S" -pdf presentation.tex
