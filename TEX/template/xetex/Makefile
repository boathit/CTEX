XELATEX		?=		xelatex
VIEW_PDF	?=		okular
tex_files 	?= 		$(wildcard data/*tex)
bib_files 	?= 		$(wildcard data/main.bib)

main.pdf: main.tex $(tex_files) $(bib_files)
	@mkdir -p build/data

	$(XELATEX) -output-dir=build main.tex

	## http://tex.stackexchange.com/questions/12686/how-do-i-run-bibtex-after-using-the-output-directory-flag-with-pdflatex-when-fi
	## compiling bib file using bibtex
	 #@cp data/main.bib build/data
	 #@cd build/; bibtex main 

	$(XELATEX) -output-dir=build main.tex
	$(XELATEX) -output-dir=build main.tex

	@mv build/main.pdf main.pdf

html: main.tex
	tth -u main.tex

rtf: main.tex
	latex2rtf main.tex

view:
	$(VIEW_PDF)	main.pdf

.PHONY: clean clean_auctex_auto clean_backup_files cleanall
clean:
	rm -rf build
##	rm -rf main.pdf

clean_auctex_auto:
	find . -name auto | xargs rm -rf

clean_backup_files:
	@echo "clean backup files"
	find . -name '*~' | xargs rm -rf 		# clean emacs backup files
	find . -name '*.swp' | xargs rm -rf		# clean vim backup files 
	find . -name '*.bak' | xargs rm -rf		# clean some .bak files

cleanall: clean clean_auctex_auto clean_backup_files
	rm -rf main.html
	rm -rf main.rtf
