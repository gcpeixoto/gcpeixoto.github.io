---
title: G-β - Python & Jupyter
---

- How to install packages from the Jupyter Notebook safely

  - `pip` installs in any environment
  - `conda` installs conda environments
  - **the shell environment and the Python executables are disconnected**
  - Anaconda pre-install assumed below.
{% highlight python %} 
import sys
!conda install --yes --prefix {sys.prefix} <package>
{% endhighlight %} 

See further discussion [here](https://jakevdp.github.io/blog/2017/12/05/installing-python-packages-from-jupyter/).

- How to enable Python debugger capabilities in Jupyter 

  - Install the kernel `xeus-python` (new conda env or base env)
  - (It works fine with new fresh conda-env create/activate workflow)
  - Install debugger extension
{% highlight python %} 
conda install xeus-python notebook -c conda-forge
jupyter labextension install @jupyterlab/debugger
{% endhighlight %} 

See further discussion [here](https://github.com/jupyterlab/debugger) and [here](https://github.com/jupyter-xeus/xeus-python).

- [Teaching and Learning with Jupyter](https://jupyter4edu.github.io/jupyter-edu-book/)
	- A reference e-book to all who use Jupyter for lecturing.

- [Lorena Barba's group](https://lorenabarba.com)
	- Open-source code-sharing innitiative and very cool Jupyter notebooks for CFD.

- [Journal of Open Source Software](https://joss.theoj.org)
	- Journal that is bursting on open source, counting with renowned people involved with machine learning, data science, and torrents of projects using Jupyter NBs.

- Autograding tools for testing Jupyter or making assignments easier to handle
	- [nbgrader](https://nbgrader.readthedocs.io/en/stable/) by Jupyter team.
	- [autograde](https://github.com/cssh-rwth/autograde)
	- [Otter-Grader](https://otter-grader.readthedocs.io/en/stable/) @Berkeley
	- Interesting [report](https://infovis.cs.vt.edu/sites/default/files/Auto_Grading_Jupyter_Notebooks.pdf) talking about graders and the alternative _Web Cat_.
	- Security failure in nbgrader is alleged and a solution is proposed by the Finnish SciComp group Aalto [here](https://scicomp.aalto.fi/aalto/jupyterhub-instructors/autograding/).  
	- This [video](https://youtu.be/__yUvsV1xsU) shows nicely how to use grader with Github Classroom and accompanies this [handout](https://github.com/jkuruzovich/otter_helper). 