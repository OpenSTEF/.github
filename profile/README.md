# OpenSTEF - Open Short Term Energy Forecasting
[![License: MPL2.0](https://img.shields.io/badge/License-MPL2.0-informational.svg)](https://github.com/openstef/openstef/blob/main/LICENSE)
[![CI Best Practices](https://bestpractices.coreinfrastructure.org/projects/5585/badge)](https://bestpractices.coreinfrastructure.org/projects/5585)
[![Downloads](https://static.pepy.tech/badge/openstef)](https://pepy.tech/project/openstef)
[![Downloads](https://static.pepy.tech/badge/openstef/month)](https://pepy.tech/project/openstef)

OpenSTEF is an open-source Python package for probabilistic short-term energy forecasting. It provides automated machine learning workflows to deliver accurate forecasts of the load on the grid for any horizon, typically from hours to days ahead. Infused with expert energy knowledge, the package incorporates external predictors such as weather data and market prices, ensuring validation and training of machine learning models to provide precise, probabilistic load predictions.

# Table of Contents
- [External information sources](#external-information-sources)
- [Description](#description)
- [Repositories](#repositories)
- [License](#license)
- [Contributing](#contributing)
- [Contact](#contact)


## Description
The energy transition poses new challenges to all parties within the energy sector. Grid operators, grappling with the upsurge in renewable energy and heightened electrification, find their grid capacities nearing physical limitations. Therefore, it is imperative to forecast grid load in the upcoming hours to days, enabling the anticipation of local congestion and thereby optimal utilization of existing assets.  

Given a timeseries of measured (net) load or generation, OpenSTEF executes a forecasting workflow that produces probabilistic predictions. This is applicable to energy consumption, renewable generation, or a combination of the two. See the [documentation](https://openstef.github.io/openstef/index.html) for a full feature overview and getting started guide.

The Dutch DSO Alliander started the Short Term Forecasting project to anticipate congestion in the distribution grid, to allow for grid safety analysis in the transmission grid and to enable smart grid innovations to locally balance supply and demand within the constraints of the grid. The objective of opensourcing the stack is two-fold: provide an industry standard for generating and evaluating forecasts in the operational time-domain, as well as allow for structured collaboration.

## Repository

[OpenSTEF](https://github.com/OpenSTEF/openstef): Main repository. Organized as a monorepo with specialized packages for the complete forecasting stack. See the [repository README](https://github.com/OpenSTEF/openstef#readme) for a full overview of packages, installation instructions, and examples.

## Features
- Workflows: automated machine learning workflows encapsulating the full train/predict cycle: preprocessing, model training and inference, and postprocessing. Configured via a workflow config specifying model type, forecast horizons, quantiles, location metadata, and feature engineering settings.
- Feature engineering: a modular transform system constructing features for training and forecasting, including time-based lags, rolling aggregates, weather features, and holiday indicators.
- Machine learning: multiple built-in models including XGBoost, LightGBM, and linear gradient boosting variants.
- Data validation: checks input data for completeness, flatline periods, and consistency before training or forecasting.
- Probabilistic forecasting: forecasts are delivered as quantile predictions across configurable confidence levels, providing uncertainty estimates alongside the central prediction.
- Energy splitting: ability to split the load forecast into solar, wind and load components, using a pluggable component splitter framework.

## License
This project is [licensed](https://github.com/OpenSTEF/.github/blob/main/LICENSE) under the Mozilla Public License, version 2.0.

## Contributing
Please read [CODE_OF_CONDUCT.md](https://github.com/OpenSTEF/.github/blob/main/CODE_OF_CONDUCT.md), [CONTRIBUTING.md](https://github.com/OpenSTEF/.github/blob/main/CONTRIBUTING.md) and [PROJECT_GOVERNANCE.md](https://github.com/OpenSTEF/.github/blob/main/PROJECT_GOVERNANCE.md) for details on the process for submitting pull requests to us.

## Contact
Please read [SUPPORT.md](https://github.com/OpenSTEF/.github/blob/main/SUPPORT.md) for how to connect and get into contact with the OpenSTEF project.


## External information sources
- [Documentation](https://openstef.github.io/openstef/index.html)
- [Python package](https://pypi.org/project/openstef/)
- [Project website](https://www.lfenergy.org/projects/openstef/)
- [Video about OpenSTEF](https://www.lfenergy.org/forecasting-to-create-a-more-resilient-optimized-grid/)
- [OpenSTEF Slack channel](https://slack.lfenergy.org/)