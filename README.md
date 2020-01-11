<p align="center">
    <img src="https://pmcvariety.files.wordpress.com/2018/01/amazon-logo.jpg?w=1000&h=562&crop=1" alt="logo" width="500" height="300"/>
</p>

<p style="text-align:left; font-size:20px;">Static webpage version of this analysis available <a href="https://ukrainian-serge.github.io/CAPSTONE.io/">HERE</a></p>
  
[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/ukrainian-serge/amazon_product_reviews/master)



<h1  align="center">Database creation with and analysis of Amazon review data</h1>

The goal of this project is extrapolationg interesting human patterns. My intent is to gravitate around digital product reviews vs non-digital product reviews, to compare wether the substrate the media is on effects the way humans review a product title. We'll squeeze as much insight as possible out of this and branch off into other categories for anaysis and comparison.

Analysis is an excellent field and I've seen some astounding insights that can be massaged out of data; with this project, I intend to do the same. The first objective would be starting with really understanding our data. To attain this "data knowledge", I thought it would be prudent to undertake the task of creating a database using the data acquired. My goal is to design the tables in such a way(the data set being extremely large) that would save precious time if the need to revisit this project and analyze it should arise. For this I will use  Python with its handy packages, and my local database management system, PostgreSQL. 


<h2 align="center">Brief work sequence overview</h2>

<h3 align="left">Acquire</h3>

 - [Amazon data](https://s3.amazonaws.com/amazon-reviews-pds/readme.html):
    - download source data using a url from [this](https://s3.amazonaws.com/amazon-reviews-pds/tsv/index.txt) link.
        This was a tough choice. Instead of later realizing I didnt have enough data, I went ahead and chose the largest set. 
    
<h3 align="left">Data wrangle and database creation</h3>

 - [Notebook_1](https://github.com/ukrainian-serge/amazon_product_reviews/blob/master/notebooks_queries/NOTEBOOK_1.0.ipynb) initial data parsing and wrangling:
      - this [notebook](https://github.com/ukrainian-serge/amazon_product_reviews/blob/master/notebooks_queries/NOTEBOOK_1.1_LOG_explore.ipynb) deals with `pandas.read_csv` errors. The error log.txt file is [here](https://github.com/ukrainian-serge/amazon_product_reviews/blob/master/notebooks_queries/Skipping_line_2019.Dec.30%2011.53PM_LOG.txt). 
      - creation of local posgresql database `amazon_reviews`.
      - design datatype structure for columns and creation of `reviews` table with inserted values.
    
 - [Notebook_2](https://github.com/ukrainian-serge/amazon_product_reviews/blob/master/notebooks_queries/NOTEBOOK_2.0.ipynb) table creation automation:
      - more parse and wrangle.
      - automated the process of splitting initial `reviews` into separate tables(by `product_category`).

<h3 align="left">Analysis and visualization</h3>

 - [Notebook_3]()
    - [Bokeh](https://docs.bokeh.org/en/latest/docs/gallery.html) interative charts for analysis
    
---

My [module](https://github.com/ukrainian-serge/amazon_product_reviews/blob/master/notebooks_queries/amazon_reviews_module.py) with functions designed for this project.

<h2 align="center">Technologies Used</h2>

 - [PostgreSQL](https://www.postgresql.org/download/)  
 - [Jupyter Notebooks/Lab](https://jupyterlab.readthedocs.io/en/stable/getting_started/installation.html) with [nbextensions](https://jupyter-contrib-nbextensions.readthedocs.io/en/latest/) of all kinds  
 - [Python](https://www.python.org/) with [Pandas](https://pandas.pydata.org/), [Sqalchemy](https://www.sqlalchemy.org/), [psycopg2](https://pypi.org/project/psycopg2/), [Bokeh](https://docs.bokeh.org/en/latest/docs/gallery.html), and more