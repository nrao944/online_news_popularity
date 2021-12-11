# Online News Popularity

A project assessing whether the type of article (Entertainment, Business, Lifestyle, Social Media, Tech, World, and Others) and when the article was published (weekday or weekend) are associated with online news popularity in accordance with DSCI 522 (Data Science Workflows) for the Master of Data Science Program at the University of British Columbia.

## Authors: 

Nagraj Rao, Linhan Cai, Jennifer Hoang

All co-authors are students in the Master of Data Science program at the University of British Columbia - Vancouver.


## Project Abstract

The market space for online news has grown manifold, with traditional news outlets also providing online versions of their articles. This growth has been complemented with increased competition, particularly from non-traditional news outlets such as small-scale digital news companies, who can reach a wider audience through social-media. As these companies optimize their staff and other resources, it is important to understand what matters to gain online traction in order to capture a larger market share? 

The aforementioned question propels our study. In particular, we want to assess if: 

(i) the type of news article (business, entertainment, news, etc.) is associated with the number of shares of online news articles, and 

(ii) the day of week a news article is published is associated with the number of shares of online news articles?

Our findings will be relevant to news organizations that are interested in boosting traction of their online news articles and may help guide management decisions on the characteristics associated with more popular articles. 

The public dataset our team is using for conducting this analysis called "Online News Popularity", and is available on University of California's Machine Learning Repository (Online News Popularity, 2015). It has 36,644 observations (examples) and 61 columns (attributes), summarizing a range of characteristics about articles that were published by Mashable between 1 January, 2013 and 31 December, 2014. Each row represents a news article and includes covariates that are a mix of categorical, continuous, and binary features. We create a new feature called “log_shares_per_day” which is the log of (number of shares/ Days between the article publication and the dataset acquisition). 

We rely on different specifications of a multiple linear regression model and adjusted R-Squared as our evaluation metric since it accounts for degrees of freedom compared to a traditional R-Squared. Adjusted R-Squared also defines the degree of variance in the dependent variable that can be explained by the independent variables. Other metrics such as RMSE or MAE do not not provide a range that will help us in establishing how well our model is doing.  

Our final model, derived using backward model selection, found evidence at 95% confidence level that both type of news article and day of the week of publication are statistically significantly associated with number of shares per day (log transformed), all else equal. In particular, an article shared on the weekend is associated with an increase in the number of shares per day of 26%. Similarly, all categories of news articles, except entertainment news, have a positive association with increase in number of shares per day. Our study achieved an adjusted R-squared score of 0.19, implying that additional features that are not among our explanatory variables appear to explain a large portion of variability in shares per day. Future recommendations include collecting data on additional features to boost the model performance.

## Report

The final report is linked: http://htmlpreview.github.io/?https://github.com/UBC-MDS/online_news_popularity/blob/main/doc/report.html

## Usage

The analysis used to create this report can be replicated using either of the following methods:

1) **Using Docker:**

*(Note - These instructions will need to be run in a unix shell such as terminal or git bash)*

Please install Docker, clone the Github repository, and run the following command from the project root directory in the command line/terminal to reset the project directory:
```
# For Mac
docker run --rm -v /$(pwd):/home/onp jennhoang/online_news_popularity:v0.3.0 make -C /home/onp clean

# For Windows
docker run --rm -v /$(pwd)://home//onp jennhoang/online_news_popularity:v0.3.0 make -C //home//onp clean
```
Then, run the following command to re-run the analysis and generate the report:
```
# For Mac
docker run --rm -v /$(pwd):/home/onp jennhoang/online_news_popularity:v0.3.0 make -C /home/onp all

# For Windows
docker run --rm -v /$(pwd)://home//onp jennhoang/online_news_popularity:v0.3.0 make -C //home//onp all
```

2) **Without Docker:**

Please install the dependencies below, clone the Github repository, and run the following command from the project root directory in the command line/terminal to run the analysis:
```
make all
```
To reset the project directory and delete the analysis outputs, the following command can be run:
```
make clean
```

## Dependencies
- Python version 3.9.5 and Python packages:
  - docopt=0.6.2
  - altair=4.1.0
  - altair-data-server=0.4.1
  - altair-saver=0.5.0
  - pandas=1.3.4
  - numpy=1.21.4
- R version 4.1.1 and R packages:
  - knitr=1.33
  - tidyverse=1.3.1
  - docopt=0.7.1
  - feather=4.1.2
  - caret=4.1.2
  - here=4.1.2
  - car=4.1.2
- GNU Make 3.81

## Dependency Diagram of Makefile

![Dependency Diagram](https://github.com/UBC-MDS/online_news_popularity/blob/main/Makefile.png)


## References

Online News Popularity. (2015). UCI Machine Learning Repository. Available at: https://archive-beta.ics.uci.edu/ml/datasets/online+news+popularity.

## License:

The materials used for this project are under an open access article distributed under the Creative Commons Attribution License, which permits unrestricted use, distribution, and reproduction in any medium, provided the original work is properly cited. If reusing/referencing, please provide a link to this webpage.


