# ContactIndex
### World-wide Contact Index during the SARS-CoV-2 pandemic

This is a first brief description of my Contact Index calculations based on mobility data. I use the Google and Apple mobility data that was publicaly availible together with the German Contact Index that can be found here:

https://contactindex.netcheck.de

With XGBoost I first calculated a fit of the German mobility data to the German CX. 

Then I use the resulting model to predict the Contact Index for other countries from their respective mobility data. A first analysis for the United Kingdom provided good correspondence to the (time-shifted) reproduction number.

Here is a preview for selected countries:

<img width="399" alt="image" src="https://user-images.githubusercontent.com/127544698/224412824-58624381-cb85-45c7-b442-10d2267f2d59.png">

<img width="394" alt="image" src="https://user-images.githubusercontent.com/127544698/224418262-c42437d5-a191-47ac-a70d-64c00d5d196e.png">

<img width="388" alt="image" src="https://user-images.githubusercontent.com/127544698/224418390-38cec8b9-fe8b-43a5-be56-97871503a1cc.png">

<img width="396" alt="image" src="https://user-images.githubusercontent.com/127544698/224413545-aa71a262-9a5e-4854-b247-b53a4f6fa003.png">

<img width="391" alt="image" src="https://user-images.githubusercontent.com/127544698/224413592-ee23173e-2ae2-43f3-bb2d-24c752e31ced.png">

