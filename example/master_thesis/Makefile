SOURCES=$(wildcard *.md)
DIR=../../../
#/home/$(USER)/devel/templates

TEMPLATE=$(DIR)/kth_thesis/kth-mag.template
BIBTEX=example.bib
CSL=$(DIR)/styles/ieee.csl

TARGET=build

PANDOC_OPTIONS=-f markdown+table_captions --table-of-contents --filter pandoc-shortcaption --mathjax=https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML --chapters
#--filter pandoc-crossref --number-sections

PANDOC_REFERENCES=--csl=$(CSL) --bibliography=$(BIBTEX)

RM = /bin/rm -f
PANDOC = pandoc
RSCRIPT=/usr/bin/Rscript
LATEX=/usr/bin/xelatex

TEX_OBJECTS=$(SOURCES:.md=.tex)
PDF_OBJECTS=$(SOURCES:.md=.pdf)

pdf: $(TARGET) $(TEX_OBJECTS) $(PDF_OBJECTS)

%.tex: %.md
	$(PANDOC)  -t latex --template=$(TEMPLATE) $(PANDOC_OPTIONS) $(PANDOC_REFERENCES) -o $(TARGET)/$@ $<

#-interaction=batchmode
%.pdf: %.tex
	$(LATEX) -output-directory=$(TARGET) $(TARGET)/$<
	$(LATEX) -interaction=batchmode -output-directory=$(TARGET) $(TARGET)/$<
	-ln -s $(TARGET)/$@

$(TARGET):
	-mkdir $(TARGET)

clean:
	-$(RM) $(HTML_OBJECTS) $(TEX_OBJECTS)
	-$(RM) -r figure $(TARGET) cache
