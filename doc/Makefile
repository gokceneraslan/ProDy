# Makefile for Sphinx documentation
#

# You can set these variables from the command line.
SPHINXOPTS    =
SPHINXBUILD   = sphinx-build
PAPER         =
BUILDDIR      = _build
DOCTESTDIR    = doctest
DOCDIR        = ../Documentation

# Internal variables.
PAPEROPT_a4     = -D latex_paper_size=a4
PAPEROPT_letter = -D latex_paper_size=letter
ALLSPHINXOPTS   = -d ../$(BUILDDIR)/doctrees $(PAPEROPT_$(PAPER)) $(SPHINXOPTS) ..

.PHONY: help clean stats both html dirhtml singlehtml pickle json htmlhelp qthelp devhelp epub latex latexpdf text man changes linkcheck doctest testdist copytxt 

help:
	@echo "Please use \`make <target>' where <target> is one of"
	@echo "  html       to make standalone HTML files"
	@echo "  dirhtml    to make HTML files named index.html in directories"
	@echo "  singlehtml to make a single large HTML file"
	@echo "  pickle     to make pickle files"
	@echo "  json       to make JSON files"
	@echo "  htmlhelp   to make HTML files and a HTML help project"
	@echo "  qthelp     to make HTML files and a qthelp project"
	@echo "  devhelp    to make HTML files and a Devhelp project"
	@echo "  epub       to make an epub"
	@echo "  latex      to make LaTeX files, you can set PAPER=a4 or PAPER=letter"
	@echo "  latexpdf   to make LaTeX files and run them through pdflatex"
	@echo "  text       to make text files"
	@echo "  man        to make manual pages"
	@echo "  changes    to make an overview of all changed/added/deprecated items"
	@echo "  linkcheck  to check all external links for integrity"
	@echo "  doctest    to run all doctests embedded in the documentation (if enabled)"

clean:
	-rm -rf $(DOCDIR)/*
	# -rm -rf $(BUILDDIR)/* $(DOCDIR)/*

stats:
	pyps update -s ProDy_stats.pkl ProDy; \
	pyps latest -o _static/ProDy_downloads.csv -d , --rst ProDy; \
	pyps monthly -p _static/ProDy_downloads.png ProDy_stats.pkl

both:
	cd $(DOCTESTDIR); \
	$(SPHINXBUILD) -b html -d ../$(BUILDDIR)/doctrees .. ../$(DOCDIR); \
	cd ..
	@echo
	@echo "Build finished. The HTML pages are in $(DOCUMENTATION)."
	cd $(DOCTESTDIR); \
	$(SPHINXBUILD) -b latex $(ALLSPHINXOPTS) ../$(BUILDDIR)/latex .. ../$(DOCDIR); \
	cd ..
	@echo "Running LaTeX files through pdflatex..."
	make -C $(BUILDDIR)/latex all-pdf
	mv -f $(BUILDDIR)/latex/ProDy.pdf ../Documentation
	@echo "pdflatex finished; the PDF files are in $(BUILDDIR)/../../."

html:
	cd $(DOCTESTDIR); \
	$(SPHINXBUILD) -b html -d ../$(BUILDDIR)/doctrees .. ../$(DOCDIR); \
	cd ..
	@echo
	@echo "Build finished. The HTML pages are in $(DOCUMENTATION)."
	
spelling:
	$(SPHINXBUILD) -b spelling $(ALLSPHINXOPTS) $(BUILDDIR)/spelling

dirhtml:
	$(SPHINXBUILD) -b dirhtml $(ALLSPHINXOPTS) $(BUILDDIR)/dirhtml
	@echo
	@echo "Build finished. The HTML pages are in $(BUILDDIR)/dirhtml."

singlehtml:
	$(SPHINXBUILD) -b singlehtml $(ALLSPHINXOPTS) $(BUILDDIR)/singlehtml
	@echo
	@echo "Build finished. The HTML page is in $(BUILDDIR)/singlehtml."

pickle:
	$(SPHINXBUILD) -b pickle $(ALLSPHINXOPTS) $(BUILDDIR)/pickle
	@echo
	@echo "Build finished; now you can process the pickle files."

json:
	$(SPHINXBUILD) -b json $(ALLSPHINXOPTS) $(BUILDDIR)/json
	@echo
	@echo "Build finished; now you can process the JSON files."

htmlhelp:
	$(SPHINXBUILD) -b htmlhelp $(ALLSPHINXOPTS) $(BUILDDIR)/htmlhelp
	@echo
	@echo "Build finished; now you can run HTML Help Workshop with the" \
	      ".hhp project file in $(BUILDDIR)/htmlhelp."

qthelp:
	$(SPHINXBUILD) -b qthelp $(ALLSPHINXOPTS) $(BUILDDIR)/qthelp
	@echo
	@echo "Build finished; now you can run "qcollectiongenerator" with the" \
	      ".qhcp project file in $(BUILDDIR)/qthelp, like this:"
	@echo "# qcollectiongenerator $(BUILDDIR)/qthelp/ProDy.qhcp"
	@echo "To view the help file:"
	@echo "# assistant -collectionFile $(BUILDDIR)/qthelp/ProDy.qhc"

devhelp:
	$(SPHINXBUILD) -b devhelp $(ALLSPHINXOPTS) $(BUILDDIR)/devhelp
	@echo
	@echo "Build finished."
	@echo "To view the help file:"
	@echo "# mkdir -p $$HOME/.local/share/devhelp/ProDy"
	@echo "# ln -s $(BUILDDIR)/devhelp $$HOME/.local/share/devhelp/ProDy"
	@echo "# devhelp"

epub:
	$(SPHINXBUILD) -b epub $(ALLSPHINXOPTS) $(BUILDDIR)/epub
	@echo
	@echo "Build finished. The epub file is in $(BUILDDIR)/epub."

latex:
	$(SPHINXBUILD) -b latex $(ALLSPHINXOPTS) $(BUILDDIR)/latex
	@echo
	@echo "Build finished; the LaTeX files are in $(BUILDDIR)/latex."
	@echo "Run \`make' in that directory to run these through (pdf)latex" \
	      "(use \`make latexpdf' here to do that automatically)."

latexpdf:
	cd $(DOCTESTDIR); \
	$(SPHINXBUILD) -b latex $(ALLSPHINXOPTS) ../$(BUILDDIR)/latex; \
	cd ..
	@echo "Running LaTeX files through pdflatex..."
	make -C $(BUILDDIR)/latex all-pdf
	mv -f $(BUILDDIR)/latex/ProDy.pdf ../Documentation
	@echo "pdflatex finished; the PDF files are in $(BUILDDIR)/../../."

text:
	$(SPHINXBUILD) -b text $(ALLSPHINXOPTS) $(BUILDDIR)/text
	@echo
	@echo "Build finished. The text files are in $(BUILDDIR)/text."

man:
	$(SPHINXBUILD) -b man $(ALLSPHINXOPTS) $(BUILDDIR)/man
	@echo
	@echo "Build finished. The manual pages are in $(BUILDDIR)/man."

changes:
	$(SPHINXBUILD) -b changes $(ALLSPHINXOPTS) $(BUILDDIR)/changes
	@echo
	@echo "The overview file is in $(BUILDDIR)/changes."

linkcheck:
	$(SPHINXBUILD) -b linkcheck $(ALLSPHINXOPTS) $(BUILDDIR)/linkcheck
	@echo
	@echo "Link check complete; look for any errors in the above output " \
	      "or in $(BUILDDIR)/linkcheck/output.txt."

doctest:
	cd $(DOCTESTDIR); \
	$(SPHINXBUILD) -b doctest -d ../$(BUILDDIR)/doctrees/ .. ..; \
	cd ..
	@echo "Testing of doctests in the sources finished, look at the " \
	      "results in $(DOCTEST)."
	      
testdist:
	mv ../prody ../prody_
	cd $(DOCTESTDIR); \
	$(SPHINXBUILD) -b doctest -d ../$(BUILDDIR)/doctrees/ .. ..; \
	cd ..
	@echo "Testing of doctests in the sources finished, look at the " \
	      "results in $(DOCTEST)."
	mv ../prody_ ../prody

copytxt:
	cp -f changes.rst ../CHANGES.rst
	cp -f getprody.rst ../INSTALL.rst
	cp -f license.rst ../LICENSE.rst
