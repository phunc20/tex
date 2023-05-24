LATEXC=pdflatex
# https://tex.stackexchange.com/questions/140845/how-can-i-ignore-latex-error-while-compiling
#LATEXFLAGS="--shell-escape -interaction nonstopmode -halt-on-error -file-line-error"
#LATEXFLAGS=
LATEXFLAGS="--shell-escape"

.PHONY: all clean

all: overleaf_minted_example.pdf

overleaf_minted_example.pdf: overleaf_minted_example.tex
	$(LATEXC) $(LATEXFLAGS) overleaf_minted_example.tex #2&> /dev/null

clean:
	@echo "removing *.{log,aux,out}, if exists"
	@for fname in *.{log,aux,out}; do \
	    if test -f $$fname; then rm $$fname; fi \
	done
