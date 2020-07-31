# Pump it Up: 
### Data Mining the Water Table
---

## Navigation
[#Contributors](Contributors) -
[#Sources](Sources) -
[#Overview](Overview) - 


-- 

## Contributors

- Raven Welch | (www.linkedin.com/in/Raven-Welch)[LinkedIn] | @RavenNHW
- Clair Marie Wholean |(https://www.linkedin.com/in/clairaia/)[LinkedIn] | @clairmarie8

## Sources 

Data was provided by (https://www.drivendata.org/competitions/7/pump-it-up-data-mining-the-water-table/page/23)[Driven Data], sourced from Taarifa and the Tanzanian Ministry of Water. 

Other research came from the following sources:
- (https://en.wikipedia.org/wiki/Water_supply_and_sanitation_in_Tanzania)[Wikipedia]
- (https://www.mdpi.com/2220-9964/6/8/244)[MDPI, Yola Georgiadou and Jeroen Verplanke]
- (https://www.jica.go.jp/english/news/focus_on/water/water_6.html)[Jica]
 
 ---
 
 ## Overview
 
 
 Tanzanian has the 6th largest population in Africa, with it's largest city, Dar es Salaam, being home to 6.7 million people. Not only that, but it's the 9th fastest growing city in the world. 
 
 ### The Problem
 
 Tanzania lacks a solid water structure, leaving many citizens without access to clean or safe access to water. There are waterpoints scattered throughout the country, of varying types with different collection systems, from rainwater to pulling up water from the ground. Additionally, many of these waterpoints are _broken_, and are either completely inoperative or functioning, but needing repair.
 
![Waterpoints by Status](/images/waterpoints_by_status.png)

And with further investigation, the distribution is wide accross the country, with many high-dentity areas containing a large number of broken or completely nonfunctional waterpoints.

![Broken Waterpoints](/images/broken_waterpoints_map.png) 

### Our Goal

Our aim is to predict the condition of a waterpoint for water management companies, to help prevent waterpoints from becoming completely non-functional. Ideally, any broken yet functioning waterpoints would be able to get repaired _before_ becoming nonfunctional, and we hope to make that possible with the power of machine learning.

### The Data

The dataset we used initially had 59,400 values, and was split up into a training set (used to develop the machine learning model) with 44,550 waterpoints, and a testing set with 14,850 values, used to see if the model is effective on data it has never seen before. 

After processing, the dataset was pruned leaving 8 columns with data on the waterpoint type, status, water quality, and water quantity.

Using that, we went through many iterations of differnet models and ended with choosing a Random Forest Classifier, as it was the most accurate. Overall, it was 73.3% accurate however when broken down into the different categories as seen below: 

- 82% of Waterpoints labeled as Non-Functional were correct
- 70% of Waterpoints labeled as Functional were correct
- 48% of Waterponits labeled as Functional, but needing repairs were correct

![Model Results](/images/model_results.png)

While the model performed fairly well with functional and nonfunctional waterpoints, it was about as good as flipping a coin in terms of determining if a waterpoint was functional but needed repairs. The source of this problem is the massive class imbalance, as there are far fewer waterpoints labeled as functioning but needing repairs compared to the other cateogries, as well as the history of inaccurate data collection, missing data, and inconsistancy with what data was recorded for this dataset.

-- 

## Reccomendations

After analyzing the data and model results, we have a few reccomendations in terms of data collection: 

- The focus of the data collection should be on improving features in relation to waterpoints and water quality
- The process should be streamlined as to not collect uneccessary data
- More data needs to be collected on functional waterpoints needing repair 
- None of the data collected should be subjective. Water salinity, parts per million, and PH should be collected. 

## Next Steps

- Methods to prevent waterpoint breakage should be determined, and shared with the communities who depend upon these water sources and the water management companies who manage the waterpoints.

- Determine features that affect function status

- Reduce the number of features used to predict waterpoint status

