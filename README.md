## Data Visualization for Visual Assets  

Digital photographs are embedded with qualitative and quantitative attributes. Creative content professionals use methods to filter and group digital images, based on different criteria, to highlight patterns or segments of large image libraries. These techniques are valuable internally to organize collections and may also provide innovative ways to share options with clients.

## Plotting Jpeg Images  
 
### Jpegs for Points: Brightness and Saturation Scatter Plot  
 
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

<img width="600" alt="bright_sat_DC" src="https://user-images.githubusercontent.com/30129746/80850625-ecd1c500-8bea-11ea-9f6c-19aea158bc69.png">
Plotting jpegs for an image collection by brightness (x) and saturation (y)

## Collection Subject Analysis  
 
### Interactive Ledger  
 
```markdown
scales = alt.selection_interval(empty='all' ,bind='scales',)
selection = alt.selection_multi(fields=['subject', 'collection'])
color = alt.condition(selection,
                      alt.Color('subject:N', legend=None,
                                    scale=alt.Scale(scheme='dark2')),
                      alt.value('transparent'))
scatter = alt.Chart(source).mark_point().encode(
    x = alt.X('transactions:Q', scale=alt.Scale(zero=False,type='log')),
    y= alt.Y('revenue:Q', scale=alt.Scale(zero=False,type='sqrt')) ,
    color= color,
).add_selection(scales).interactive()

legend = alt.Chart(source).mark_rect().encode(
    y=alt.Y('subject:N', axis=alt.Axis(orient='right')),
    x='collection:N',
    color=color
).transform_filter( scales ).add_selection(
    selection
).properties(title="select dimension")

scatter | legend
```

### Filtering Sales Data by Subject and Collection
Plotting individual assets by times sold (x-axis) and revenue earned (y-axis) allow the viewer to see the selling trends for the images. An interactive ledger gives the user options to select subsets of photographs by subject and collection. The tooltip provides information about the individual pictures on hover.


 
  
##  Dominant Color Analysis
Identifying dominant colors in images allows the viewer to source assets that fit a desired color scheme. Collections may have a palette that resounds with a specific client, creating an opportunity to contribute to a brand or participate in a campaign. Depending on a photographer's location, techniques, and personal tastes their image colors vary. Below are six collections' dominant colors returned in grids.

```markdown
import seaborn as sns
sns.set()
def hex_to_rgb(hex_value):
  h = hex_value.lstrip('#')
  return tuple(int(h[i:i + 2], 16) / 255.0 for i in (0, 2, 4))
hex_colors = [
  '#f0787e', '#f5a841', '#5ac5bc', '#ee65a3', '#f5e34b', '#640587', '#c2c36d',
  '#2e003a', '#878587', '#d3abea', '#f2a227', '#f0db08', '#148503', '#0a6940',
  '#043834', '#726edb', '#db6e6e', '#db6ecb', '#6edb91'
]
rgb_colors = list(map(hex_to_rgb, hex_colors))
sns.palplot(rgb_colors)
row_size = 15
rows = [rgb_colors[i:i + row_size] for i in range(0, len(rgb_colors), row_size)]
for row in rows:
  sns.palplot(row)
```

<img width="600" alt="dom_color_6" src="https://user-images.githubusercontent.com/30129746/80851767-a764c600-8bf1-11ea-94b6-9955388477dc.png">


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
