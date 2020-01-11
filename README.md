# A Sparse Regression Approach for Evaluating and Predicting NHL Results

A more rigorous overview of the project can be found in the pdf, but below is a high level (and less technical) description.

## Motivation

This repository contains an early draft of a research project I worked on in undergrad at the University of Alabama. The motivation of this project was to:

* Develop models that can accurately predict NHL regular season stands and playoff results.
* Utilize model coefficients to better understand driving factors behind regular season and post-season success.
* Address the claim "Defense win championships."

## Data

Originally data was collected from the population NHL data aggregation site http://war-on-ice.com/. This is the datasource the paper is based off of; however, the site has since closed down with no new owners taking over maintenance of the site. I now have a dataset scraped from https://www.naturalstattrick.com/ that can be used to recreate the analysis.

The resulting modelling dataset ends up with over 1,000 features. Given the limited number of observations (teams * # years of data), our feature set is high-dimensional relative to our sample space. We use penalized regression techniques as our means of variable extraction.

## Code

Code used for data scraping, data cleaning, model building, model validation, and so on will be added to this repo at a later date.

## Approach

Models were developed to address three different scenarios:

1. Use regular season data to predict regular season standings
2. Use regular season data to predict postseason match winners
3. Use postseason data to predict postseason match winners

GLMs were developed for this purpose with the following variations:

* Different link functions were tested
* Different sparse regression techniques (Lasso, Ridge, Elastic Net) were used
* Hyperparameters were tuned to prioritize different metrics (sparsity of coefficients vs. minimizing RMSE)

## Results

The created models are able to predict NHL playoff success at least as well as existing naive approaches. Analysis on the coefficients that remain suggest that in the regular season offense is more predictive of defense of how good a team is. For the playoffs offense still appears to be more important, but by a much smaller margin. One explanation for this is that offense is a larger driver of which teams make the playoffs, so teams that make the playoffs have a larger variation in defensive ability than offensive ability which makes defense appears to be more important in the postseason.



