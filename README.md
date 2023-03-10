# ContactIndex
### World-wide Contact Index during the SARS-CoV-2 pandemic

This is a first brief description of my Contact Index calculations based on mobility data. I use the Google and Apple mobility data that was publicaly availible together with the German Contact Index that can be found here:

https://contactindex.netcheck.de

With XGBoost I first calculated a fit of the German mobility data to the German CX. 

Then I use the resulting model to predict the Contact Index for other countries from their respective mobility data. A first analysis for the United Kingdom provided good correspondence to the (time-shifted) reproduction number.

Here is a preview for selected countries:

<img width="386" alt="image" src="https://user-images.githubusercontent.com/127544698/224420337-bf822124-3062-4764-910b-d10d94579233.png">

<img width="393" alt="image" src="https://user-images.githubusercontent.com/127544698/224420446-2f739ebe-9d34-4143-8d62-2ac3eebe2c62.png">

<img width="399" alt="image" src="https://user-images.githubusercontent.com/127544698/224420531-25ad870b-b3ba-4ccd-96b4-286d088192ad.png">

