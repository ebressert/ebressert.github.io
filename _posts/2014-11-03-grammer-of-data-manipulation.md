---
layout:     post
title:      Grammar of Data Manipulation
date:       2014-11-03
summary: Test text
---

R and Python are two widely used languages for data analysis. R has been around for some time, has a healthy set of libraries for statistical analysis and predictions, and the packages have had time to evolve and become more polished. Whereas Python came into the spotlight for analytical purposes in the last decade thanks to NumPy, SciPy, Scikit-Learn, and recently - Pandas. Taking what R has learned, Pandas replicated the DataFrame structure in to Python and has made the operation of working with tabular data much easier.

What **was** lacking in both R and Python was the capability of manipulating data in a consistent and functional form. Similar to [*Grammar of Graphics*](http://www.springer.com/statistics/computational+statistics/book/978-0-387-24544-7), which is employed nicely in ggplot2, a package called [dplyr](http://cran.rstudio.com/web/packages/dplyr/vignettes/introduction.html) was developed to employ a similar grammar system. At its purest form, dplyr treats data manipulation as follows,


$$ verb(\text{DataFrame}, operator) $$


where the verbs are

- filter()
- slice())
- arrange()
- select()
- rename()
- distinct()
- mutate()
- transmute()
- summarise()
- sample_n()
- sample_frac()

{% highlight R linenos %}
library(nycflights13)

head(flights)
#> Source: local data frame [6 x 16]
#>    year month day dep_time dep_delay arr_time arr_delay carrier tailnum
#> 1  2013     1   1      517         2      830        11      UA  N14228
#> 2  2013     1   1      533         4      850        20      UA  N24211
#> 3  2013     1   1      542         2      923        33      AA  N619AA
#> 4  2013     1   1      544        -1     1004       -18      B6  N804JB
#> ..  ...   ... ...      ...       ...      ...       ...     ...     ...
#> Variables not shown: flight (int), origin (chr), dest (chr), air_time
#>   (dbl), distance (dbl), hour (dbl), minute (dbl)


filter(flights, month == 1, day == 1)
#> Source: local data frame [842 x 16]
#>
#>    year month day dep_time dep_delay arr_time arr_delay carrier tailnum
#> 1  2013     1   1      517         2      830        11      UA  N14228
#> 2  2013     1   1      533         4      850        20      UA  N24211
#> 3  2013     1   1      542         2      923        33      AA  N619AA
#> 4  2013     1   1      544        -1     1004       -18      B6  N804JB
#> ..  ...   ... ...      ...       ...      ...       ...     ...     ...
#> Variables not shown: flight (int), origin (chr), dest (chr), air_time
#>   (dbl), distance (dbl), hour (dbl), minute (dbl)
{% endhighlight %}
