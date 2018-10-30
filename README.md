# Problem Statement

Gun violence in the US seems to be an intractable problem. Because of political polarization, lobbyist dollars or other monolithic factors, it remains a perennial and unmitigated disaster in this country. My goal in this project was, firstly, to attempt to identify any overall trends in gun violence, as well as to identify hot spots that may be underreported by the media. Additionally, I'm interested in the possibility of forecasting gun violence in order to make better policy decisions.

# Data

For the completion of this project, I relied on a dataset compiled by Kaggle user James Ko from data courtesy of the DC-based nonprofit gunviolence.org. The information it contained was quite exhaustive--locations, numbers of deaths/injuries, participant information (if available), number of weapons used, etc. For my purposes, I was looking almost exclusively at locations and number of fatalities. The data begins 1/1/2013 and continues through March of 2018. However, the data for 2013 was largely absent, so I disregarded this year.

https://www.kaggle.com/jameslko/gun-violence-data/

**An important caveat: This data only contains information regarding homicides or attempted homicides. It does not contain any data regarding suicides or accidental deaths/injuries. This is significant because, according to the nonprofit Everytown, nearly two thirds of all gun deaths are suicides.**

https://everytownresearch.org/gun-violence-america/?source=etno_ETHomePage&utm_source=et_n_&utm_medium=_o&utm_campaign=ETHomePage

For end of day stock market prices, I used a fix for the Yahoo finance API released by the Python organization.

All population information was obtained from the US Census Bureau.

# Process

I began by cleaning the kaggle dataset and performing some high-level EDA. I discovered, for instance, that the Mandalay Bay mass shooting in Las Vegas was notably absent from the dataset... this would have thrown off my findings irreparably, so I added it in manually.

I then wanted to examine what relationship, if any, there was between mass shootings and gun company stock prices. Based on visual inspection, there seems to be a correlation, although I couldn't prove causation definitively. This would be a good topic to look at in depth at a later date.

![]aobc_mass.png

Iteratively, I began to become more granular in my approach and focus. Through EDA, it was first evident that there was a wide disparity between the rates of violence of particular states. I soon discovered that cities were the actual drivers of America's high per capita rates of gun violence. I looked at yearly per capita rates for cities, and then those of large cities (>500k residents) in particular.

Lastly, I wanted to see if there was any way to model gun violence trends and, ideally, make future predictions. I found some tentative success using the Facebook Prophet module. It seems that there are clear seasonal trends in shootings, although I was a bit skeptical of my model's performance. Namely, I see a clear upward trend in violence over the past four years that Prophet did not take into account when forecasting.

# Conclusions

On a national level, gun violence has increased over the past four years. The underlying causes of this escalation remain unclear to me and would have to be investigated further. However, this is a very big deal: after decades of decline, levels of violence are once again increasing.



https://cdn.vox-cdn.com/thumbor/oVYER5nMqftXligfzHXYYQW0e4U=/0x0:417x395/920x0/filters:focal(0x0:417x395):format(webp):no_upscale()/cdn.vox-cdn.com/uploads/chorus_asset/file/9371435/firearm_homicide_deaths.png

On a city level, year after year, certain cities rate abysmally high in terms of gun violence. I've focused particularly on Baltimore in this project, as it's the large city that always has the highest per capita rates of violence. However, other cities such as Gary, Indiana and Wilmington, Delaware also have very high per capita rates. I think the media's obsession with gun violence in Chicago is potentially harmful: although Chicago has the highest total number of gun murders year after year, there are many cities that are worse relative to their populations. It does the residents of these cities a great disservice to underreport their respective epidemics.

In terms of forecasting, this was an interesting experiment but I ultimately think it's challenging to make any meaningful predictions on longer-term trends (for instance, will 2019 rates of gun violence be higher or lower than 2018). Forecasting would be useful, however, in allocating resources to cities in times of seasonal spikes. This might be a moot point, however, as violence doesn't behave predictably or relationally. For instance, there has been a sharp spike in homicides in Baltimore in recent weeks, which is unusual for the colder fall weather: https://www.cbsnews.com/news/230-officers-shifted-to-baltimore-streets-after-uptick-in-deadly-violence/

# Stretch Goals

I experimented a bit with using Gini coefficients to predict levels of gun violence before abandoning this approach. Some cities with huge Gini coefficients, namely Los Angeles and New York, have low levels of violence relative to other US cities. And here you can't merely rely on the strength of gun laws as a predictor--Maryland has gun laws that are comparable to California and New York. The problem with Gini is that is measuring the gap between rich and poor--it doesn't do well on a city like Baltimore or Gary that is mostly poor. I do think that looking at some other economic metrics might be helpful towards this end.
