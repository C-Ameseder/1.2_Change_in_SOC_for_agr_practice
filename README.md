<img src="https://github.com/C-Ameseder/1.2_Change_in_SOC_for_agr_practice/blob/main/6.Images/1.SOC_in_perenials_dahboard.png" alt="SOC in Dataset" width="800"/>

# Unlock the power of our agricoultural soils
This project predicts the change in soil organic carbon using data on agriculutral practice, soil data and environmental data, aiming to predict the carbon storage capacities worldwide using the No-Dig method as agricultural practivce.  
Christoph Ameseder

## Content
- [Project Description](#project-description)
- [Hypotheses / Questions](#hypotheses-questions)
- [Dataset](#dataset)
- [Cleaning](#cleaning)
- [Analysis](#analysis)
- [Model Training and Evaluation](#model-training-and-evaluation)
- [Conclusion](#conclusion)
- [Future Work](#future-work)
- [Workflow](#workflow)
- [Validation](#validation)
- [Links](#links)

## Project Description
80 percent of Carbon is binded in the soil, the majority as organic carbon, only a small part is in the atmosphere. If we would be able to increase the capacity of agricultural soils to mitigate atmospheric carbon we not only would address the issue of climate change, but as well the problem of soil degradation and desertification. Own field trials in Berlin using the No-Dig method represented by Charles Dowding show that no-till and no-dig practices in combination with a annual application of compost (around 10cm/4inch each year) can increase the soil organic carbon content) We use agricultural data for perennials in combination with doil data and environmental climate data in order to predict soil organic carbon for different soil types in different climate zones

## Hypotheses / Questions
* What are the important factors that determine the carbon content of soils worldwide?
* Can we predict soil organic carbon using publicly available datasets?
* Does no-dig or no-till has an impact on the SOC content? 
* Is there an influence of the type of fertilizers on the soil organic content (organic/non-organic)
* Can we use the model to predict the carbon binding capacities under No-Dig agricultural practice?


## Dataset
We used a dataset of 1600 observations (cumulated of several soil profiles) of 180 studies in 32 countries where there has been a switch to agricultural produce using perennial crops. We combined these data with physical and chemical features of the respective soil profiles using the WOSIS database 2019. For environmental and climate factors we used the Worldclim database version2.


## Cleaning
One of the main problems in this observation is that different measures are used to measure SOC in different layers. Although we had a measure for all observations, there is no direct way to calculate SOC out of the respective other measure. We overcame this by generating a small dataframe with limited features and used KNN Imputer to impute the missing values. Describe your full process of data wrangling and cleaning. By doing so we gave a lot of weight to the SOC measure and tried to limit the bias.

## Analysis
Our first dataset of different studies worldwide was highly sparced, therefore we could not come up with a valid model. After merging the dataset with soil and environmental data we could predict SOC using a random forest model.
However, human factors such as no-till and fertilizer type show low influence on target and high p values. We ran some subset analysis but came to the conclusion that we cannot reject the null hypothesis here, namely: human factor has not influence on SOC.

Feature selection was done by correlation on the target using pandas profiling and some calculation of some correlation measures. Later we check for multicollinearity.
Some features have then be dropped due to high p-values in OLS

## Model Training and Evaluation
One of the research questions was to evaluate which factors are important, which is why we used random forest, as we can easily determine the importance of every factor using this model. Further model improvement has not been done, as the dataset on human factors influencing the SOC content has not been sufficient. For the prediction of the SOC for no-dig method further observations are necessary.

## Conclusion
* We can predict SOC levels in soils worldwide using soil and environmental measures
* The influence of not-till or the type of fertilizer could not be included in the model, we could not reject the null hypothesis
* We therefore can not predict the SOC content for agricultural soils worldwide applying the no-dig method

## Future Work
From case studies we know that we can dramatically increase the SOC content - one of the most promising methods is the No-Dig-method. Unfortunately although in small scale this method recently gained a lot of attention, data on that is still missing. Current agricultural practice rarely using compost as fertilizer which is the main reason why we do not have data on that important feature. We therefore call for measuring SOC content andattain soil profiles for places, where no=dig has been applied for several years.

## Workflow
We had an iterative process and run several models on different parts of the datasets, in order to deal with highly sparced data and to get a first estimate of the importance of features. We then accumulated data from the environment data and soil data. Google colab notebooks that are only partly uploaded. After merging all data sources correctly we did a correlation analysis of all features on the target and eliminated features. Second we checked for multicollinearity and dropped some further features.

## Validation
The algorithm was tested on some smaller datasets from agricultural sites in Canada




## Links



[Repository](https://github.com/C-Ameseder/1.2_Change_in_SOC_for_agr_practice/)   
[Slides](https://prezi.com/p/adl5ei_ty8wb/carbon-sequestration-for-agricultural-soils/?present=1/)    
[Dashboard](https://public.tableau.com/profile/christoph7221#!/vizhome/SOC-perenials/Dashboard1?publish=yes)   
[PersonalWebsite](https://christophameseder.com)    
[LinkedIn](https://linkedin.com/in/christoph-ameseder.com) 
