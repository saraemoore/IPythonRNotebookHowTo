IPythonRNotebookHowTo
=====================

Intro & Motivation
---------------------
This repo contains three IPython notebooks, each representing a different way to run R code within an IPython notebook.  The intended audience is R users who have limited experience with Python, IPython, or IPython notebooks, but who would like to start using IPython notebooks for one reason or another.  There are a [handful][1] of [tutorials][2] [about][3] [this][4] available online, but none this tailored to interactive use, comprehensive, up-to-date (that I could find).  

[1]: http://nbviewer.ipython.org/github/ipython/ipython/blob/3607712653c66d63e0d7f13f073bde8c0f209ba8/docs/examples/notebooks/rmagic_extension.ipynb "IPython Rmagic Functions Extension example notebook"
[2]: http://www.randalolson.com/2013/01/14/filling-in-pythons-gaps-in-statistics-packages-with-rmagic/ "Randy Olson's Rmagic + IPython intro]"
[3]: http://nbviewer.ipython.org/gist/yoavram/5280132 "Yoav Ram's Example of using ggplot2 from IPython notebook"
[4]: https://climateecology.wordpress.com/2014/01/20/ggplot2-in-python-a-major-barrier-broken/ "ggplot2 in Python"

Setup
---------------------
1.  Install a Python distribution that includes IPython, aka Interactive Python, or update your current distribution.  Two distributions that will work are [Enthought Canopy](https://www.enthought.com/products/canopy/) and [Anaconda](https://store.continuum.io/cshop/anaconda/). As [Randy Olson points out](http://www.randalolson.com/2012/05/12/a-short-demo-on-how-to-use-ipython-notebook-as-a-research-notebook/), Enthought Canopy offers [free academic licenses](https://store.enthought.com/#canopy-academic) to students and staff of degree-granting institutions.  Anaconda is also free.
2.  Update IPython.  Details on doing this under both distributions above are provided on [IPython's installation page](http://ipython.org/install.html).
3.  Install or update [R](http://www.r-project.org/). If your R installation is only slightly out of date, you should be ok, but just note that an update may be necessary to allow everything to play nicely together.
4.  Necessary for two of the three strategies in this guide: install or upgrade [Python module `rpy2`](http://rpy.sourceforge.net/rpy2.html).  The easiest way to do this is to use Python module `easy_install`. Here's an example of what installation would look like on Mac OS/Linux:
```
    sudo easy_install rpy2
```
  and update on Mac OS/Linux:
```
    sudo easy_install --upgrade rpy2
```
  If you're having trouble with this step, you might want to check your Python installation or try installing manually (by downloading the module's source, unpacking it, and running `sudo python setup.py install` in the unpacked directory).

5.  May be necessary if your Python distribution is earlier than 3.4 (true of Canopy and potentially true of Anaconda): install Python module `singledispatch`.  The installation and upgrade for this on Mac OS/Linux are analogous to the above. Install:
```
sudo easy_install singledispatch
```
and update:
```
sudo easy_install --upgrade singledispatch
```

Use
---------------------
As stated above, there are three notebooks in this repo, each detailing a different approach to running R code interactively in an IPython notebook.  The rendered notebooks can be viewed in a browser via nbviewer:
*  the [Rmagic approach](http://nbviewer.ipython.org/github/saraemoore/IPythonRNotebookHowTo/blob/master/RmagicExample.ipynb), which retains the ability to run other types of code in the same notebook,
*  the ["fake R kernel" approach](http://nbviewer.ipython.org/github/saraemoore/IPythonRNotebookHowTo/blob/master/fakeRkernelExample.ipynb), which does not require the user to know or use any other language and has a simple setup procedure, and
*  the ["real R kernel" approach](http://nbviewer.ipython.org/github/saraemoore/IPythonRNotebookHowTo/blob/master/realRkernelExample.ipynb), which also does not require the user to use any language other than R. This approach is somewhat experimental and has a slightly more complex setup procedure, but no code is funneled through Python with this setup, yielding a "purer" (and probably faster) R experience.
After setup (above) is complete, the notebooks in this repo can be downloaded, with each run locally under the IPython invocation described in its own introduction (the invocation, such as `ipython notebook`, should be run from the command line *within the directory that contains the notebooks*). Rerun each code block in a given notebook to confirm that your setup for that approach is working (see [running code in IPython notebooks](http://nbviewer.ipython.org/github/ipython/ipython/blob/1.x/examples/notebooks/Part%201%20-%20Running%20Code.ipynb)).
