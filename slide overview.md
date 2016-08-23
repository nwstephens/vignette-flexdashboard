
flexdashboard: Easy interactive dashboards for R
========================================================
author: Jim Clemens
date: 4/26/16
autosize: true

Use R Markdown to publish a group of visualizations
========================================================

[Examples](http://rstudio.github.io/flexdashboard/examples.html)

- Flexible and easy to specify layouts
- Charts are intelligently re-sized to fill the browser 
- Dashboards are adapted for display on mobile devices
- Combine with RStudio Connect for daily metrics updates

Available Components
========================================================

- Interactive htmlwidgets
- Base, lattice, and grid graphics
- Tabular data (with optional sorting, filtering, and paging)
- Value boxes for highlighting summary data
- Gauges

The [Components page](http://rmarkdown.rstudio.com/flexdashboard/using.html#components) describes the use of each in detail.

Layouts
========================================================

- Pages
- Tabsets
- Storyboards
- Input Sidebars
- Themes
- Mobile Specific

See the [layouts page](http://rmarkdown.rstudio.com/flexdashboard/layouts.html) for more detail.

Using Shiny in flexdashboards
========================================================

- Allow users to change parameters interactively
- Update data automatically
- Requires deployment on a Shiny Server

Instructions can be found on the [flexdashboards Shiny page.](http://rmarkdown.rstudio.com/flexdashboard/shiny.html)

Building an Example
========================================================

We'll build a flexdashboard using data from the [quantmod package](http://www.quantmod.com/)

- getSymbol returns a time series of the price of stock
- Cl is the closing price
- dygraph charts a time series
- DT displays a table


```r
library(quantmod); library(dygraphs); library(DT)

# Load trading history
getSymbols(c("AAPL", "AMZN", "IBM"))
# graph closing prices
dygraph(Cl(AAPL))
# Display as a table
datatable(AAPL)
```

