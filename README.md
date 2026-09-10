# DAT 2002 Portfolio Page
## Guy Francis

### Visualization 1
![Visualization 1](/Wind_Speed_vs_Pressure.png/)

**About this visualization:** This visualization shows the relationship between wind speed and air pressure at two Colorado locations. At both locations, there appears to be a negative correlation: as one of these variables increases the other decreases. The relationship appears slightly stronger for Alamosa compared to Denver.

**Software:** This visualization was created using Python/Matplotlib.

**Data:** The data for this visualization were taken from [meteostat.net](https://meteostat.net).

### Visualization 2
![Visualization 2](/US_World_Gini.png)

**About this visualization:** This visualization shows the trend in the Gini coefficient for the United States and all countries since 1963. The Gini coefficient is a measure of economic inequality, with 0% representing total equality and 100% representing total inequality (one person has all the wealth). The trend shows that US inequality has increased from around 35% in 1980 to over 40% in the 2020s, while average inequality for all countries increased in the 1980s and 1990s but then declined in recent decades.

**Software:** This visualization was created using ggplot in RStudio. 

**Data:** The data for this visualization were taken from [World Bank Open Data](https://data.worldbank.org/indicator/SI.POV.GINI).

**Code:** The R code to create this visualization is shown below.
```
ggplot(long_gini, aes(x = Year_Numerical, y = Gini_Coeff))  +
geom_point(aes(Year_Numerical, Gini_Coeff, color="Line One")) +
geom_line(data = us_gini, aes(x = Year_Numerical, y = Gini_Coeff, color="Line Two"), size = 1) +
theme_minimal() +
labs(title='Gini Coefficients for All Countries by Year', x='Year', y='Gini Coefficient (%)')+
theme(plot.title=element_text(hjust=0.5, family='Tahoma', face='bold'),     legend.background = element_rect(color = "black", linewidth = 0.5, fill = "white")) +
geom_smooth(aes(color='Global Trend Line')) +
scale_color_manual(name=NULL, values=c('Line One'='grey80', 'Line Two'='red', 'Global Trend Line'='blue'), labels=c('Global trend line', 'Individual countries', 'United States'))
```
Click the following link to view the [raw markdown for this page](https://raw.githubusercontent.com/gef1729/gef1729.github.io/refs/heads/main/README.md).
