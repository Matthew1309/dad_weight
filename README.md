# This repository will contain the dad_weight project.

My dad who has been trying to lose weight has also been keeping notes of his progress. Here I include his raw notes and a script that will walk you 
through some basic data analysis.

1. Plotting data
2. Basic stats of data
3. Slope of data
4. Modeling weight loss
5. Predictions of future weight

# Chronolog
## 4/20/2023
I updated the weight tracking up through today. Needed to adjust some of the regex to handle his new format, but I didnt' re-read everything, just lines 350 down. Additionally, I wanted to model his weight, this weight loss rate, and his weight loss accelaration. The first 220 days or so of the weight loss accelaration journey appeared to follow a sin curve, and the model looks really decent!

I then took a couple integrals to predict what the other two features would look like. I used `curve_fit` and `find_peak` to make an observation that my dad seems to go through 100 day cycles of active weight loss or weight gain. Very interesting.

Actually looking at the acceleration graph, rationally it would make sense if it was a damped sine wave! because ultimately what we want is a steady downward slope, but when you first start dieting, you are full of motivation and you can do that super fast aggressive weight loss, but then you cool off and start getting in the groove and don't want to feel the hunger pangs, so you don't dip so hard into the peaks and troughs. This should continue until you reach a somewhat steady state (no accelaration). To achieve this, I think we need to add some sort of $e^x$ term. Look up damped sine waves and see if they fit!

