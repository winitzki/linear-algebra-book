# Makefile for the Linear Algebra book by Sergei Winitzki

# xfig source files
FIGSRC=v1v2-vol.fig 3dparallelepiped_1.fig 2darea.fig indstep.fig
# lyx source files
LYXSRC=linalg.lyx gfdl.lyx
# final PDF file with source included
PDFWITHSRC=Linear_algebra_exterior.pdf

.SUFFIXES : .fig .eps

# extra files
EXTRAFILES=Makefile README.txt Sergei_Winitzki_blackboard_2008.eps

FIGEPS=$(FIGSRC:.fig=.eps)
TEXSRC=$(LYXSRC:.lyx=.tex)

# run latex until no references are changed
define runlatex
latex $(firstword $^)
while grep -q 'LaTeX Warning.*Rerun' $(addsuffix .log,$(basename $(firstword $^))); do latex $(firstword $^); done
endef

# run latex and makeindex together
define runlatexidx
$(runlatex)
makeindex $(addsuffix .idx,$(basename $(firstword $^)))
$(runlatex)
endef

$(PDFWITHSRC): linalg.pdf linalg.tar.gz
	pdftk linalg.pdf attach_files linalg.tar.gz output $@
linalg.tar.gz: $(LYXSRC) $(TEXSRC) $(FIGSRC) $(FIGEPS) $(EXTRAFILES)
	tar zcvf linalg.tar.gz $(LYXSRC) $(TEXSRC) $(FIGSRC) $(FIGEPS) $(EXTRAFILES)
.fig.eps:
	fig2dev -L eps $< $@
#3dparallelepiped_1.eps: 3dparallelepiped_1.fig
#	fig2dev -L eps 3dparallelepiped_1.fig 3dparallelepiped_1.eps
linalg.tex: linalg.lyx
	lyx --export latex linalg.lyx
	mv linalg.tex 1linalg.tex
	cat 1linalg.tex | LC_ALL=C sed -e 's,usepackage{mathpazo},usepackage{palatino},' > linalg.tex
	rm 1linalg.tex
gfdl.tex: gfdl.lyx
	lyx --export latex gfdl.lyx
linalg.dvi: $(TEXSRC) $(FIGEPS)
	$(runlatexidx)
linalg.pdf: linalg.dvi
	dvips linalg.dvi
	ps2pdf linalg.ps

# replace paper sizes and document style options here
linalg-book-print.tex: linalg.tex Makefile
	LC_ALL=C sed -e 's|geometry{.*[bt]margin=.*,.*}|geometry{paperwidth=6.2in,paperheight=9.3in}|; s|documentclass\[[a-z0-9,]*\]{.*}|documentclass[10pt,twoside,english,american,pointlessnumbers,openright,idxtotoc,cleardoubleempty]{scrbook}|; s,wanthyperlinkstrue,wanthyperlinksfalse,;  s,wantphotoblurbtrue,wantphotoblurbfalse,; s,thisispdffiletrue,thisispdffilefalse,; s,thisisminitrue,thisisminifalse,; s|begin{document}|begin{document}\n \\special{papersize=6in,9in}\\typearea[13mm]{1}|' < linalg.tex > $@
# note: paperwidth=6in,paperheight=8in in geometry but \\special{papersize=6in,9in}\\typearea[12mm]{20}| reproduces the same width but wrong height

linalg-book.tex: linalg.tex Makefile
	LC_ALL=C sed -e 's|geometry{.*[bt]margin=.*,.*}|geometry{paperwidth=6in,paperheight=9in,tmargin=15mm,bmargin=12mm,lmargin=20mm,rmargin=17mm}|; s|documentclass\[[a-z0-9,]*\]{.*}|documentclass[10pt,english,american,pointlessnumbers,openright,idxtotoc,cleardoubleempty]{scrbook}|; s,thisisminitrue,thisisminifalse,;s|begin{document}|begin{document}\n \\special{papersize=6in,9in}\\typearea[6mm]{1}|;' < linalg.tex > $@

# pdf file for online distribution: book formatting, hyperlinks, embedded source
linalg-book.dvi: linalg-book.tex $(TEXSRC) $(FIGEPS) linalg.tar.gz
	$(runlatexidx)
linalg-book.pdf: linalg-book.dvi
	dvips -Ppdf -G0 linalg-book.dvi -o
	ps2pdf13 -dEmbedAllFonts=true -dSubsetFonts=false -dPDFSETTINGS=/printer linalg-book.ps

linalg-ebook.pdf: linalg-book.pdf
	cp linalg-book.pdf linalg-book1.pdf
	pdftk linalg-book1.pdf attach_files linalg.tar.gz output $@
	rm -f linalg-book1.pdf

# pdf file only for printing: no hyperlinks, no embedded source
linalg-book-print.pdf: linalg-book-print.tex $(TEXSRC) $(FIGEPS) Makefile linalg-book.pdf
	$(runlatexidx)
	dvips -Ppdf -G0 linalg-book-print.dvi -o
	ps2pdf13 -dEmbedAllFonts=true -dSubsetFonts=false -dPDFSETTINGS=/printer linalg-book-print.ps
	mv linalg-book-print.pdf linalg-book-print1.pdf
	pdftk linalg-book-print1.pdf attach_files linalg.tar.gz linalg-book.pdf output $@
	rm -f linalg-book-print1.pdf
clean:
	rm -f *.pdf *.aux *.dvi *.ind *.ps *.ilg  *.log *.tar.gz *.idx *.out *.toc  linalg-book.tex linalg-book-print.tex #linalg.tex gfdl.tex

all:	$(PDFWITHSRC) linalg-ebook.pdf linalg-book-print.pdf

help:
	@echo "Possible targets:"
	@echo " make     (default target, $(PDFWITHSRC) - formatted in small print, with hyperlinks)"
	@echo " make linalg-book.pdf            formatted for normal size, with hyperlinks"
	@echo " make linalg-book-print.pdf      formatted for normal size, without hyperlinks"
	@echo " make all                        make all pdf files"

