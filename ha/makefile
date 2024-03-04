# makefile: Rnw -> tex -> pdf
# v 2.0
# .Rnw extension is automatically added
file_name = tssp_ha

$(file_name).pdf: $(file_name).tex 
	# protection against biber error
	# http://tex.stackexchange.com/questions/140814/
	rm -rf `biber --cache`

	# create pdf
	# will automatically run pdflatex/biber if necessary
	latexmk -xelatex -latexoption=-shell-escape $(file_name).tex
	# arara -v $(file_name).tex

	# clean
	# latexmk -c $(file_name).tex



clean:
	latexmk -c $(file_name).tex
	-rm $(file_name).amc 
	-rm $(file_name).bbl 
	-rm $(file_name).log
	-rm $(file_name).fdb_latexmk 
	-rm $(file_name).fls 
	-rm $(file_name).xdv
	-rm $(file_name).pyg
	-rm $(file_name).synctex.gz
	
