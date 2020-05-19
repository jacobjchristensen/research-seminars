
# Research seminars

In this **seminar series**, we will discuss various aspects of research.

Work related to R and RStudio will be central, but other aspects  of research are also considered, such as strategies for effective *project planning*, *project management*, *data collection*, *data analysis* and *communication*. 

![](figures/premise.png)


## Documentation


### 2020-06-02

*Topic*: TBA


### 2020-05-26

*Topic*: Power calculations in R

We will go over some simple power calculations in R using the `pwr` package, and discuss the usefulness of *post hoc* power calculations in particular. 



### 2020-05-19

*Topic*: How to do peer review

This will be more of a discussion about how to do peer review. We don't want to end up as [reviewer #2](http://dailynous.com/2017/02/07/bad-reviewer-2-actually-data-philosophy-journal/). 

Short summary: 

- Give a brief overview and general recommendation. 
  -	Succinctly describe knowledge gap, importance and relevance to the readers of the journal.
  -	Briefly outline key methods and findings. 
  -	Explain reasoning behind recommendation. 
- Prioritize your feedback by importance: most important major comments first; minor comments last. 
- Use checklists: STROBE, CONSORT, etc. or specific checklists provided by the journal. 
- The distinction between *minor* and *major* revision is not entirely clear; however, a rule of thumb can be whether reviewer comments would lead to another round of review or not. 



### 2020-05-12

*Topic*: EDA of tidytuesday dataset

Amanda went through the TT dataset for week 20 about Volcanos. Made the following figures: 

- Number of volcanos per country (top 15 countries with most volcanos)
- Number of volcanos per country (top 15 countries with most volcanos), colored by volcano type
- Elevation of volcanos (top 15 countries with most volcanos) with density plots
- We also made a `leaflet` map of all volcanos. Just 'cause. 
- And some other stuff. 

Code in `tidytuesday_w20.Rmd` and `tt-week20-volcanos.Rmd`. 


### 2020-05-05

*Topic*: This week, we will use tidytuesday data from week 8, about food consumption and CO2 emissions. These data are taken from [nu3 - Food carbon footprint index 2018](https://www.nu3.de/blogs/nutrition/food-carbon-footprint-index-2018). 

*Log*: 

We went through a few aspects related to tidytuesday in general, including use of the `tidytuesdayR` package. Spent some time getting to know the variables included. Then we discussed potential research questions, and started analysis. 

Code in `tt-week18.rmd` (Jacobs code) and `200505-TT.rmd` (Vegards code). It should be possible to download and run these scripts without problems. 


### 2020-04-28

*Topic*: RStudio cheatsheets: data visualization (`ggplot2`)

Created a few plots to showcase the ggplot2 functionality. Then we went over the key topics from the cheatsheet, including: 

- Different types of visualizations (see also [Claus Wilkes great book](https://serialmentor.com/dataviz/))
- Geoms
- Scales
- Coordinate systems
- Facets
- Position adjustment
- Themes
- Labels
- Legends
- Saving

Code in `cheatsheets-ggplot2.rmd`. 


### 2020-04-20

*Topic*: RStudio cheatsheets: apply functions (`purrr`)

- Key functions from cheatsheet
  
  - `map`/`map2`/`pmap` and `_*` friends
  - `pluck`, `keep`, `discard`
  - `modify`
  - `set_names`

We also went through a few modeling examples using the *mutate-map* strategy. 

Code in `cheatsheets-purrr.rmd`. 


### 2020-04-14

*Topic*: RStudio cheatsheets: data transformation (`dplyr`)

1. Key functions from cheatsheet (Vegard)

- Went through key function, including: 
  
  - `pull`
  - `distinct`
  - `slice`
  - `select` and helper functions
  - `rename`
  - `mutate`
  - `filter` and helper functions
  - `arrange`
  - `group_by`
  - `summarise`

Code in `200414-Dplyr.rmd`. 

There are also a few new functions coming in [`dplyr` 1.0.0](https://www.tidyverse.org/blog/2020/04/dplyr-1-0-0-rowwise/). We briefly discussed a few of these, including new features for `summarise` using `across`. 


2. Perform log transformation and normalization (to standard normal distribution) (Jacob)

Code in `log-scale.Rmd`


### 2020-04-06

*Topic*: RStudio cheatsheets: data import (`tidyr`)

- Discussed the `read_*` functions, with emphasis on `read_csv`. 
- We can specify which type of delimiter we have with `read_delim` and the delim argument. 
- Get more info about a `readr` function with ?, like so: `?read_csv`, or at [the tidyverse documentation website](https://readr.tidyverse.org/). 
- Use `col_types = cols()` to specify column types directly in the call to the readr function. 
- Otherwise, change column types with a subsequent mutate call; you can also use some variant of purrr::modify. 
- `haven` is great to read (and write) SPSS (.sav) and STATA (.dta) files. 
- Use `read_sav` or `read_spss` to read SPSS files. 
- Check if a variable is labelled (with SPSS labels) using the `haven::is.labelled` predicate function.
- Convert from labelled SPSS variable to R factor with the `haven::as_factor` function.
- Pull out other attributes from an SPSS file/object with the `attributes` function. 
- Be careful with converting stuff to factors. Under the hood, a factor is just an integer. 
- Use `drop_na` to drop rows with missing entries, or supply a variable name to remove rows with missing entries for just that variable. 
- Replace missing entries with something using the `replace_na` function. 
- This pattern is a recurring theme: `gather`/`pivot_longer` - `separate` - `unite` - `spread`/`pivot_wider`. 


### 2020-03-30

*Topic*: Regularization with LASSO and ridge. 

- Discussed penalization principles. 
- Discussed LASSO, ridge and the standard variable selection procedures (forward/backward stepwise). 
- Trevor Hastie and Junyang Qian has [a great vignette](https://web.stanford.edu/~hastie/glmnet/glmnet_alpha.html) on the `glmnet` package. 
- Chapter six in *An Introduction to Statistical Learning - with Applications in R* by James, Witten, Hastie & Tibshirani is a great resource for the `glmnet` package and LASSO/ridge regression. 
- It is [free online](http://faculty.marshall.usc.edu/gareth-james/ISL/). 
- There are also some [available videos](https://www.dataschool.io/15-hours-of-expert-machine-learning-videos/) that can take you though the material. 
- It is somewhat unclear how we should optimally use these procedures in statistical inference. 
- They can probably be used in concert with traditional methods to select the most important variables in a larger set of potential variables. That is, a more data-driven type of variable selection (shrinkage). This would be similar to use of PCA to account for correlation between variables, although PCA doesn't retain that much interpretability. 



### 2020-03-23

- Worked through the `pivot_` functions from `tidyr`. 
- These can be very useful to take control over repeated measures. 
- They are also very effective for visualizations: 
  - Visualize distributions for multiple variables. 
  - Visualize small multiples (subsets of data over many small panels/facets)

