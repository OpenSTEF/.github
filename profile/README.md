# OpenSTEF - Open Short Term Energy Forecasting
[![License: MPL2.0](https://img.shields.io/badge/License-MPL2.0-informational.svg)](https://github.com/openstef/openstef/blob/main/LICENSE)
[![CII Best Practices](https://bestpractices.coreinfrastructure.org/projects/5585/badge)](https://bestpractices.coreinfrastructure.org/projects/5585)

OpenSTEF provides automated machine learning pipelines to deliver accurate and explainable forecasts of the load on the grid for the next 48 hours. Infused with expert energy knowledge, the platform incorporates external predictors such as weather data and market prices, ensuring validation and training of machine learning models to provide precise load predictions.

# Table of Contents
- [External information sources](#external-information-sources)
- [Description](#description)
- [Repositories](#repositories)
- [License](#license)
- [Contributing](#contributing)
- [Contact](#contact)

## External information sources
- [Documentation](https://openstef.github.io/openstef/index.html);
- [Python package](https://pypi.org/project/openstef/);
- [Project website](https://www.lfenergy.org/projects/openstef/);
- [Dashboard documentation](https://raw.githack.com/OpenSTEF/.github/main/profile/html/openstef_dashboard_doc.html);
- [Linux Foundation project page](https://openstef.github.io/openstef/index.html);
- [Video about OpenSTEF](https://www.lfenergy.org/forecasting-to-create-a-more-resilient-optimized-grid/);
- [Teams channel](https://teams.microsoft.com/l/team/19%3ac08a513650524fc988afb296cd0358cc%40thread.tacv2/conversations?groupId=bfcb763a-3a97-4938-81d7-b14512aa537d&tenantId=697f104b-d7cb-48c8-ac9f-bd87105bafdc). 


## Description
The energy transition poses new challenges to all parties within the energy sector. Grid operators, grappling with the upsurge in renewable energy and heightened electrification, find their grid capacities nearing physical limitations. Therefore, it is imperative to forecast grid load in the upcoming hours to days, enabling the anticipation of local congestion and thereby optimal utilization of existing assets.  

OpenSTEF provides a complete software stack specifically engineered to forecast the load on the electricity grid for the next hours to days. Given a timeseries of measured (net) load or generation, a fully automated machine learning pipeline is executed which delivers a probabilistic forecast of future load. This is applicable to energy consumption, renewable generation, or a combination of the two. OpenSTEF does not stop at forecating: it validates input data, combines measurements with external predictors such as weather data and market prices, trains any scikit-learn compatible machine learning model, and delivers the forecast via both an API and an (expert) graphical user interface. The entire stack, crafted on open-source technology and adhering to standards, is organized in a microservice architecture optimized for cloud-deployment.

The Dutch DSO Alliander started the Short-Term-Forecasting project to anticipate congestion in the distribution grid, to allow for grid safety analysis in the transmission grid and to enable smart grid innovations to locally balance supply and demand within the constraints of the grid. The objective of opensourcing the stack is two-fold: provide an industry standard for generating and evaluating forecasts in the operational time-domain, as well as allow for structured collaboration.
![Forecast highligts](https://user-images.githubusercontent.com/18208480/127109029-77e09c97-8d06-4158-8789-4c1d5ecede61.png "Example of the OpenSTEF dashboard")
## Repositories 
OpenSTEF has different repositories. 

[OpenSTEF](https://github.com/OpenSTEF/openstef): Basis of all the repositories. Automatic machine learning pipelines. Builds the Opensource Short Term Forecasting package. 

[OpenSTEF-dbc](https://github.com/OpenSTEF/openstef-dbc): Provides (company specific) database connector for OpenSTEF package.

[OpenSTEF-reference](https://github.com/OpenSTEF/openstef-reference): Deploy the entire OpenSTEF stack on your machine. Provides a reference implementation of the OpenSTEF stack including datamodels, databases and UI.  

[OpenSTEF-offline-example](https://github.com/OpenSTEF/openstef-offline-example): Provides Jupyter Notebooks showing how to use OpenSTEF and apply it's functionality to your usecase.

## Framework features 
- Prediction job: input configuration for a task or pipeline. It contains for example the location and forecasting horizon.
- Feature engineering: is called by pipelines to select required features for training/forecasting based on the configuration from the prediction job (e.g. create new features for energy load of yesterday, last week). 
- Machine learning: is called by pipelines to perform training, forecasting, or evaluation based on the configuration from the prediction job (e.g. train an XGB quantile model).
- Pipelines: OpenSTEF contains automated machine learning pipelines. Can be called to perform training, forecasting or evaluating by giving input data to the pipeline.
- Data validation: called by pipelines to validate data. 
- Confidence estimates: there are two methods for confidence estimation: quantile regression and standard deviation.  
- Energy splitting: ability to split the load forecast into solar, wind and load. Uses the Domain Adaption for Zero Shot Learning in Sequence (DAZLS), which is a technique which transfers knowledge from complete information substations to incomplete information substations. 

## License
This project is licensed under the Mozilla Public License, version 2.0.

## Contributing
Please read [CODE_OF_CONDUCT.md](https://github.com/OpenSTEF/.github/blob/main/CODE_OF_CONDUCT.md), [CONTRIBUTING.md](https://github.com/OpenSTEF/.github/blob/main/CONTRIBUTING.md) and [PROJECT_GOVERNANACE.md](https://github.com/OpenSTEF/.github/blob/main/PROJECT_GOVERNANCE.md) for details on the process for submitting pull requests to us.

## Contact
Please read [SUPPORT.md](https://github.com/OpenSTEF/.github/blob/main/SUPPORT.md) for how to connect and get into contact with the OpenSTEF project.
