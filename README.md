# wi4475_2026
![TU Delft logo](https://raw.githubusercontent.com/robot144/wi4475_2026/main/images/tu_logo.png)

Homework series for data assimilation course WI4475 for 2026 at Delft University of Technology.

## First Homework series
  - [pdf version of homework1](https://raw.githubusercontent.com/robot144/wi4475_2026/main/wi4475_2026_homework1.pdf)
  - [html preview of homework 1](https://robot144.github.io/wi4475_2026/wi4475_2026_homework1.html)
  - [Jupyter notebook version of homework 1](https://raw.githubusercontent.com/robot144/wi4475_2026/main/wi4475_2026_homework1.ipynb)

## Second Homework series
_Not yet available_

## Installation instructions

### Step 1: Install Python
There are several ways to install Python. If you have python installed already on your system, then this is probably fine too. Some sources are:
- Official source [[|https://www.python.org/downloads/]]
- [[Anaconda distribution|https://www.anaconda.com/download]]

### Step 2: Install Jupyter
Jupyter notebooks are a friendly way to use python from a web-browser and document your steps with pieces of text in Markdown format. Markdown allows for simple layout of the text. You can look at this cheat sheet for the basics [[https://www.markdownguide.org/cheat-sheet/]]
For mathematicians the latex formula support is especially useful. For example
```Markdown
For $x \in [0,L]$ we have
$$y(x)=sin(2 \pi x/L)$$
```
Jupyter is most easily installed as a package of python, this is often `conda install jupyter` for Anaconda and friends and `pip install jupyter` for others. Check in python:
```python
import jupyter
```
You'll get an error message if the installation wasn't successful yet. You can start the Jupyter server from start menu of your system or using 
```bash,cmd
jupyter notebook
```
### Step 3: Install Julia
At [[Download from main Julia pagehttps://julialang.org/downloads/]] and follow the instructions for your operating system found there. The Julia command line is called the REPL. Try to start it. A message and prompt will appear if successful.

### Step 4: Install IJulia
IJulia is the Julia package that can connect Jupyter to Julia. You can install it on the prompt of Julia:
```julia
using Pkg
Pkg.add("IJulia")
```
### Step 5: Select a Julia kernel
Now you should be able to use Julia within a Jupyter notebook. To test this, open a new Jupyter notebook and go to select kernel and select Julia. If Julia doesn't appear as an option then open the Julia REPL and try:
```julia
using IJulia
IJulia.installkernel()
```
Then restart Jupyter and try again.

Now you should be able to use Julia in a Jupyter notebook. Note that there are many alternatives, too many to list them all. However, it is usually straightforward to make this work on any system. My personal favorite is a combination of vscode with plugins for Jupyter and Julia, but other may have other preferences and this is definitely not necessary here.