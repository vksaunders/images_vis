## Data Visualization for Visual Content

Visualizing data for visual assets, like photographs, introduces interesting challenges. Many visual properties of photography cannot necessarily be mapped to standard visualization methods, particularly when working with large image libraries.

Digital photographic images are embedded with technical data that can be sorted, grouped and analyzed for patterns. Photographs also cover subject matter and have external success measures, like sale prices, that can be sorted and plotted in more traditional tables and graphs. Finding ways to “see” photographs through data and in the data provides a frontier for photographic study. This combination of quantitative and qualitative variables offers interesting options for visualizing creative content collections. Creative content professionals can use the below tools to identify trends among assets, collections, and subject-matter, based on different qualities. Grouping image assets by their physical properties, such as hue and saturation, may also provide innovative ways to present assets to viewers.

This project explores some of the ways to analyze a collection of images using Python, Imageplot, Excel, and Tableau. Filtering a commercial stock library by photographer, six collections are analyzed and compared using different metrics.

### Plotting Jpeg Images
#### Jpegs for Points: Brightness and Saturation Scatter Plot

Spreadsheet data and database data without thumbnail reference, can be limiting for creative directors who wish to understand their collections visually by directly seeing the image mapped to its numeric value sets. This Python script substitutes jpegs for points in a scatter graph. Using [ImageJ](https://imagej.net/Welcome) and ImagePlot from [Software Studies Initiative](http://lab.softwarestudies.com/), attributes of brightness, saturation, and hue for picture collections were measured and recorded in CSV files. Then Python is used to plot the jpegs according to any measures chosen. 

```markdown
def absoluteFilePaths(directory):
   for dirpath,_,filenames in os.walk(directory):
       for f in filenames:
           yield os.path.abspath(os.path.join(dirpath, f))
images = []
for p in paths:
    foo = Image.open( p )
    foo = foo.resize((int(foo.size[0]/20) , 
    int(foo.size[1]/20)),Image.ANTIALIAS) 
    images.append( foo )
fig, ax = plt.subplots()
ax.scatter(x, y)
for x0, y0, image in zip(x, y,images):
    ab = AnnotationBbox( OffsetImage(image)  , (x0, y0), frameon=False) 
    ax.add_artist(ab)
```

<img width="419" alt="DC_NC" src="https://user-images.githubusercontent.com/30129746/80531445-a9682400-8968-11ea-8988-eb0711751943.PNG">
### Plotting jpegs for two collections by hue (x) and saturation (y)

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/vksaunders/picsvis/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/vksaunders/picsvis/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
