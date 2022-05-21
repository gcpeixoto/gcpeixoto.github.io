---
title: G-β - Python & Jupyter
---

### How to install packages from the Jupyter Notebook safely

  - `pip` installs in any environment
  - `conda` installs conda environments
  - **the shell environment and the Python executables are disconnected**
  - Anaconda pre-install assumed below.
{% highlight python %} 
import sys
!conda install --yes --prefix {sys.prefix} <package>
{% endhighlight %} 

See further discussion [here](https://jakevdp.github.io/blog/2017/12/05/installing-python-packages-from-jupyter/).

### How to enable Python debugger capabilities in Jupyter 

  - Install the kernel `xeus-python` (new conda env or base env)
  - (It works fine with new fresh conda-env create/activate workflow)
  - Install debugger extension
{% highlight python %} 
conda install xeus-python notebook -c conda-forge
jupyter labextension install @jupyterlab/debugger
{% endhighlight %} 

See further discussion [here](https://github.com/jupyterlab/debugger) and [here](https://github.com/jupyter-xeus/xeus-python).

### Learning resources

- [Teaching and Learning with Jupyter](https://jupyter4edu.github.io/jupyter-edu-book/)
	- A reference e-book to all who use Jupyter for lecturing.

- [Lorena Barba's group](https://lorenabarba.com)
	- Open-source code-sharing innitiative and very cool Jupyter notebooks for CFD.

### Journals

- [Journal of Open Source Software](https://joss.theoj.org)
	- Journal that is bursting on open source, counting with renowned people involved with machine learning, data science, and torrents of projects using Jupyter NBs.

### Autograding 

- Autograding tools for testing Jupyter or making assignments easier to handle
	- [nbgrader](https://nbgrader.readthedocs.io/en/stable/) by Jupyter team.
	- [autograde](https://github.com/cssh-rwth/autograde)
	- [Otter-Grader](https://otter-grader.readthedocs.io/en/stable/) @Berkeley
	- Interesting [report](https://infovis.cs.vt.edu/sites/default/files/Auto_Grading_Jupyter_Notebooks.pdf) talking about graders and the alternative _Web Cat_.
	- Security failure in nbgrader is alleged and a solution is proposed by the Finnish SciComp group Aalto [here](https://scicomp.aalto.fi/aalto/jupyterhub-instructors/autograding/).  
	- This [video](https://youtu.be/__yUvsV1xsU) shows nicely how to use grader with Github Classroom and accompanies this [handout](https://github.com/jkuruzovich/otter_helper). 

### Lecturing with RISE

- Notes on [RISE](https://rise.readthedocs.io/en/stable/installation.html) Slideshow troubleshooting:
	- RISE stopped working correctly on Safari with Big Sur 11.2.3 suddenly. 
	- Go to fix...
	- With version 5.7.1, I had an issue with
	{% highlight bash %} 
	pkg_resources.ContextualVersionConflict: 
	(jedi 0.15.2 ... Requirement.parse('jedi>=0.16'), {'ipython'})
	{% endhighlight %}
- With `conda update jedi; conda list jedi`, the version was not being upgraded to 0.18 (available on PyPi);
- Worked only with `conda update -c conda-forge jedi=0.17.2` after a long wait on "frozen/flexible solve... solving environment...";
- Then, launching Jupyter on Safari, the `Cell Toolbar > Slideshow` could be visible, but the button to launch RISE Slideshow was not showing up.
	- Current solution: use Chrome.		

- How to customize RISE's chalkboard and themes
	- List of available themes [here](https://revealjs.com/themes/).
	- From version 5.7.1, colors are customizable for chalkboard.
	- Options can be found in the [reveal.js-plugins/chalkboard README](https://github.com/rajgoel/reveal.js-plugins/tree/master/chalkboard)
	- Here is an example on how to change chalkboard options:	
{% highlight json %} 
"rise": {
  "chalkboard": {
      "boardmarkerWidth": 3,      
      "grid": {
        "color": "rgb(50,50,10,0.5)",
        "distance": 80,
        "width": 2
      }
    },
 }
{% endhighlight %} 		

### How to edit the font color of a postscripted PDF 

- I will report a pathway although I have not gotten to a final solution yet:
- Stefano Chizzolini, [PDFClown](https://sourceforge.net/projects/clown/)'s developer proposed a code in this [post](https://sourceforge.net/p/clown/discussion/607163/thread/bc191071/). At the current version, however, PDFClown possibly has embedded all those isolated Java elements.
- The idea would be try to follow SC's approach.
- Secondly, [PyPDF2](https://pypi.org/project/PyPDF2/) might be a Python alternative. There is a tutorial [here](https://realpython.com/creating-modifying-pdf/#setting-font-properties), but font color changes seems to be a hard stuff.
	- Why I wanted that? Modify color of latexized PDF text from black to CMY-balanced (after K=0) color to fill out CMY printer cartridges.
	- Let us leave that for future... 

### Python 'gotchas'

- [Python "gotchas"](https://mrfuxi.github.io/blog/python-gotchas/) are weird things that may happen with Python coding.

### Encoding/decoding characters

- To print symbols for musical notes it is necessary to have a font in the computer capable to represent the Unicode. See [here](https://stackoverflow.com/questions/48055887/python-how-to-specify-and-view-high-numbered-unicode-characters).
- The Unicode table for music is [here](https://unicode.org/charts/PDF/U1D100.pdf).
- So, to print the G clef, we'd use `print('\U0001D120')`, with Unicode `\U` escape. Seemingly, there are few font types that handle music symbols. One available is [Bravura](https://github.com/steinbergmedia/bravura).

### Set browser for Jupyter-Lab

- To choose a different browser from the computer's default where to run Jupyter-Lab, run `jupyter server --generate-config` and edit the option `c.ServerApp.browser` in  `$HOME/.jupyter/jupyter_server_config.py`
{% highlight python %} 
 #  Default: ''
import webbrowser
c.ServerApp.browser = 'chrome'
{% endhighlight %} 		
- The module `webbrowser` allows us to choose among many known browsers. See table [here](https://docs.python.org/3/library/webbrowser.html#webbrowser.get).
- For further detail, see this [discussion](https://github.com/jupyterlab/jupyterlab/issues/9565).

### PDF parsing

- [pdfminer.six](https://github.com/pdfminer/pdfminer.six). Install with `pip install pdfminer.six` and run with `pdf2txt.py file.pdf` (install adds to PATH).


### DataViz Tools

- [PyViz](https://pyviz.org/tools.html): overview of data visualization Python ecosystem.
- [Holoviz](https://holoviz.org/index.html): modern project that integrates many tools.
- [From Data to Viz](https://www.data-to-viz.com): where design meets data science. Amazing holistic view.


### CSV to MD conversion 

- Use [MDTable](https://github.com/mzjp2/mdtable): very cool options
- {% highlight python %} 
from mdtable import MDTable 
MDTable('input.csv').save_table('output.csv')
{% endhighlight %} 