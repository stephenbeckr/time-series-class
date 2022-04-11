# Homeworks for MATH/STAT 4540/5540 Intro to Time Series

- [Homework 1](MATHSTAT4540_Spr22_HW1.pdf) due Fri Jan 28 before midnight on Canvas/Gradescope. 
  - If you use latex (not required), there is a source code file on Canvas which can save you some time of retyping questions.
- [Homework 2](MATHSTAT4540_Spr22_HW2.pdf) due Fri Feb 11 before midnight on Canvas/Gradescope. 
- [Homework 3](MATHSTAT4540_Spr22_HW3.pdf) due Fri Mar 4 before midnight on Canvas/Gradescope.  This homework should be nicely formatted.
- [Homework 4](MATHSTAT4540_Spr22_HW4.pdf) due Sun Mar 20 before midnight on Canvas/Gradescope.  This homework should be nicely formatted.
- [Final Project](MATHSTAT4540_Spr22_Project.pdf) due Saturday April 30th before 7 PM on Canvas/Gradescope.



## FAQ

### General

**Gradescope** has a [submission guide](https://gradescope-static-assets.s3.amazonaws.com/help/submitting_hw_guide.pdf) that recommends software for your phone to take pictures of written homework and convert it to a PDF (your final submission to Gradescope must be a PDF).

Note: the links in the PDFs will not work if you view the PDF on github, but if you open the PDF in its own tab, or download it, all the links should work.

**Collaboration**: Collaboration with your fellow students is OK and in fact recommended, although direct copying is not allowed.  Please write down the names of the students that you worked with.

**Internet**: The internet is allowed for basic tasks (e.g., looking up definitions on wikipedia) but it is
not permissible to search for proofs or to post requests for help on forums such as [math.stackexchange.com](http://math.stackexchange.com/)
or to look at solution manuals

#### Merging multiple PDF files

**Mac** You can use the Preview software that comes with Mac, and drag-and-drop in the Thumbnail view, or follow these [instructions](https://support.apple.com/en-us/HT202945).

**Linux** install `pdftk` (e.g., `apt-get install pdftk`), and the on the command line, it's just `pdftk inputFile1.pdf inputFile2.pdf cat output outputFileName.pdf`.  This works on Mac and Windows too (on Mac, the exact command line works; on Windows, I'm not sure).

**Windows** there are [lists of free web- and desktop-based software](https://superuser.com/a/34294), including [i-love-pdf](https://www.ilovepdf.com/merge_pdf), but [PDFtk](https://www.pdflabs.com/tools/pdftk-the-pdf-toolkit/) is one of the most classic and respected (no viruses). I haven't used PDFtk on Windows, but the website claims they have a GUI; or if you don't like their GUI, try a [3rd party GUI that uses PDFtk](https://www.pdflabs.com/tools/pdftk-the-pdf-toolkit/).


#### Jupyter

Tips for exporting jupyter notebook code to a PDF:

- You can try this [Notebook to PDF conversion website](https://htmtopdf.herokuapp.com/ipynbviewer/) that some of our students have had good luck with

- Or try `nbconvert` which requires [`pandoc`](https://pandoc.org/installing.html). You can do this on [Colab](https://colab.research.google.com/), following the [instructions here](https://stackoverflow.com/a/54191922) (but note that you may need to add a backslash before any white space when you run commands, e.g., change a command like

`!cp drive/My Drive/Colab Notebooks/Untitled.ipynb ./`
to
``!cp drive/My\ Drive/Colab\ Notebooks/Untitled.ipynb ./``
)

Note that if you include latex in the jupyter notebook, when you run `nbconvert`, you cannot have any whitespace near the `\$` symbols for math due to a requirement of `pandoc` (see [here](https://pandoc.org/MANUAL.html#extension-tex_math_dollars)).  So, ``$ f(x) = 3x^2 $`` will not work, but `$f(x) = 3x^2$` will be OK.

The downside of `nbconvert` is that images are saved as png, not pdf, so fonts don't come through, but that's not a big deal for homework.

If you run jupyter locally, you might be able to run `nbconvert` without using the command line; go to "Download" the "PDF via LaTeX".

#### Rstudio
You can use R markdown or R notebooks as nice ways to present your HW, including text, math, code and plots.  From the notebook, export it to a PDF (or print it and choose PDF as the destination).

#### R source code (not Jupyter)
The *non-preferred* ways are (1) screenshot of your editor (not so nice since it's an image not text, but at least you get syntax color highlighting), and (2) export from a text editor to PDF (not so nice if you don't get syntax color highlighting).

It's not nice to the graders to submit code without syntax color highlighting!

Better ways: it depends on your system and editor, but there are many ways. For example, tailored to Python but probably applicable to R as well, this [stackoverflow 'printing python code to PDF'](https://stackoverflow.com/q/20412038) offers several suggestions. For example, since I already use `vim` and its setup with syntax highlighting, I can do [this answer](https://stackoverflow.com/a/20412421) and do `vim abc.py -c ":hardcopy > abc.ps" -c ":q"` followed by `ps2pdf abc.ps abc.pdf` -- no extra software needed!


