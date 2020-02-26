## TWelcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/lapseudog/lapseudog.github.io/edit/master/index.md) to **maintain** and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

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


# Outliers
The Normal distribution is commonly refered in common language.
In addition the Standard deviation is a common measure of the dispersion. While the standard deviation does not only apply to the standard distribution, the standard deviation if often illustrated applied to the standard distribution. Confusing? probably.

## Rule of thumb

## Common method for identifying outliers

### Mean and Standard Deviation

### Median and Median Absolute Deviation (MAD)
Median of the abs[Median - values]

### Median and Interquantile Deviation (IQD)


## Results with common distributions

|Distribution | Rank of mean +2 SD| Rank of mean +3 SD|Rank of MAD +2| Rank of MAD +3|Rank of IQD +2| Rank of IQD +3|
|--- |--- |--- |--- |--- |--- |--- |
Normal Distribution |  97.718 |  99.864 | 91.135 |  97.840 | 99.647 |  99.997 |
std Exponential |  95.024 |  98.159 | 80.957 |  88.229 | 94.449 |  98.139 |
Exponential 0.5 |  95.021 |  98.165 | 80.930 |  88.242 | 94.471 |  98.161 |
Exponential 2.0 |  95.020 |  98.160 | 80.889 |  88.185 | 94.445 |  98.147 |
Exponential 0.1 |  95.008 |  98.170 | 80.906 |  88.188 | 94.413 |  98.142 |
Gamma shp .1 |  96.210 |  97.755 | 55.791 |  57.420 | 80.190 |  83.236 |
Gamma shp .5 |  94.982 |  97.795 | 74.452 |  80.964 | 91.188 |  95.795 |
Gamma shp 1 |  95.038 |  98.172 | 80.861 |  88.159 | 94.463 |  98.155 |
Gamma shp 3 |  95.567 |  98.824 | 85.652 |  93.119 | 97.146 |  99.485 |
Gamma shp 5 |  95.909 |  99.058 | 86.891 |  94.304 | 97.837 |  99.714 |
Gamma shp 10 |  96.325 |  99.317 | 88.197 |  95.440 | 98.484 |  99.867 |
Power shp .01 |  98.145 |  98.512 | 50.564 |  50.707 | 75.517 |  75.828 |
Power shp .1 |  93.082 |  96.296 | 55.789 |  57.407 | 80.414 |  83.715 |
Power shp .5 |  96.403 |  100.000 | 82.650 |  94.812 | 100.000 |  100.000 |
Power shp 1 |  100.000 |  100.000 | 99.865 |  100.000 | 100.000 |  100.000 |
Power shp 5 |  100.000 |  100.000 | 100.000 |  100.000 | 100.000 |  100.000 |
Power shp 10 |  100.000 |  100.000 | 100.000 |  100.000 | 100.000 |  100.000 |
Power shp 100 |  100.000 |  100.000 | 100.000 |  100.000 | 100.000 |  100.000 |
Beta 0.5 0.5 |  100.000 |  100.000 | 100.000 |  100.000 | 100.000 |  100.000 |
Beta 1 1 |  100.000 |  100.000 | 100.000 |  100.000 | 100.000 |  100.000 |
Beta 1 3 |  95.218 |  99.512 | 84.984 |  93.577 | 98.652 |  100.000 |
Beta 2 2 |  99.221 |  100.000 | 93.776 |  100.000 | 100.000 |  100.000 |
Beta 2 5 |  96.140 |  99.650 | 87.980 |  95.957 | 99.215 |  100.000 |
Beta 5 1 |  100.000 |  100.000 | 100.000 |  100.000 | 100.000 |  100.000 |

## boring details
predominance of normal distribution :
https://trends.google.com/trends/explore?date=today%205-y&q=normal%20distribution,power%20law%20distribution,gamma%20distribution,exponential%20distribution


generated with 
Numpy version  1.18.1
Python version  3.8.1 


### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/lapseudog/lapseudog.github.io/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
