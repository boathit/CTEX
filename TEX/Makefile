LATEX ?= xelatex
VIEW_PDF ?= evince

main.pdf: main.tex $(tex_files)
	@mkdir -p build/data

	$(LATEX) -output-dir=build main.tex
	$(LATEX) -output-dir=build main.tex


	@mv build/main.pdf main.pdf
	$(VIEW_PDF) main.pdf

clean:
	rm -rf build
	rm main.pdf
view:
	$(VIEW_PDF) main.pdf
cleanall:
	find . -name '*~' | xargs rm -rf
	find . -name '*.swp' | xargs rm -rf
	find . -name '*.bak' | xargs rm -rf
	rm -rf build
	rm main.pdf
