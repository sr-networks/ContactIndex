# ContactIndex
### World-wide Contact Index during the SARS-CoV-2 pandemic

This is a first brief description of my Contact Index calculations based on mobility data. I use the Google and Apple mobility data that was publicaly availible together with the German Contact Index that can be found here:

https://contactindex.netcheck.de

With XGBoost I first calculated a fit of the German mobility data to the German CX. 

Then I use the resulting model to predict the Contact Index for other countries from their respective mobility data. A first analysis for the United Kingdom provided good correspondence to the (time-shifted) reproduction number.

Below are some preview charts for selected countries. The first columns shows the evolution of CX over the entire time for which mobility data is availible (Apple stopped providing in April 2022). The second column compares the CX evolution with that of the R values for the respective countries. Mostly good agreement (with the expected time delay for reporting) except for United States. Presumably mobility and contact behavior is too different from that of European countries for the Germany-based model to be useful. 

<img width="386" alt="image" src="https://user-images.githubusercontent.com/127544698/224420337-bf822124-3062-4764-910b-d10d94579233.png">  <img width="422" alt="image" src="https://user-images.githubusercontent.com/127544698/224478394-b04771b7-aa0b-4626-ae22-7066ebb83fe3.png">


<img width="393" alt="image" src="https://user-images.githubusercontent.com/127544698/224420446-2f739ebe-9d34-4143-8d62-2ac3eebe2c62.png"> <img width="425" alt="image" src="https://user-images.githubusercontent.com/127544698/224478435-33f04127-383e-40df-bc42-ae5a94c3b57a.png">


<img width="399" alt="image" src="https://user-images.githubusercontent.com/127544698/224420531-25ad870b-b3ba-4ccd-96b4-286d088192ad.png"> <img width="421" alt="image" src="https://user-images.githubusercontent.com/127544698/224478445-e2f4e35c-eba2-4099-8f08-76c8b434c51e.png">


