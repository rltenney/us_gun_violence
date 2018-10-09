# Problem Statement

In the media deluge that follows each high profile mass shooting in America, there is often an article or two touching upon the relationship between the stock market and mass murder. Anecdotally, we expect to see the stock prices for major gun companies rise in the days following a mass shooting--the rationale for this being that buyers expect the sale of arms to be further regulated or, for certain models (the notorious AR-15, for example), to be banned outright. For this project, I will quantify the relationship, if any, between stock prices of the three major firearms manufacturers in America--Smith & Wesson (AOBC), Sturm Ruger (RGR) and Vista Outdoor (VSTO)--and the incidence of mass shootings.

Additionally, I want to investigate the correlation between economic inequality, number of guns per capita and the level of gun violence present in a given country/state/city.

# Data

For the completion of this project, I relied heavily on a comprehensive gun violence dataset from Kaggle. This dataset was compiled by Kaggle user ____ from data courtesy of website gunviolence.org. For mass shooting information in particular, I used another (smaller) dataset courtesy of that same organization.

For end of day stock market prices, I used a fix for the Yahoo finance API released by the Python organization.

For the gini coefficient of each US state, I relied on another Kaggle dataset.

For global data gun violence data, I relied on data from gunviolence.org and the OECD (by way of Wikipedia).

International Gini coefficients were from the OECD and the World Bank (by way of Wikipedia).

# Process

I first cleaned my main dataset, dropping a great deal of features that weren't related to my specific concerns.
