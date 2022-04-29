# OpenSTEF - Open Short Term Energy Forecasting
[![License: MPL2.0](https://img.shields.io/badge/License-MPL2.0-informational.svg)](https://github.com/openstef/openstef/blob/main/LICENSE)
[![CII Best Practices](https://bestpractices.coreinfrastructure.org/projects/5585/badge)](https://bestpractices.coreinfrastructure.org/projects/5585)

OpenSTEF provides automated machine learning pipelines to deliver accurate, self-correcting and explainable forecasts of the load on the grid for the next 48 hours.

![Forecast highligts](https://user-images.githubusercontent.com/18208480/127109029-77e09c97-8d06-4158-8789-4c1d5ecede61.png)

Find the latest information on the project on [the projects website](https://wiki.lfenergy.org/display/OS/OpenSTEF).

Want to join the discussion? Join our [Teams channel](https://teams.microsoft.com/l/team/19%3ac08a513650524fc988afb296cd0358cc%40thread.tacv2/conversations?groupId=bfcb763a-3a97-4938-81d7-b14512aa537d&tenantId=697f104b-d7cb-48c8-ac9f-bd87105bafdc).

You can also watch a [video about OpenSTEF](https://www.lfenergy.org/forecasting-to-create-a-more-resilient-optimized-grid/) instead of reading about the project



## Description
The energy transition poses new challenges to all parties in the energy sector. For grid operators, the rise in renewable energy and electrification of energy consumption leads to the capacity of the grid to near its physical constraints. Forecasting the load on the grid in the next hours to days is essential for anticipating on local congestion and making the most of existing assets.  

OpenSTEF provides a complete software stack which forecasts the load on the electricity grid for the next hours to days. Given a timeseries of measured (net) load or generation, a fully automated machine learning pipeline is executed which delivers a probabilistic forecast of future load. This works for energy consumption, (renewable) generation or a combination of both. OpenSTEF performs validation on the input data, combines measurements with external predictors such as weather data and market prices, trains any scikit-learn compatible machine learning model, and delivers the forecast via both an API and an (expert) graphical user interface. The stack is based on open source technology and standards and is organized in a microservice architecture optimized for cloud-deployment.

The Dutch DSO Alliander started the Short-Term-Forecasting project to anticipate congestion in the distribution grid, to allow for grid safety analysis in the transmission grid and to enable smart grid innovations to locally balance supply and demand within the constraints of the grid. By opensourcing the stack, the ambition is to provide an industry standard for generating and evaluating forecasts in the operational time-domain, as well as allow for structured collaboration.

Dashboard documentation can be found [here](https://raw.githack.com/OpenSTEF/.github/main/profile/html/openstef_dashboard_doc.html).
[![here](https://user-images.githubusercontent.com/60883372/146760483-29af3ac7-62af-4f13-98c7-982a79c517d1.jpg)](https://raw.githack.com/OpenSTEF/.github/main/profile/html/openstef_dashboard_doc.html)
Screenshot of the operational dashboard showing the key functionality of OpenSTEF

## License
This project is licensed under the Mozilla Public License, version 2.0.

## Contributing
Please read [CODE_OF_CONDUCT.md](https://github.com/OpenSTEF/.github/blob/main/CODE_OF_CONDUCT.md), [CONTRIBUTING.md](https://github.com/OpenSTEF/.github/blob/main/CONTRIBUTING.md) and [PROJECT_GOVERNANACE.md](https://github.com/OpenSTEF/.github/blob/main/PROJECT_GOVERNANCE.md) for details on the process for submitting pull requests to us.

## Contact
Please read [SUPPORT.md](https://github.com/OpenSTEF/.github/blob/main/SUPPORT.md) for how to connect and get into contact with the OpenSTEF project
