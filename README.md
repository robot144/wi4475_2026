# wi4475_2026
![TU Delft logo](https://raw.githubusercontent.com/robot144/wi4475_2026/main/images/tu_logo.png)

Homework series for data assimilation course WI4475 for 2026 at Delft University of Technology.
- please consult Brightspace for the deadlines and submission.
- This repository contains the homework assignments in several formats.
- The assignments are given as Jupyter notebooks. The code cells make use of the Julia programming language There is a brief introduction to both Julia and Markdown at the end of this README file, including installation instructions.
- I am aware that not all of you have seen Julia before. This shouldn't be a problem because the assignments are designed to be self-contained and to guide you through the necessary steps. However, if you encounter any issues or have questions, please don't hesitate to reach out for help. 
- If you really feel uncomfortable with Julia, you can also use Python. However, I do not have a Python version of the assignments ready, so you will need to translate the code yourself. Feel free to contact me if you want to go this route.

## First Homework series
  - [pdf version of homework1](https://raw.githubusercontent.com/robot144/wi4475_2026/main/wi4475_2026_homework1.pdf)
  - [html preview of homework 1](https://htmlpreview.github.io/?https://github.com/robot144/wi4475_2026/blob/main/wi4475_2026_homework1.html)
  - [Jupyter notebook version of homework 1](https://raw.githubusercontent.com/robot144/wi4475_2026/main/wi4475_2026_homework1.ipynb)

## Second Homework series
  - [pdf version of homework2](https://raw.githubusercontent.com/robot144/wi4475_2026/main/wi4475_2026_homework2.pdf)
  - [html preview of homework 2](https://htmlpreview.github.io/?https://github.com/robot144/wi4475_2026/blob/main/wi4475_2026_homework2.html)
  - [Jupyter notebook version of homework 2](https://raw.githubusercontent.com/robot144/wi4475_2026/main/wi4475_2026_homework2.ipynb)

## Installation instructions

### Step 1: Install Python
There are several ways to install Python. If you have python installed already on your system, then this is probably fine too. Some sources are:
- Official source [https://www.python.org/downloads/](https://www.python.org/downloads/)
- [Download Anaconda distribution](https://www.anaconda.com/download)

### Step 2: Install Jupyter
Jupyter notebooks are a friendly way to use python from a web-browser and document your steps with pieces of text in Markdown format. Markdown allows for simple layout of the text. You can look at this cheat sheet for the basics [https://www.markdownguide.org/cheat-sheet/](https://www.markdownguide.org/cheat-sheet/).
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
At [Download from main Julia page](https://julialang.org/downloads/) and follow the instructions for your operating system found there. The Julia command line is called the REPL. Try to start it. A message and prompt will appear if successful.

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

## Very very brief intro to Julia and Markdown

### Julia in one minute
The Julia syntax in a nutshell:
```julia
ratio = 2*π*x₀ #Greek symbols are allowed and are typed as \pi<TAB> and x\_0<TAB>
a=randn(2,100) #some random Gaussian points
scatter(a[1,:],a[2,:]) #make a scatter plot
for i in 1:1000
    a[:,i] = a[:,i]*ratio #note the dot before the *= operator, this makes the operation element-wise
    if norm(a[:,i])>10
        a[:,i] .= a[:,i]/norm(a[:,i]) #note the dot before the = operator, this makes the operation element-wise
    end
end
function myfunc(x)
    return sin(x) + cos(2x) #note the dots before the function calls, this makes the operation element-wise
end
x=-10:0.1:10 #make a vector from -10 to 10 with steps of 0.1
y=myfunc.(x) #evaluate myfunc for all values in x. The dot makes it element-wise, which is called broadcasting in Julia
plot(x, y) #plot the function myfunc from -10 to 10
my_array = [1 2 3; 4 5 6; 7 8 9] #make a 3x3 matrix
element_2_3 = my_array[2,3] #get the element in row 2, column 3; start counting at 1
my_array_squared = my_array*my_array #matrix multiplication
my_array_elementwise_squared = my_array . * my_array #element-wise multiplication
```

### Markdown in one minute
````markdown
# Header 1
## Header 2
### Header 3

Some useful markdown syntax:
short pice of `code`: `x = 2+2`
and a code block:

```julia
#julia comment
function f(x)
    return x^2
end
```


- **Bold text**: `**Bold text**`
- *Italic text*: `*Italic text*`
- [Links](https://example.com): `[Links](https://example.com)`
- Lists:
    - Item 1: `- Item 1`
    - Item 2: `- Item 2`
- Numbered lists:
    1. First item: `1. First item`
    2. Second item: `2. Second item`
- Equations:
    - Inline: `$E=mc^2$` → $E=mc^2$
    - Block: `$$E=mc^2$$` → $$E=mc^2$$
````
