SRCFILE = user_manual
MANUAL_FILES = user_manual.tex
LATEX_FLAGS=-interaction=nonstopmode

all: Economics_for_RAVEN_user_manual.pdf

Economics_for_RAVEN_user_manual.pdf: $(MANUAL_FILES) version.tex
	pdflatex $(LATEX_FLAGS) $(SRCFILE).tex
	bibtex $(SRCFILE)
	pdflatex $(LATEX_FLAGS) $(SRCFILE).tex
	pdflatex $(LATEX_FLAGS) $(SRCFILE).tex

.PHONY: clean

clean:
	@rm -f *~ *.aux *.bbl *.blg *.log *.out *.toc *.lot *.lof $(SRCFILE).pdf

#creating version file
version.tex : $(MANUAL_FILES)
	git log -1 --format="%H %an %aD" .. > version.tex


