# Problem Definition

Predicting Relative Suitability for Rare Specialist Bees

Many pollinator species in North America are declining or poorly understood, and losses of these insects can threaten crop production and ecosystem function. In particular, rare specialist bees frequently have very few occurrence records, which limits the information conservationists have about where these species occur and when they are seasonally active. Identifying likely suitable habitat and seasonal activity windows is an important step toward understanding species’ conservation needs and informing habitat protection.

This project aims to predict the geographic regions and seasonal periods where rare specialist bee species are active. Models for this prediction can be trained using data from iNaturalist and survey data from the Rare Insect Conservation Program in Utah (hosted within the Utah Division of Wildlife Resources, funded by Utah State University).

A key idea in this prediction involves using information about host plants. For example, there are very few observations of the Colorado Calliopsis Bee (Calliopsis coloradensis) on iNaturalist. However, because the bee is a documented pollen specialist on Curlycup Gumweed (Grindelia squarrosa), then the much more abundant observations of the plant can help identify potential bee habitat. Combining bee observations, host-plant observations, and other data such as climate and geography could generate a catalog of relationships that predicts generalized locations of insect/host plant density. This would help biologists conduct targeted surveys where and when they would be most likely to observe these species.

The final product would be a relative suitability layer to be used in GIS software to guide field surveys for and support conservation decisions involving rare specialist bees.

The scope of the product will be limited to the western North America region. While each plant genus may have an extensive range, the bee species we will be producing relative suitability models for are specialized to the region east of the Missouri River/eastern Texas boundary, and not including Canada or Mexico. 

# Data Gathering

We will combine data from bee sighting records and host plant occurance records to produce the suitability models. Bee occurance records will be obtained for a set of 17 specialist bees from iNaturalist (https://www.inaturalist.org/home), the Bee Library (https://library.big-bee.net/portal/index.php), Ecdysis (https://ecdysis.org/collections/list.php) and the Global Biodiversity Information Facility (GBIF - https://www.gbif.org/).

Plant occurence data will be obtained from GBIF, swbiodiversity (https://swbiodiversity.org/seinet/collections/search/index.php) and iNaturalist. 

The Rare Insect Conservation Program has provided a spreadsheet with 17 specialist bee species and their known host plants.

# Data Assessment

## Volume and Coverage
Some specialist bees do not have sufficient records to be able to reliably train a model to predict their relative suitability, but many of the bees we will be considering have 200-4000 records combined in the above listed datasets, which should be sufficient for train-test splits. We will likely focus on developing a workflow for the bees which have the largest sets of records as those will be easier to assess, and then can consider applying those workflows to the more sparse bee records. Plant records will not be the limiting factor; GBIF alone often has tens of thousands of records for each host plant, though these records span large geographic regions and will need to be cleaned. 

One consideration is whether plant data records, which will span much larger regions than bee sighting records, should be cleaned to roughly match the geographic area of the bee sighting records. This can be tested in the initial exploratory data analysis.

## Bias and Representativeness
Bee sighting records are likely concentrated around regions with the easiest access, which certainly underrepresents the species suitable habitat. May be helpful to find a way to put that in the models, i.e. to possibly extrapolate beyond just where they were sighted initially. 

# Assessing Learnability

> Michael comment - I think that building an initial model on just Anthophora porterae would be a good start. It has a good data availability, it has one host plant Astragalus which has an extreme amount of data availability, and having only one host plant will simplify the initial analysis. Will also make it easier to determine what additional features are most useful for the model (weather data, geographic data, etc).

> Michael comment - Perdita coreopsidis would be another good start, with slightly higher complexity. It has high data availability and 3 primary host plants.

# KPI Definitions

> Michael comment - I am actually not sure what the best KPI for determining optimal models will be here. How do we evaluate a GLM combining things like weather data, sighting data etc? We are producing a probability distribution over the state of Utah, so I need to look into how we evaluate the "effectiveness" of this probability distribution on training data (since this isn't a classification problem).

Primary KPI -  

Secondary KPIs - Minimal features was noted as better as its cheaper for survey teams to collect? May need to check this with Amanda.
