all: proposal

frontandacm: frontpages acm
	pdftk frontpages.pdf acm-main.pdf cat output proposal.pdf
	# pdfedit proposal.pdf remove pagination for frontpages, couldn't figure out how to tweak the mit layout to remove them

proposal: main.tex
	pdflatex main && bibtex main && pdflatex main && pdflatex main

frontpages: frontpages.tex
	pdflatex frontpages

acm: acm-main.tex
	pdflatex acm-main && bibtex acm-main && pdflatex acm-main && pdflatex acm-main

clean: 
	rm -f *.dvi *.aux *.log *.blg *.toc *.bbl *~ *.lof *.lot *.out

extraclean: 
	rm -f *.pdf *.dvi *.aux *.log *.blg *.toc *.bbl *~ *.lof *.lot *.out

viewpdf:
	pdflatex main && bibtex main && pdflatex main && pdflatex main && evince main.pdf
	rm -f *.dvi *.aux *.log *.blg *.toc *.bbl *~ *.lof *.lot *.out
	# TODO: how can I call 'clean' instead of having to copy-paste the command?

problem: 
	latex problem.tex && dvips problem.dvi && ps2pdf problem.ps; 
