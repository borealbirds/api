# Summaries from BAM National Model v4

https://borealbirds.github.io
https://borealbirds.ualberta.ca

## Species

The file lists the species for which results are available, 
it has the following fields:
	
- `id`: AOU code for the species
- `scientific`: scientific name for the species
- `english`: common name for the species in English
- `french`: common name for the species in French
- `family`: family for the species

## Abundance estimates by region

The file lists abundances (million males) and density estimates (males / ha) by region
(density = abundance / area), it has the following fields:

- `id`: AOU code for the species
- `scientific`: scientific name for the species
- `english`: common name for the species in English
- `region`: Canada, or Bird Conservation Regions within Canada
- `abundance_estimate`: mean abundance estimate
- `abundance_lower`: 5th percentile of bootstrap abundance estimate
- `abundance_upper`: 95th percentile of bootstrap abundance estimate
- `density_estimate`: mean density estimate
- `density_lower`: 5th percentile of bootstrap density estimate
- `density_upper`: 5th percentile of bootstrap density estimate
- `areakmsq`: area of region in km^2

## Density estimates by region and land cover class

The file lists density estimates (males / ha) by region and land cover class,
it has the following fields:

- `id`: AOU code for the species
- `scientific`: scientific name for the species
- `english`: common name for the species in English
- `region`: Canada, or Bird Conservation Regions within Canada
- `landcover`: North Americal land cover classes
- `estimate`: mean density estimate
- `lower`: 5th percentile of bootstrap density estimate
- `upper`: 95th percentile of bootstrap density estimate

## Validation

Validation metrics for species by region,
it has the following fields:

- `id`: AOU code for the species
- `scientific`: scientific name for the species
- `english`: common name for the species in English
- `region`: Canada, Bird Conservation Regions (BCR) or BCR subunits within Canada
- `prevalence`: number of non-zero counts divided by the number of counts in the region
- `run_complete`: number of bootstrap runs out of 32 (non-completion is due to lack of detection in the bootstrap sample)
- `AUC_init`: area under the receiver-operator characteristic (ROC) curve based on the constant density model with QPAD detectability offsets
- `AUC_final`: area under the receiver-operator characteristic (ROC) curve based on the final density model with QPAD detectability offsets
- `pseudo_R2`: deviance based pseudo R^2 assuming Poisson density and based on the final density model with QPAD detectability offsets
- `occc`: overall concordance correlation coefficient (OCCC) for agreement between completed bootstrap runs (`occc = oprec * oaccu`)
- `oprec`: overall precision
- `oaccu`: overall accuracy

## Variables

List of predictor variables used in the models,
it has the following fields:

- `variable`: predictor variable name
- `definition`: definition of the variable
- `resolution`: spatial resolution where applicable
- `source`: data source where applicable

## Variable importance

Variable importance values for each species/subregion combination, and as averages
for Canada, based on mean importance values from all the completed bootstrap runs,
it has the following fields:

- `id`: AOU code for the species
- `scientific`: scientific name for the species
- `english`: common name for the species in English
- `variable`: predictor variable name
- `region`: Canada, Bird Conservation Regions (BCR) or BCR subunits within Canada
- `importance`: average importance (0-1) describing how often the variable was selected in trees
