SOURCES=$(wildcard *.md)
DIR=/usr/local
#/home/$(USER)/devel/templates

TEMPLATE=$(DIR)/kth_thesis/kth-mag.template
BIBTEX=example.bib
CSL=$(DIR)/styles/ieee-with-url.csl
TARGET = build

PANDOC_OPTIONS=-f markdown+table_captions --listings --table-of-contents --mathjax=https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML --chapters --include-after-body=$(TARGET)/appendix.tex

PANDOC_REFERENCES=--csl=$(CSL) --bibliography=$(BIBTEX)

RM = /bin/rm -f
PANDOC = pandoc
RSCRIPT=/usr/bin/Rscript
LATEX=xelatex

TEX_OBJECTS=$(SOURCES:.md=.tex)
PDF_OBJECTS=$(SOURCES:.md=.pdf)

pdf: $(TARGET) appendix $(PDF_OBJECTS)
tex: $(TARGET) appendix $(TEX_OBJECTS)

appendix:
	pandoc includes/appendix.md -t latex --chapters -o $(TARGET)/appendix.tex

$(TARGET):
	-mkdir $(TARGET)

%.tex: %.md
	$(PANDOC)  -t latex --template=$(TEMPLATE) $(PANDOC_OPTIONS) $(PANDOC_REFERENCES) -o $(TARGET)/$@ $<

%.pdf: %.md
	$(PANDOC) --latex-engine=$(LATEX) --template=$(TEMPLATE) $(PANDOC_OPTIONS) $(PANDOC_REFERENCES) -o $(TARGET)/$@ $<

clean:
	-$(RM) $(HTML_OBJECTS)
	-$(RM) -r figure $(TARGET) cache
