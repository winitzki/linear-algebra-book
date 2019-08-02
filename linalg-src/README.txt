		README for the source distribution of "Linear algebra via exterior products"
		 by Sergei Winitzki

The text is distributed under GNU Free Documentation License. This license permits you to copy
the entire text, to make changes, and to distribute either original or modified versions, as
long as you distribute them under the same license and with full human-editable source.

	Obtaining the source files

The source is given as a set of LaTeX and other files. The main document is linalg.lyx, which is
a document for the LyX editor. The LaTeX files are generated from the LyX files. Finally, a PDF
file is generated, and the complete source package is attached to the PDF file as a tar.gz file
attachment (i.e. inside the PDF file). You can extract the attachment, for example, in Adobe
Acrobat Reader by clicking on the attachment icon and selecting "Save". Alternatively, you can
use the free "pdftk" program to extract the attachment using a command such as

pdftk "Linear_algebra_exterior.pdf" unpack_files output ~/temp/

This command will extract the file "linalg.tar.gz" into the directory ~/temp/ 

Then you need to unpack the source files:

tar zxf linalg.tar.gz

	Compiling from source

If you make changes to the document, e.g. to reformat the pages, you need to recompile from
the source.

A Makefile is provided, so all you need to do is to type "make" and have a working installed
LaTeX, Ghostscript, and pdftk. 

The result is first, the file "linalg.pdf" containing the text, then "linalg.tar.gz"
containing the updated source, and finally the file "Linear_algebra_exterior.pdf" containing
the text and the source embedded as attachment. You should then distribute this last file.

Without the Makefile, the full compilation procedure can be performed using the commands:

latex linalg.tex
latex linalg.tex
makeindex linalg.idx
latex linalg.tex
latex linalg.tex
dvips linalg.dvi
ps2pdf linalg.ps
tar zcvf linalg.tar.gz linalg.lyx linalg.tex v1v2-vol.fig v1v2-vol.eps Makefile gfdl.lyx gfdl.tex README.txt
pdftk linalg.pdf attach_files linalg.tar.gz output Linear_algebra_exterior.pdf


