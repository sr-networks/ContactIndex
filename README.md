# ContactIndex
### Contact Index for the countries of the world during the SARS-CoV-2 pandemic

This is a first description of my Contact Index calculations from mobility data. Briefly, I use the Google and Apple mobility data that was publicaly availible together with the German Contact Index that can be found here:

www.contactindex.netcheck.de

Using the XGBoost I calculated a fit of the German mobility data to the German CX. 

Then I use the resulting model to predict the Contact Index for other countries from their respective mobility data. A first analysis for the United Kingdom provided good correspondence to the (time-shifted) reproduction number.

<img width="399" alt="image" src="https://user-images.githubusercontent.com/127544698/224412824-58624381-cb85-45c7-b442-10d2267f2d59.png">

<img width="392" alt="image" src="https://user-images.githubusercontent.com/127544698/224413447-0ee9917d-2dc5-47a1-909d-65e70669c884.png">

<img width="398" alt="image" src="https://user-images.githubusercontent.com/127544698/224413502-ea72bc64-97b5-437e-9ca4-d2d9b33457ca.png">

<img width="396" alt="image" src="https://user-images.githubusercontent.com/127544698/224413545-aa71a262-9a5e-4854-b247-b53a4f6fa003.png">

<img width="391" alt="image" src="https://user-images.githubusercontent.com/127544698/224413592-ee23173e-2ae2-43f3-bb2d-24c752e31ced.png">

