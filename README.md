# How far can you go for love on Airbnb? 

Welcome to our research project! This research aims to answer the following research question:

**What is the effect of Valentine's Day on Airbnb listings in Europe?**

![This is an image](https://turntable.kagiso.io/images/romantic_bedroom.width-800.jpg)

## Motivation
Valentine's Day is celebrated yearly on the 14th of February. It is a day when romance takes centre stage and people show their love for each other with accompanying rituals. Specific behaviours and rituals that people often perform are giving gifts, showing affection, or going out for dinner or a romantic getaway [(Close & Zinkhan, 2006)](https://www.acrwebsite.org/volumes/v33/v33_10020.pdf). For overnight stays, Airbnb accommodation is often booked.

Therefore, this study proposes the following research question:

*What is the effect of Valentine's Day on Airbnb listings?*

During this project, we zoom in on three major cities in Europe. We find this interesting as countries celebrate Valentine's Day with different intensity. Furthermore, we focus on the following subquestions:
1. What is the influence of Valentine's Day on the price of Airbnb listings?
2. What is the influence of Valentine's Day on the number of booked Airbnb listings? 
3. Compared to 'normal days', are relatively more Airbnb accommodations with one/two beds booked during Valentine's Day?

These sub-questions include comparisons between the cities of Paris, Rome and Madrid. We chose these cities because celebrating Valentine's Day is popular in each of their respective countries [(Valentine’s Day Around the World, n.d.)](https://www.autoeurope.com/travel-blog/valentines-day-around-world/).

## Method and results

### Method

The data used in this research project was obtained from [Inside Airbnb](http://insideairbnb.com/). For this research, we looked into the data starting from two weeks before Valentine's Day 2022 (January 31st) untill two weeks after Valentine's Day 2022 (February 28th). We created a dummy for Valentine's Day so that we could compare the effect of Valentine's Day with other, "normal" days. For the analysis, we compare three major cities in Europe: Paris, Rome and Madrid.

In order to answer the research question, we used several types of analyses. For the analysis of the effect of Valentine's Day on the price Airbnb listings, a t-test has been performed. In addition, a logistic regression was performed to examine the effect of Valentine's Day on the number of bookings. This type of regression was also used to examine whether accommodations with fewer (one/two) beds are booked during Valentine's Day. We compared the outcomes of different cities (Madrid, Paris, Rome) in all these analyses.

Variable | Description
-------- | --------
price | The price of the Airbnb listing in dollars
bookings | Dummy variable: whether the accommodation is unbooked (0) or booked (1)
beds | Dummy variable: zero or more than two beds (0) or one or two beds (1)
valentinesday | Dummy variable: whether it is not Valentine's Day (0) or it is (1)
city | The city where the Airbnb ad is located (Madrid, Paris or Rome)

![Schermafbeelding 2022-10-14 om 11 49 06](https://user-images.githubusercontent.com/112401369/195817813-da1a32ac-452d-42ed-ad10-9fd6e870779e.png)

### Results

- Price: H0: Valentine's Day has no influence on the prices of Airbnb listings. A P-value of >0.05 was found in the results of the T-test for both all cities combined and individual cities. Therefore, with a significance of 0.05, the H0 could not be rejected. No significant relation was found between Valentine's Day and prices of Airbnb listings. 

- Bookings: H0: Valentine's Day has no influence on the amount of booked Airbnbs. The result from the logistic regression show a P-value<0.01. Therefore, with a significance of 0.05, the null hypothesis could be rejected. On Valentine's Day, the odds of a listing being booked, increases with 1.03. Looking at the exponents, we found a small difference of this effect between cities. On Valentine's Day, the odds of booked Airnbnbs in Madrid decreases by a value of 0.996. While in Rome, these odds increase by a value of 1.006 and in Paris by a value of 1.006. The exponents show that the likelihood of booking an Airbnb on Valentine's Day is highest in Paris.

- Beds: H0: Valentine's Day has no influence on the number of beds in booked Airbnbs. The P-value of the logistic regression and log likelihood are both >0.05. Therefore, with a significance of 0.05, the H0 could not be rejected. No significant relation was found between Valentine's Day and the number of beds in booked Airbnbs.

## Conclusion

In answer to our research question, no significant correlation was found between Valentine's Day and Airbnb accommodation prices. This is true both for accommodations in Paris, Rome and Madrid together and for the cities individually. Second, a significant relation was found between Valentine's Day and the chances of an Airbnb listing being booked. However, although the chances of a listing being booked in Paris and Rome increases on Valentine's Day, the chance of a booking in Madrid decreases on this day. Finally, no significant relation was found between Valentine's Day and the number of beds in booked Airbnbs.

## Repository overview
```
├── README.md
├── gen
│   ├── analysis
│   │   └── output
│   └── data-preparation
│       └── temp
└── src
    ├── analysis
    └── data-preparation
```

## Dependencies

- Install [R and RStudio](https://tilburgsciencehub.com/building-blocks/configure-your-computer/statistics-and-computation/r/).
- Install [make](https://tilburgsciencehub.com/building-blocks/configure-your-computer/automation-and-workflows/make/).

For R, install the following packages:
```
install.packages('tidyverse')
install.packages('dplyr')
install.packages('ggplot2')
install.packages('readr')
install.packages('stringr')
install.packages('ggpubr') 
install.packages('car') 
install.packages('scales')
install.packages('stargazer')
```

## Running instructions

**Step-by-step**

To run the code, we recommend using the make file. Please follow the following instructions:

1. Fork this repository

2. Open your command line / terminal and run:

```
git clone https://github.com/{your username}/Airbnb-Valentines-Day.git
```

3. Set your working directory to:

```
Airbnb-Valentines-Day
```

4. Run make using the following command:

```
make
```

Make will run all code and delete all raw and unnecessary data files created during the pipeline.

Alternatively, one can run the scripts/files in the following order:

1. Install packages: ../src/data-preparation/install_packages.R
2. Download data: ../src/data-preparation/download_data.R
3. Clean data: ../src/data-preparation/data_cleaning.R
4. Explore data: ../src/data-preparation/data_exploration.Rmd
5. Price analysis: ../src/analysis/price_analysis.R
6. Bookings analysis: ../src/analysis/bookings.analysis.R
7. Beds analysis: ../src/analysis/beds.analysis.R
8. Final report: ../src/analysis/report.Rmd

## More resources

- Close, A., & Zinkhan, G. (2006). A holiday loved and loathed: a consumer perspective of Valentine's Day. ACR North American Advances.

- Home. (n.d.-a). Retrieved 16 October 2022, from http://insideairbnb.com/

- Valentine’s Day around the world. (n.d.). Retrieved 17 October 2022, from https://www.autoeurope.com/travel-blog/valentines-day-around-world/

## About

This research project is part of the [Data Preparation and Workflow Management (dPrep)](https://dprep.hannesdatta.com/) course at Tilburg University and is conducted by Team 12. The contributors of the research are:
- [Anouk Bor](https://github.com/AnoukBor)
- [Eva Bos](https://github.com/EvaBos)
- [Bi Xuan Guo](https://github.com/bixuanguo)
- [Mandana Khabbazi](https://github.com/Mandanakhabbazi)
- [Indi Wieggers](https://github.com/indiwieggers123)
