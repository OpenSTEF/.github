## Hi there 👋

<!--

**Here are some ideas to get you started:**

🙋‍♀️ A short introduction - what is your organization all about?
🌈 Contribution guidelines - how can the community get involved?
👩‍💻 Useful resources - where can the community find your docs? Is there anything else the community should know?
🍿 Fun facts - what does your team eat for breakfast?
🧙 Remember, you can do mighty things with the power of [Markdown](https://docs.github.com/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
-->

# OpenSTEF 
OpenSTEF provides automated machine learning pipelines to deliver accurate, self-correcting and explainable forecasts of the load on the grid for the next 48 hours.
**add image**

## Description
The energy transition poses new challenges to all parties in the energy sector. For grid operators, the rise in renewable energy and electrification of energy consumption leads to the capacity of the grid to near its physical constraints. Forecasting the load on the grid in the next hours to days is essential for anticipating on local congestion and making the most of existing assets.  

OpenSTEF provides a complete software stack which forecasts the load on the electricity grid for the next hours to days. Given a timeseries of measured (net) load or generation, a fully automated machine learning pipeline is executed which delivers a probabilistic forecast of future load. This works for energy consumption, (renewable) generation or a combination of both. OpenSTEF performs validation on the input data, combines measurements with external predictors such as weather data and market prices, trains any scikit-learn compatible machine learning model, and delivers the forecast via both an API and an (expert) graphical user interface. The stack is based on open source technology and standards and is organized in a microservice architecture optimized for cloud-deployment.

The Dutch DSO Alliander started the Short-Term-Forecasting project to anticipate congestion in the distribution grid, to allow for grid safety analysis in the transmission grid and to enable smart grid innovations to locally balance supply and demand within the constraints of the grid. By opensourcing the stack, the ambition is to provide an industry standard for generating and evaluating forecasts in the operational time-domain, as well as allow for structured collaboration.

**add image**
Screenshot of the operational dashboard showing the key functionality of OpenSTEF

Repositories
OpenSTEF	Automated Machine Learning Pipelines. Builds the Open Short Term Forecasting package
OpenSTEF-dbc	Provides (company specific) database connector for the OpenSTEF package
OpenSTEF-offline-example	
Provides Jupyter Notebooks showing how to use OpenSTEF and apply it's functionality to your usecase
OpenSTEF-reference	Deploy the entire OpenSTEF stack on your machine. Provides a reference implementation of the OpenSTEF stack
