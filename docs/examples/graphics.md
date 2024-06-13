# Views and custom graphics

First, we'll use the listvisu() command to find out which views are available.

```
pycoa.listvisu()
```

Types of display available in Pycoa :

Since its last update Pycoa offers several options for visualising data using different visualisation libraries.

- `pycoa.setvisu(vis=‘name_visu’)`: Allows you to select the type of visualisation you prefer.
    - `bokeh'` (default): for interactive and dynamic visualisations with Bokeh
    - `folium'`: Used only for maps working with bokeh
    - `seaborn'`: for statistical visualisations with Seaborn
    - `mplt'`: for classic visualisations with Matplotlib

Example with Seaborn

```
pycoa.setvisu(vis=‘seaborn’)
pycoa.plot()
pycoa.hist()
pycoa.hist(typeofhist=‘byvalue’)
pycoa.hist(typeofhist=‘pie’)
pycoa.map()
```

This heatmap shows the number of hospital deaths in France by month and by year. It's a great way to compare different years and see when the epidemic was at its worst.

## Graph customisation options

As well as choosing the type of display, Pycoa also allows you to customise various aspects of the graphs. Customisation options include :

- `mode`: displays information about hovered curves
    - `mouse`' (default)
    - `hline`' horizontal line
    - `vline`' vertical line
- `title`: chart title
- `textcopyright`: name attached to copyright ⓒ pycoa.fr
- `plot_width`: plot width (default plot_width=500)
- `plot_height`: plot height (default plot_height=380)

```
pycoa.setvisu(vis=‘bokeh’, mode=‘hline’, plot_width=600, plot_height=400, title=‘My graph’, textcopyright = ‘@myname’)
```
 