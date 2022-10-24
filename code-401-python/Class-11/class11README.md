## Matplotlib tutorial

### Introduction

_*matplotlib is probably the single most used Python package for 2D-graphics. It provides both a very quick way to visualize data from Python and publication-quality 
figures in many formats. We are going to explore matplotlib in interactive mode covering most common cases.*_

### Simple plot

Draw the cosine and sine functions on the same plot. Starting from the default settings, we'll enrich the figure step by step to make it nicer:

firstly ,get the data for the sine and cosine functions:

import numpy as np
X = np.linspace(-np.pi, np.pi, 256, endpoint=True)
C, S = np.cos(X), np.sin(X)

#### Using defaults

Matplotlib comes with a set of default settings that allow customizing all kinds of properties. You can control the defaults of almost every property in matplotlib:
figure size and dpi, line width, color and style, axes, axis and grid properties, text and font properties and so on. While matplotlib defaults are rather good in
most cases, you may want to modify some properties for specific cases.

#### Instantiating defaults

we've instantiated (and commented) all the figure settings that influence the appearance of the plot. The settings have been explicitly set to their default values,
but now you can interactively play with the values to explore their affect
 

1.*Changing colors and line widths*  like (plt.plot(X, C, color="blue", linewidth=2.5, linestyle="-"))

2.*Setting limits*  like (plt.xlim(X.min()*1.1, X.max()*1.1))

3.*Setting ticks*  like (plt.xticks( [-np.pi, -np.pi/2, 0, np.pi/2, np.pi]))

4.*Setting tick labels*  like (plt.xticks([-np.pi, -np.pi/2, 0, np.pi/2, np.pi],
       [r'$-\pi$', r'$-\pi/2$', r'$0$', r'$+\pi/2$', r'$+\pi$']))
       
5.*Moving spines*  like (ax.spines['bottom'].set_position(('data',0)))

6.*Adding a legend*  like (plt.plot(X, S, color="red",  linewidth=2.5, linestyle="-", label="sine"))

7.*Annotate some points* like (plt.annotate(r'$\sin(\frac{2\pi}{3})=\frac{\sqrt{3}}{2}$',
             xy=(t, np.sin(t)), xycoords='data',
             xytext=(+10, +30), textcoords='offset points', fontsize=16,
             arrowprops=dict(arrowstyle="->", connectionstyle="arc3,rad=.2")))
8.*Devil is in the details*  like (for label in ax.get_xticklabels() + ax.get_yticklabels():
    label.set_fontsize(16)
    label.set_bbox(dict(facecolor='white', edgecolor='None', alpha=0.65 )))
    

![image] (https://github.com/rougier/matplotlib-tutorial/raw/master/figures/exercice_10.png)




 
### Figures, Subplots, Axes and Ticks

#### Figures 

A figure is the windows in the GUI that has "Figure #" as title. Figures are numbered starting from 1 as opposed to the normal Python way starting from 0.
This is clearly MATLAB-style. There are several parameters that determine what the figure looks

#### Subplots

With subplot you can arrange plots in a regular grid. You need to specify the number of rows and columns and the number of the plot. Note that the gridspec
command is a more powerful alternative.

#### Axes 

Axes are very similar to subplots but allow placement of plots at any location in the figure. So if we want to put a smaller plot inside a bigger one
we do so with axes.

#### Ticks

Well formatted ticks are an important part of publishing-ready figures. Matplotlib provides a totally configurable system for ticks. There are tick locators
to specify where ticks should appear and tick formatters to give ticks the appearance you want. Major and minor ticks can be located and formatted independently
from each other. By default minor ticks are not shown


### Animation

For quite a long time, animation in matplotlib was not an easy task and was done mainly through clever hacks. However, things have started to change since
version 1.1 and the introduction of tools for creating animation very intuitively, with the possibility to save them in all kind of formats (but don't expect to be
able to run very complex animations at 60 fps though).

#### Drip drop

A very simple rain effect can be obtained by having small growing rings randomly positioned over a figure. Of course, they won't grow forever since the wave is 
supposed to damp with time. To simulate that, we can use a more and more transparent color as the ring is growing, up to the point where it is no more visible. 
At this point, we remove the ring and create a new one.


![image](https://github.com/rougier/matplotlib-tutorial/raw/master/figures/rain-static.png)

#### Earthquakes

The USGS Earthquake Hazards Program is part of the National Earthquake Hazards Reduction Program (NEHRP) and provides several data on their website. Those data are
sorted according to earthquakes magnitude, ranging from significant only down to all earthquakes, major or minor. You would be surprised by the number of minor 
earthquakes happening every hour on the planet. Since this would represent too much data for us, we'll stick to earthquakes with magnitude > 4.5. At the time of 
writing, this already represent more than 300 earthquakes in the last 30 days.

![image](https://github.com/rougier/matplotlib-tutorial/raw/master/figures/earthquakes.png)



### Other Types of Plots

![image](https://github.com/rougier/matplotlib-tutorial/raw/master/figures/scatter.png)

![image](https://github.com/rougier/matplotlib-tutorial/raw/master/figures/bar.png)

![image](https://github.com/rougier/matplotlib-tutorial/raw/master/figures/quiver.png)

![image](https://github.com/rougier/matplotlib-tutorial/raw/master/figures/plot3d.png)

![image](https://github.com/rougier/matplotlib-tutorial/raw/master/figures/text.png)

