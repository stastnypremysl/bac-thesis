export TEXINPUTS=../tex//:

all: thesis.pdf abstract.pdf

# LaTeX must be run multiple times to get references right
thesis.pdf: thesis.tex $(wildcard *.tex) bibliography.bib thesis.xmpdata
	xelatex -shell-escape -output-driver="xdvipdfmx -z 0" $<
	bibtex thesis
	xelatex -shell-escape -output-driver="xdvipdfmx -z 0" $<
	xelatex -shell-escape -output-driver="xdvipdfmx -z 0" $<

abstract.pdf: abstract.tex abstract.xmpdata
	xelatex -shell-escape -output-driver="xdvipdfmx -z 0" $<

clean:
	rm -f *.log *.dvi *.aux *.toc *.lof *.lot *.out *.bbl *.blg *.xmpi
	rm -f thesis.pdf abstract.pdf
