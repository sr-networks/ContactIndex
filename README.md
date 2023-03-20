# CXmob - Contact Index from mobility data
### Global analysis of the Contact Index during the SARS-CoV-2 pandemic

This is a first description of my Contact Index calculations based on mobility data. I use the Google and Apple mobility data that was publicaly availible together with the German Contact Index that can be found here:

https://contactindex.netcheck.de

- With XGBoost I first calculated a fit of the German mobility data to the German CX:

<img width="531" alt="image" src="https://user-images.githubusercontent.com/127544698/225931088-f2af6898-8bcb-4c04-bd4a-11877cc30e46.png">

Overfitting is avoided by using k-fold cross-validation.

- Then I use the resulting model to predict the Contact Index for other countries from their respective mobility data. 

Below are some preview charts for selected countries. 
- The first columns shows the evolution of CX over the entire time for which mobility data is availible (Apple stopped providing in April 2022). 
- The second column compares the CX evolution during the first year of the pandemic with that of the R values for the respective countries. Mostly good agreement (with the expected time delay for reporting) except for United States. 
- The third column compares CX with the Government Response Index (specifically the stringency index, which includes all containment and closure policy and one health information index). Note that the axis if GRI is inverted so that strong restrictions coincide with small CX. Data from https://github.com/OxCGRT/covid-policy-tracker

<img width="250" alt="image" src="https://user-images.githubusercontent.com/127544698/224420337-bf822124-3062-4764-910b-d10d94579233.png">  <img width="270" alt="image" src="https://user-images.githubusercontent.com/127544698/224478394-b04771b7-aa0b-4626-ae22-7066ebb83fe3.png"> <img width="270" alt="image" src="https://user-images.githubusercontent.com/127544698/224572358-7c4187a7-94bd-4f1e-bf5a-36b5db419257.png">

<img width="250" alt="image" src="https://user-images.githubusercontent.com/127544698/224420446-2f739ebe-9d34-4143-8d62-2ac3eebe2c62.png">  <img width="270" alt="image" src="https://user-images.githubusercontent.com/127544698/224478435-33f04127-383e-40df-bc42-ae5a94c3b57a.png"> <img width="270" alt="image" src="https://user-images.githubusercontent.com/127544698/224572422-9b1eead6-1d1b-428c-98d6-04c39b2f112a.png">

<img width="250" alt="image" src="https://user-images.githubusercontent.com/127544698/224420531-25ad870b-b3ba-4ccd-96b4-286d088192ad.png">  <img width="270" alt="image" src="https://user-images.githubusercontent.com/127544698/224478445-e2f4e35c-eba2-4099-8f08-76c8b434c51e.png"> <img width="270" alt="image" src="https://user-images.githubusercontent.com/127544698/224572451-d7257cef-b9fc-4afd-96a5-a941f8b04d49.png">



Next we plot data for all countries for which complete information is available (why is much information in Apple mobility data missing in many countries?):

![Unknown](https://user-images.githubusercontent.com/127544698/226203516-c15d5eb3-45a5-463c-9f9f-748c06d28751.png)

We then calculate the correlation coefficients for all available countries and obtain:

<img width="394" alt="image" src="https://user-images.githubusercontent.com/127544698/226203613-3f9cdc14-5eab-4a19-bc75-1e1282928be7.png">

Apparently for most European countries (except Sweden and Norway) a very convincing correlation between the estimated CX and the reproduction numbers is found. We will continue further analysis with those countries which have an R2 value above 0.5: France, UK, Italy, Germany, Spain, Belgium, and Ireland.

1. Calculation of transmissibility
<img width="410" alt="image" src="https://user-images.githubusercontent.com/127544698/226457178-f896f4e3-deb8-4823-86b1-6fe751b592d4.png">

2. Calculation of most effective NPIs

to do
