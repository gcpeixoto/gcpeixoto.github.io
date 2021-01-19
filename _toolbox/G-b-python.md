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
