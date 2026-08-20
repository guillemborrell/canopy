TECTONIC ?= tectonic

.PHONY: all clean arxiv

all: main.pdf

main.pdf: main.tex references.bib $(wildcard figures/*.png)
	$(TECTONIC) --keep-intermediates main.tex

arxiv: main.bbl
	tar -czf arxiv-source.tar.gz main.tex main.bbl references.bib figures

main.bbl: main.tex references.bib
	$(TECTONIC) --keep-intermediates main.tex

clean:
	rm -f main.aux main.blg main.log main.out arxiv-source.tar.gz
