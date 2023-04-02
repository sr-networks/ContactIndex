# CXmob - Contact Index from mobility data
### 1 Global analysis of the Contact Index during the SARS-CoV-2 pandemic

This is a first description of Contact Index calculations based on mobility data. I used the Google and Apple mobility data that was publicaly availible together with the German Contact Index that can be found here:

https://contactindex.netcheck.de

- With XGBoost I first calculated a fit of the German mobility data to the German CX:

<img width="531" alt="image" src="https://user-images.githubusercontent.com/127544698/225931088-f2af6898-8bcb-4c04-bd4a-11877cc30e46.png">

- Overfitting is avoided by using k-fold cross-validation. 
- Then I use the resulting model to predict the Contact Index for other countries from their respective mobility data. 

Below are some preview charts for selected countries. 
- The first columns shows the evolution of CX over the entire time for which mobility data is availible (Apple stopped providing in April 2022). 
- The second column compares the CX evolution during the first year of the pandemic with that of the R values for the respective countries. Mostly good agreement (with the expected time delay for reporting) except for United States. 
- The third column compares CX with the Government Response Index (specifically the stringency index, which includes all containment and closure policy and one health information index). Note that the axis if GRI is inverted so that strong restrictions coincide with small CX. Data from https://github.com/OxCGRT/covid-policy-tracker

<img width="260" alt="image" src="https://user-images.githubusercontent.com/127544698/224420337-bf822124-3062-4764-910b-d10d94579233.png">  <img width="280" alt="image" src="https://user-images.githubusercontent.com/127544698/224478394-b04771b7-aa0b-4626-ae22-7066ebb83fe3.png"> <img width="280" alt="image" src="https://user-images.githubusercontent.com/127544698/224572358-7c4187a7-94bd-4f1e-bf5a-36b5db419257.png">

<img width="260" alt="image" src="https://user-images.githubusercontent.com/127544698/224420446-2f739ebe-9d34-4143-8d62-2ac3eebe2c62.png">  <img width="280" alt="image" src="https://user-images.githubusercontent.com/127544698/224478435-33f04127-383e-40df-bc42-ae5a94c3b57a.png"> <img width="280" alt="image" src="https://user-images.githubusercontent.com/127544698/224572422-9b1eead6-1d1b-428c-98d6-04c39b2f112a.png">

<img width="260" alt="image" src="https://user-images.githubusercontent.com/127544698/224420531-25ad870b-b3ba-4ccd-96b4-286d088192ad.png">  <img width="280" alt="image" src="https://user-images.githubusercontent.com/127544698/224478445-e2f4e35c-eba2-4099-8f08-76c8b434c51e.png"> <img width="280" alt="image" src="https://user-images.githubusercontent.com/127544698/224572451-d7257cef-b9fc-4afd-96a5-a941f8b04d49.png">


### 2 Plots of CX for all countries and comparision to the Oxford NPI index

Next we plot data for all countries for which complete information is available (why is much information in Apple mobility data missing in many countries?):

![Unknown](https://user-images.githubusercontent.com/127544698/226203516-c15d5eb3-45a5-463c-9f9f-748c06d28751.png)

### 3 Correlation of contacts with the (time-shifted) effective reproduction numbers

We then calculate the correlation coefficients for optimal time delay between CX and R (shown on the rhs) for all available countries and obtain:

<img width="396" alt="image" src="https://user-images.githubusercontent.com/127544698/229367172-d5dea30f-7509-4ac2-a706-eeeb5a4f703d.png"> <img width="392" alt="image" src="https://user-images.githubusercontent.com/127544698/229367251-0095f6db-4c1f-4d04-b8e5-b455723c186c.png">

Apparently for most European countries (except Sweden and Norway) a very convincing correlation between the estimated CX and the reproduction numbers is found. For other countries the R2 is much smaller. We interpret this as a too small prediction power of the mobility data (fitted to German contacts) for those countries, possibly because the mobility and transport behavior is very different from the central European countries.

We will continue further analysis with those countries which have an R2 value above 0.5: France, UK, Italy, Germany, Spain, Belgium, and Ireland.

### 4 Calculation of transmissibility

Transmissibility T is the probablity of transmission of the virus given the contact between and infected and an susceptible individdum. I have here used a scaled version of T, so that the value for wildtyp SC2 in a completely non-immune population is 1. Please find more information on the definition in https://www.medrxiv.org/content/10.1101/2023.03.02.23286502v1

<img width="450" alt="image" src="https://user-images.githubusercontent.com/127544698/226458496-cffcbe37-b430-4d2b-bf56-d1762d086cde.png"> <img width="440" alt="image" src="https://user-images.githubusercontent.com/127544698/226461336-4ccfe682-ea2e-42c5-9373-fd33036fb1de.png">

As in the case of Germany (rhs), we can see for most countries the T increasing effects of alpha, delta and omicron variants. As well, immunization (natural and vaccinated) drives down T from early 2021 on. 

### 5 Calculation of most effective NPIs

Now, what does it all mean for the assessment of NPIs during the SC2 pandemic? Ideally, after implementation of an NPI, the number of contacts should reduce. However, there are a few conceptual problems:

A - The contact numbers are reduced because of self-restriction following the news of increased case numbers.

B - Contact numbers could also be reduced after announcement of the NPI.

In fact, we generally found that CX decreased often before the NPI implimentaiton, so that in average no significant effect of the NPI may be conlcuded. (this even holds if the trend, or difference, in CX is considered and not the absolute value, see below)

It is thus hard to quantify the NPI. In the case A, one may conclude that the NPI is not neccessary. In B, we may check what happens with announcement of the NPI (data not shown).

Here is the evolution of the weekly CX trends compared to their repsective values four days before the NPI implementation:


<img width="500" alt="image" src="https://user-images.githubusercontent.com/127544698/229352089-980a8afe-e51b-4cbb-9ec6-8310dee8cfe0.png"> <img width="500" alt="image" src="https://user-images.githubusercontent.com/127544698/229352499-8a7f42e8-e804-48f2-9a1d-11d9cf7c34fa.png">

<img width="500" alt="image" src="https://user-images.githubusercontent.com/127544698/229352514-ff19c786-83f4-48d9-abdc-70cf3432337a.png"> <img width="500" alt="image" src="https://user-images.githubusercontent.com/127544698/229352528-4cd4cb69-23f6-486c-8ef7-60f6b15a39d6.png">

<img width="500" alt="image" src="https://user-images.githubusercontent.com/127544698/229352535-939d3ec8-9171-4cde-af61-1ffb0c74dcef.png"> <img width="500" alt="image" src="https://user-images.githubusercontent.com/127544698/229352540-59ad7bcc-577b-4359-86b7-0193bbcfc0c3.png">

<img width="490" alt="image" src="https://user-images.githubusercontent.com/127544698/229352547-e5aab9b4-7800-4612-b1bb-3d098553cfa0.png"> <img width="490" alt="image" src="https://user-images.githubusercontent.com/127544698/229352563-60a4c2f8-64fe-4729-b9d2-6df02e8f6e3d.png">






