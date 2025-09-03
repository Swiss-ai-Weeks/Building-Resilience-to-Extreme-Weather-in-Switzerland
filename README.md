# Welcome to "AI for Resilience against Extreme Weather Events" by Swiss Re
This respository is part of the Zurich hackathon of [Swiss {ai} Week](https://swiss-ai-weeks.ch/) happening on 26/27 September 2025.

## Introduction
The recent tragedy of glacier collapse in Blatten and the increasing summer heatwaves underscore the vulnerabilities in the Swiss Alps. In this evolving risk landscape, the reinsurance industry plays a crucial role in helping societies understand and manage the financial impact of natural disasters such as landslides, floods, and heatwaves.  

AI-driven technologies open up new opportunities for the (re)insurance industry to take societal responsibility in responding to natural catastrophes. With this hackathon, Swiss Re aims to explore innovative ways to turn these opportunities into concrete solutions that enhance resilience and create tangible benefits for society. 

This document provides an overview of Swiss Re's hack challenge and potential solution designs, risk and insurance inputs for better scoping and pointers to datasets and other resources that you can leverage.  

# Hackathon Challenge 
Welcome to the Hackathon on **AI for Resilience against Extreme Weather Events**!  The aim of this challenge is to use data and technology to enable Swiss society to build resilience to extreme weather events. You are encouraged to design any solution that contributes to this goal. The ideas below illustrate some possible directions you might pursue, yet you are just as welcome to think beyond them and propose something entirely new: 

Your solutions might include:
- **Innovative Parametric Insurance Solutions**: Design and prototype a parametric insurance model with innovative trigger mechanism based on real-time environmental data (e.g. extreme temperature index). Simulate payout scenarios based on historical or synthetically created datasets. The payout does not need to be financial - think of what would bring instant relief to society, e.g. during a heatwave! 
- **AI-Powered Early Warning Systems**: Thinking of individuals living or travelling through Switzerland, design and prototype an AI-powered application enabling to better apprehend selected risks (e.g., landslides or glacier collapses) and issuing warnings or relevant mitigation recommendations based on the user location. The AI model should be able to leverage multimodal data ranging from weather to topological data and assume the user's location as known. 
- **Intelligent Disaster Response Systems** Prototype a platform for real-time disaster coordination with integration of open source exposure data and optimized resource allocation in case of a disaster. Conduct damage assessment of natural hazards (e.g., floods, hail, windstorms, precipitation) on properties from street view or satellite imagery. The tool should help identify where the most significant losses/damage might occur. For example, in areas with high concentration of rooftop solar panels, older and more vulnerable buildings, or other exposure characteristics that increase susceptibility to damage.   
- **Any other solutions**: Be creative and feel free to think and build completely out of the box!

## Risk Inputs for Scoping
Swiss communities face a wide range of natural hazards, each with different impacts on people and health, property, and agriculture.  

### Hazard / Exposure mapping (risk scenarios) 
The table below provides examples of how selected hazards can affect these areas of exposure. While not exhaustive, it illustrates the variety of risks and consequences across lines of business. To make your solution both relevant and feasible, we recommend focusing on one specific hazard-exposure intersection which represents a concrete risk scenario, e.g., floods × property damage or hail × agriculture. 

| Hazards ↓ / Exposures → | People & Health                          | Property damage                                                                 | Agriculture                                |
|--------------------------|------------------------------------------|---------------------------------------------------------------------------------|--------------------------------------------|
| **Flood**               | Evacuation, injuries, fatalities         | Property (buildings) & infrastructure damage (Power grid, bridges, roads, railway lines) | Crop loss, forest loss                      |
| **Windstorm**           | Injuries, fatalities                     | Property (buildings) & infrastructure damage (Power grid), road blockages from trees | Crop loss, forest loss                      |
| **Convective storms (hail)** | Injuries, fatalities                | Property (buildings, solar panels) damage, motor damage                         | Crop loss depending on the growing season   |
| **Earthquakes** (not climate-driven but relevant in Switzerland) | Injuries, fatalities | Property (buildings) & infrastructure damage (Power grid, bridges, roads, railway lines) | Crop loss, forest loss through indirect impacts e.g. landslides |
| **Landslides**          | Injuries, fatalities                     | Property (buildings) & infrastructure damage (Power grid, bridges, roads, railway lines) | Crop loss, forest loss                      |
| **Drought**             | Water shortage                           | Property & infrastructure damage from subsidence depending on the soil conditions | Crop loss, forest dieback                   |
| **Heat wave**           | Health issues                            | Power grid failures, potentially affecting other infrastructures                | Crop loss, forest dieback                   |

### Useful References
- [GMD - CLIMADA v1](https://gmd.copernicus.org/articles/12/3085/2019/): a global weather and climate risk assessment platform 
- [GitHub - CLIMADA-project](https://github.com/CLIMADA-project/climada_python): CLIMADA is a free and open-source software framework for climate risk assessment and adaptation option appraisal. 
- [Harnessing Large Language Models for Disaster Management: A Survey](https://arxiv.org/html/2501.06932v1)

## Data Sources
In this challenge, you will use open-source hazard and exposure data to build AI-powered solutions that help the Swiss society become more resilient against extreme weather events in Switzerland.  
### Hazard Data
#### Weather Data: MeteoSwiss
- MeteoSwiss (manual download) via the [MeteoSwiss Data Download Portal](https://www.meteoswiss.admin.ch/services-and-publications/applications/ext/download-data-without-coding-skills.htm). You can select different meteorological parameters (temperature, precipitation, sunshine, wind, etc.), choose a station and timeframe, export the data directly. We added a few sample CSVs in this repository (`/data` folder) so you can quickly test your pipelines.
- MeteoSwiss (API access), access documented in the [MeteoSwiss Opendata GitHub](https://github.com/MeteoSwiss/publication-opendata). Key features: REST-like API, Data available in JSON, CSV, and XML; includes observations, forecasts, and gridded datasets

#### Earthquake Data: Swiss Seismological Service (SED)
The [SED's seismic network](http://www.seismo.ethz.ch/en/knowledge/earthquake-data-and-analysis-tools/waveform-data/) records continuous wave-form data in real-time from over 200 permanent stations in Switzerland and an additional approximately 50 permanent stations in neighbouring regions, as well as from temporary stations set up for various projects. Access of waveform data is possible via [EIDA](https://www.orfeus-eu.org/data/eida/index.html).

#### Flood Data: Federal Office for the Environment (FOEN)
The FOEN surveys a number of parameters on Swiss rivers, lakes and groundwater. 
The hydrological data from the FOEN monitoring stations are accessible via the federal government's Linked Data Service [LINDAS](https://lindas.admin.ch/?lang=en). The [data](https://environment.ld.admin.ch/.well-known/void/dataset/hydro#https://environment.ld.admin.ch/.well-known/void/dataset/hydro) on discharge, water level, temperature and flood danger levels are updated every 10 minutes.

#### Glacier & Snow Data
The  Glacier Monitoring in Switzerland ([GLAMOS](https://www.glamos.ch/en/)) systematically documents and monitors long-term [glacier changes](https://www.glamos.ch/en/downloads#inventories/A55f-03) in the Swiss Alps. 

The  Institute of Snow and Avalanche Research ([SLF](https://www.slf.ch/en/)) operates an extensive network of manual measuring sites. At their sites, which are distributed throughout the Swiss Alps, they for example measure data on snow depth and 24-hour new snow. You can download data older than 7 days manually using the [file download](https://measurement-data.slf.ch/) or you download live data using their [API](https://measurement-api.slf.ch/). 


### Exposure Data
#### National data portals
- [Open Street Map](https://www.openstreetmap.org/#map=9/47.000/8.000) with [osm](https://www.osm.ch/entwickler.html) as dataset limited to Switzerland
- [swissBUILDINGS3D (swisstopo)](https://www.osm.ch/entwickler.html) - Data access described in this [document](https://backend.swisstopo.admin.ch/fileservice/sdweb-docs-prod-swisstopoch-files/files/2023/11/14/82d88341-a54c-4504-9055-f60002a609c4.pdf)
- [opendata.swiss](https://opendata.swiss/de) - Data catalog of Swiss Open Government Data, operated by the Federal Statistical Office (BFS)
- [BFS Data Portal](https://data.bfs.admin.ch/) - Data catalog of the Federal Statistical Office (BFS)
- [BFS STAT-TAB](https://www.pxweb.bfs.admin.ch/pxweb/en/) - Interactive database of the Federal Statistical Office (BFS)
- [BFS Registers](https://www.bfs.admin.ch/bfs/en/home/registers.html) - Official Swiss Enterprise Register, Population Register and Federal Register of Buildings and Dwellings.
- [SBB](https://opentransportdata.swiss/en/) - Open transport data provided by SBB.
- [Swiss Tourism Data](https://www.tourismdata.ch/) - Open portal of the National Data Infrastructure for Tourism (NaDIT)
- [Swisscom](https://data.swisscom.com/explore/) 


#### Cantonal data portals
- [Aargau](https://www.ag.ch/de/themen/datenportal#/)
- [Basel Stadt](https://data.bs.ch/explore/)
- [Basel Land](https://data.bl.ch/explore/)
- [Fribourg / Freiburg](https://opendata.fr.ch/pages/home/)
- [Luzern](https://www.lustat.ch)
- [Schwyz](https://data.sz.ch/explore/)
- [St. Gallen](https://daten.sg.ch/explore/) - Cantonal open data portal.
- [Thurgau](https://data.tg.ch/explore)
- [Zürich](https://www.zh.ch/de/politik-staat/opendata.zhweb-noredirect.zhweb-cache.html#/)
- [Zürich ](https://www.zh.ch/de/politik-staat/gemeinden/gemeindeportraet.html) – Web application providing a comprehensive set of indicators which can be exported to various formats.

## Guide to Approach the Challenge
To help you structure your work during the hackathon, we suggest the following four steps. These are not mandatory but can serve as a practical guide to move efficiently from problem statement to solution and pitch within the sprint timeframe. 

 
**1. Scope the Problem**
- Identify the hazard–exposure intersection you want to address. 
- Clarify the type of threat, the potential loss or impact, and the geographic focus. 
- Bring in your own observations, domain expertise, and lived experience to sharpen the problem framing. 

**2. Design Your Solution**
- Define who your persona is (e.g., municipality, household, insurer, hiker) and how they would use the product. 
- Consider the role of AI and data: what sources are available, what’s feasible in 36 hours, and what’s innovative. 
- Sketch a mock-up or conceptual design of your solution to make it tangible. 

**3. Prototype**
- Build a working model using real or synthetic datasets. 
- Perform basic validation to ensure plausibility. 
- Make your assumptions explicit (e.g., thresholds, triggers, coverage). 
- Implement a simple dashboard, app, or platform to demonstrate functionality. 

**4. Prepare the Pitch and Submission**
- Summarize your work in a clear slide deck. 
- Use storytelling to explain the problem, solution, and societal impact. 

---
By accessing or using the data provided, you agree to the following terms and conditions.

## Terms and Conditions
> The data is provided solely for the purpose of participating in the hackathon event held in Zurich, Switzerland, and for developing solutions directly related to the specific challenge you have selected. You are strictly prohibited from using the Data for any other purpose, including but not limited to:
> - Commercial use.
> - Research or development outside the scope of this hackathon challenge.
> - Personal use or any other unauthorized activities.
> 
> The data is provided "as is" without any warranties, express or implied, including but not limited to, warranties of merchantability, fitness for a particular purpose, or non-infringement. The hackathon organizers do not guarantee the accuracy, completeness, or reliability of the data.
>
> Immediately following the conclusion of the hackathon event, you are obligated to permanently and securely delete all copies of the data, including any derived or processed data, from all your devices, storage media, and systems. 

## Source of Data
The data of this respository has been provided by [Swiss Re](https://www.swissre.com/)
