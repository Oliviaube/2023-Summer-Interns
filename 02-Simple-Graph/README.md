# Simple Graph

This project will get us started and make some room for experimetation with graphing using python libraries. The goal is to make a simple template for plotting an arbitrary fuction over some range. 

The following should be user inputs:
- a function to plot
- the range over which to plot it
- labels for the graph, x-axis and y-axis

There are several graphing libraries available for python, I like the looks of [plotly](https://plotly.com/python/) for adding interactivity down the line.

## Installation
1. In a **JupyterLab Terminal window**- `conda install -c conda-forge -c plotly jupyter-dash`
1. Restart Jupyterlab

## Example: plotly.ipynb
Examine the example code in the *plotly* notebook to solve some of the objectives.

## Common API Usage
Use `fig = px.line` to create a new *line* graph then use `fig.show()` to display it.
```python
import plotly.express as px
fig = px.line(
    x=x,
    x=y,
    xaxis_title='xaxis',
    yaxis_title='yaxis',
)

fig.show()
```
To continue to use the same graph, however, update some aspects of the graph, use `fig.update_layout()` followed by `fig.show()`.
```python
fig = px.update_layout(
    title='Title For the Plot',
    width=width_in_pixels,
    height=height_in_pixels
)
fig.show()
```
