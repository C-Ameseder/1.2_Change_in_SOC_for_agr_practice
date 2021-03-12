<img src="https://github.com/C-Ameseder/1.2_Change_in_SOC_for_agr_practice/blob/main/6.Images/1.SOC_in_perenials_dahboard.png" alt="SOC in Dataset" width="800"/>

# 1.2_Change_in_SOC_for_agr_practice
This project predicts the change in soil organic carbon using data on agriculutral practice, soil data and environmental data
Christoph Ameseder

*[Your Cohort, Campus & Date]*

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
- [Organization](#organization)
- [Links](#links)

## Project Description
80 percent of Carbong is binded in the soil, the majority as organic carbon, only a small part is in the athmospehre. If we woul be able to increase the capacity of agricultural soils to mitigate athmospheric carbon we not only would address the issue of climate change, but as well the problem of soil degeneration and dessertification. Own field trials in Berlin using the No+Dig method represented by Charles Dowding show that no-till and no-dig practices in combination with a annual application of compost (around 10cm/4inch each year) can increase the soil organic carbon content) We use agircultural data for perennials in combination with doil data and environmental climate data in order to predict soil organic carbon for different soil types in different climate zones

## Hypotheses / Questions
* What are the important factors that determine the carbon content of soils worldwide?
* Can we predict soil organic carbon using publicly available datasets?
* Does no-dig or no-till has an impact on the SOC content? 
* Is there an influence of the type of fertlizers on the soil organic content (organic/non-organic)
* Can we use the model to predict the carbon binding capacitites under No-Dig agricultural practice?


## Dataset
We used a dataset of 1600 observations (cummulated of several soil profiles) of 180 studies in 32 countries where there hase been a switch to agricultural produce using perennial crops. We combinded these data with physical and chemical features of the respective soil prifiles using hte WOSIS database 2019. For environmental and climate factores we used the Worldclim database version2.


## Cleaning
One of the main probelms in this observation is that different measures are used to measure SOC in different layers. Although we had a measure for all observation, there is not direct way to calculate SOC out of the respective other measure. We overcome this by generating a small dataframe with limited features and used KNN Imputer to impute the missing values. Describe your full process of data wrangling and cleaning. By doing so we gave a ot of weight to the SOC meausre and tried to limit the bias.

## Analysis
Our first datasety of different studies worldwide was highly sparced, therefore we could not come up with a valid model. After merging the dataset with soil and envrionmental data we could predict SOC using a random forest model.
However, human factos such as no-till and fertiliyer type show low influence on target and high p values. We ran some subset analysis but came to the conclusion that we cannot reject the null hzpothesis here, namely: human factor has not influence on SOC.

Feature selection was done by correaltion on the target using poandas profiling and some the calcualtion of some correlation measures. Later we checke for multicolinearity.
Some features have then be droped due to high p-values in OLS

## Model Training and Evaluation
One of the research questions was to evaluate whoich factors are important, which is why we used random forest, as we can easily determine the importacne of every factor using this model. Further mdoel improovement has not been done, as the dataset on human factors influencing the SOC content has not been sufficient. For the predicton of the SOC for no-dig method further onservations are necessary.

## Conclusion
* We can predict SOC levels in soils worldwide using soil and environmetnal measures
* The influence of not-till or the type of fertilzer could not be ncluded in the model, we could not reject the null hypotehsis
* We therefore can not predict the SOC content for agricultural soils wordwide applyin the no-dig method

## Future Work
From case studies we know that we can dramatically increase the SOC content - one of the most promissing methods is the No-Dig-method. Unfortunately although in small scale this method recently gained a lot of attention, data on that is still missing. Current agricultural practice rarely using compost as fertilizer which is the main reason why we do not have data on that important feature. We therefore call for measuring SOC content andattain soil profiles for places, where no=dig has been applied for severl years.

## Workflow and Validation
We had an iterative process and run several models on different parts of the datasets, in order to deal with highly sparced data and to get a first estimate of the importance of features. We then cummulated data from the enviromnet data and soil data. Google colab notebooks on that are only partly uplaoded. After merging all data sources correctly we did a correlation analysis of all features on the target and eliminated features. Second we checked for mulitcolinearity an dropped some further features.

## Validation
The algorithm was testes on some smaller dstasets from agricultural sites in Canada



## Links



[Repository](https://github.com/C-Ameseder/1.2_Change_in_SOC_for_agr_practice/) 
[Personal_website] (https://christophameseder.com/)
[Slides](https://prezi.com/p/adl5ei_ty8wb/carbon-sequestration-for-agricultural-soils/?present=1/)  
[Dashboard](https://public.tableau.com/profile/christoph7221#!/vizhome/SOC-perenials/Dashboard1?publish=yes) 
