---
title: "FinalExam Basic Stastic"
output: 
  flexdashboard::flex_dashboard:
    vertical_layout: scroll
    theme: yeti
    source_code: hide
---

  
```{r setup, include=FALSE}
# Load library
library(flexdashboard)
library(tidyverse)
library(highcharter)
library(viridis)
library(DT)
library(gapminder)
library(jsonlite)
```

Members {data-orientation=rows}
====

```{r}

```


Summary of Basic Statistics {data-orientation=rows}
====
  
## Column {.tabset .tabset-fade data-height=520}
----

### Chapter 1 {data-width=1200}

Intro to Statistics

### Chapter 2 {data-width=1200}

Data Exploration

### Chapter 3 {data-width=1200}

Basic Visualizations

### Chapter 4  {data-width=1200}

Central Tendency

### Chapter 5 {data-width=1200}

Statistical Dispersion 

### Chapter 6 {data-width=1200}

Essentials of Probability

### Chapter 7 {data-width=1200}

Probability Distributions 

### Chapter 8 {data-width=1200}

Confidence Interval 

### Chapter 9  {data-width=1200}

Statistical Inference

### Chapter 10  {data-width=1200}

Nonparametric Methods


Dataset {data-orientation=rows}
=======================================================================
  
### Table {data-height=520}

```{r}
df <- readr::read_csv(
  "https://raw.githubusercontent.com/dsciencelabs/dataset/refs/heads/master/bestsellers_with_categories.csv",
  show_col_types = FALSE
) %>% 
  dplyr::distinct(Name, .keep_all = TRUE) %>% 
  dplyr::rename(User_Rating = `User Rating`)
```
  
```{r}
# This is going to be a datatable
df1 <- df %>% 
  filter(User_Rating >= 4.5) %>% 
  arrange(desc(Reviews)) %>% 
  select(Name, Author,User_Rating,Reviews,Price,Year)

datatable(df1, 
          options=list(scrollX=TRUE),
          caption = htmltools::tags$caption(
            style = 'caption-side: bottom; text-align: center;',
            'Table: ', htmltools::em('Best Books from 2009 to 2019 By Users Rating Greateher Than 4.5.')
          ))
```

All About Basic Visualizations {data-orientation=rows}
=======================================================================

## Column {.tabset .tabset-fade data-height=520}
-----------------------------------------------------------------------
  
### Pie-Chart {data-width=600 data-height=510}
  
```{r}

```

### Bar-Chart {data-width=600 data-height=510}
  
```{r}

```

### Line-Chart {data-width=600 data-height=510}
  
```{r}

```

### Central_Tendency

```{r}

```

### Statistical Dispersion

```{r}

```

### Probability Distributions

```{r}

```

Confidence Interval  {data-orientation=rows}
=======================================================================

Case Study Example


Statistical Inference {data-orientation=rows}
=======================================================================

Case Study Example


Nonparametric Methods {data-orientation=rows}
=======================================================================

Case Study Example
