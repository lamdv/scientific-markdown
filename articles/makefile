clean:
	latexmk -C

all:
	article

chapters := $(wildcard chapters/*.md)

article: $(chapters)
	pandoc \
		--from markdown+yaml_metadata_block+table_captions \
		--to pdf \
		--variable documentclass=article \
		--variable classoption=twocolumn \
		--variable classoption=12pt \
		--number-sections \
		--listings \
		--natbib \
		--bibliography ref.bib \
		--csl citation.csl \
		--output article.pdf \
		--pdf-engine latexmk \
		--standalone \
		article.md $(chapters) ref.md
