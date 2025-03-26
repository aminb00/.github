# Organisation of Work Package 2 - Spoke 0 - GRINS (Growing Resiliant, INclusive and Sustainable)

This organization on GitHub stems from the need to collect in one place the code produced by the Bergamo team related to downloading and handling environmental data: climate, air quality and emissions. More specifically, this reproducible code will enter the AMELIA platform for the automatisation of the download process, to make the AMELIA platform updatable every release of dataasets.

Several repositories can be found within the organization, each of them almost independent. After downloading the data and preparing them for use, there is a repository that refers to the statistical model used for the techniques of data fusion, change of spatial and temporal support, and uncertainty quantification.

## What is GRINS?

GRINS ([link](https://www.grins.it)) produces frontier research in the economic-political-social science and data science spectrum to provide scientific evidence to guide public policy as well as the choices of citizens and companies in complex decision-making contexts. Grins' mission translates into the realisation of an open data platform designed to support the decision-making processes of all actors, from citizens to administrators, through the production of high quality statistical information and analysis, in compliance with strict professional ethical principles and the most advanced scientific standards.

The goal of the GRINS (Growing Resiliant INclusive and Sustainable) project is to help the Italian community to grow efficiently as well as resilient, inclusive and sustainable. This important and challenging goal will be reached thank to the deeper comprehension of the reality. Data are the mirror of reality, but they must be collected, validated, re-organised, harmonised, analysed, visualised and finally interpreted. Statistical tools are the only instruments capable of performing these operations on the data, so they are indispensable for achieving the goals of the GRINS project.

The team of the University of Bergamo (UNIBG) involved in the spoke 0, more specifically in the Work Package 0.2 (WP0.2), leaded by Prof. Alessandro Fassò, is proposing to use a common methodology for data harmonisation among the groups of the project. In particular, these methods are suitable for spatial and temporal data. UNIBG works mainly with environmental data: weather, air quality and emissions. Harmonised data, with the same spatial and temporal resolution (i.e. municipality and daily), will compose the dataset used by the AMELIA platform. More specifically, this dataset will represent the deliverable D.0.2.1 of the GRINS project.

### The Spoke 0

Spoke 0, or the Hub, is entirely dedicated to the construction, development and maintenance of the AMELIA (dAta platforM for the transfEr of knowLedge and statistIcal Analysis) data platform. The other eight thematic Spokes will provide Spoke 0 with primary sources, intermediate data, statistical analyses, software codes and final deliverables, which will be processed and harmonised through the platform.

The goal of the AMELIA platform is to help the Italian community to grow efficiently as well as resilient, inclusive and sustainable. This important and challenging platform will be used toward a deeper comprehension of the reality. Data are the mirror of reality, however they must be collected, validated, re-organised, harmonised, analysed, visualised and finally interpreted. Statistical tools are the only instruments capable of performing these operations on the data, so they are indispensable for achieving the goals of the AMELIA platform, and therefore of the GRINS project.

#### The Work Package 2

Work Package 0.2 focuses on ensuring the quality of the indicators available on the platform referring to the economic actors and territories examined, spatially and temporally determined, obtained by means of classical statistical models and machine learning techniques. These indicators will be based on harmonised datasets obtained from the integration of heterogeneous and georeferenced data sources. Frontier research in statistical science and machine learning will be used to build pilot statistical models for record linkage and statistical matching of survey data, spatio-temporal fusion of data, e.g. from Copernicus sources, and small area estimation. The quality of the developed indicators will be evaluated in accordance with the FAIR, SAFE and open data principles.

The team of the University of Bergamo (UNIBG) involved in the spoke 0, more specifically in the Work Package 0.2 (WP0.2), leaded by Prof. Alessandro Fassò, is proposing to use a geostatistical approach to harmonise spatio-temporal data. Indeed, UNIBG team work mainly with environmental data: weather, air quality and emissions. Harmonised data, i.e. with the same spatial and temporal resolution (e.g. municipality and daily), will be part of the AMELIA platform. More specifically, this dataset will represent the deliverable D.0.2.1

# Repositories

This organisation has been created within the GRINS project to take trace of the scripts used for generating intermediate and final outputs of the projects. Several repositories are available and extensive descriptions are contained within each of them. Within the same repository, there are several versions of code (*v.0.0.1* or *v.1.0.0* etc.) that generate respective versions of datasets.

Work is mainly divided in two parts: 
- Input data
- Statistical modelling

## Input Data 

Environmental data include different dimensions represented here by different acronyms: **AQ** for Air Quality, **WE** for Weather, **EM** for Emissions. Within the same dimension, data can be substantially different: observed by land monitoring stations, measured by satellites, produced by mathematical models, and others. Several different organisations managing the release of these data, use different procedures. For this reason, the pair dimension-source is used to identify a dataset. Each dataset has his own repository. For example, the air quality data (AQ) downloaded from the European Environmental Agency (EEA) is a repository called **AQ-EEA**. Each repository containes the code used from the download to the final dataset. Common tasks operated with R routines within these repositories are: automatic download, converting format (e.g. from csv or netcdf to Rdata), changing temporal resolution (e.g. from hourly to daily), solving critical situations about the quality of raw data (e.g. errors in the raw data), quality check (e.g. removing anomalies in the data). For data, the following repositories are available:

1. **AQ-EEA** contains the data flow for air quality measurements obtained by the European Environmental Agency.
2. **AQ-CAMS** contains the data flow for air quality numerical models output obtained by the Copernicus Atmosphere Monitoring Service (CAMS).
3. **WE-C3S** contains the data flow for weather data obtained by the Climate Change Service (C3S).
4. **EM-CAMS** contains the data flow for emission data obtained by the Copernicus Atmosphere Monitoring Service (CAMS).

#### Input data
_Table 1: Summary of inputs_
| **Dim** | **Source** | **GitHub repo** | **version** | **Dataset**            | **Brief description**    | **Period** | **Variables selected**                                                                                                         | **temporal resolution** | **spatial resolution** |
|---------|------------|-----------------|-------------|------------------------|--------------------------|------------|--------------------------------------------------------------------------------------------------------------------------------|-------------------------|------------------------|
| AQ      | EEA        | AQ-EEA          | v.1.0.0     | Airbase                | measured air pollution   | -          | -                                                                                                                              | -                       | -                      |
| AQ      | EEA        | AQ-EEA          | v.1.0.0     | E1a                    | measured air pollution   | 2013-2022  | CO, NH3, NO, NO2, O3, PM2.5, PM10, SO2                                                                                         | hourly,bi-hourly, daily | point referenced       |
| AQ      | EEA        | AQ-EEA          | v.1.0.0     | E2a                    | measured air pollution   | 2023       | CO, NH3, NO, NO2, O3, PM2.5, PM10, SO2                                                                                         |                         |                        |
| AQ      | CAMS       | AQ-CAMS         | v.1.0.0     | air quality reanalysis | air pollutant from CTMs  | 2013-2023  | NO2, CO, NH3, NMVOC, NO, O3, PM2.5, PM10, SO2                                                                                  | hourly                  | 0.1° x 0.1°            |
| WE      | C3S        | WE-C3S          | v.1.0.0     | ERA5Land               | land-weather reanalysis  | 2013-2023  | high/low vegetation index, relative humidity, surf solar radiation, temperature, total precipitation, wind direction and speed | hourly                  | 0.1° x 0.1°            |
| WE      | C3S        | WE-C3S          | v.1.0.0     | ERA5 Single Level      | weather model reanalysis | 2013-2023  | boundary layer height                                                                                                          | hourly                  | 0.25° x 0.25°          |
| EM      | CAMS       | EM-CAMS         | v.1.0.0     | CAMS-GLOB-ANT v6.2     | emissions from CAMS      | 2000-2024  | NO2                                                                                                                            | monthly                 | 0.1° x 0.1°            |
| EM      | CAMS      | EM-CAMS         | v.1.0.0     | CAMS-REG-ANT    | regional anthropogenic emissions | 2019-2023* | NO2, … (eventuali altre)        | monthly                 | 0.1° x 0.1°            |
| EM      | TEMPO     | EM-TEMPO        | v.1.0.0     | TEMPO           | esempio: nuove rilevazioni EM    | 2013-2023* | es. NOx, PM, ecc. (da definire) | daily (o da definire)   | ??? (da definire)      |

<p>&nbsp;</p>

#### Intermediate transformation
_Table 2: Summary of intermediates transformation_
| **Dim** | **Source** | **GitHub repo** | **version** | **spatial transformation** | **techniques used (space)** | **temporal transformation** | **techniques used (time)**                  |
|---------|------------|-----------------|-------------|----------------------------|-----------------------------|-----------------------------|---------------------------------------------|
| AQ      | EEA        | AQ-EEA          | v.1.0.0     | none                       | none                        | hourly/bi-hourly -> daily   | kalman smoother. Min,1q,mean,med,3q,max     |
| AQ      | CAMS       | AQ-CAMS         | v.1.0.0     | none                       | none                        | hourly -> daily             | Min,1q,mean,med,3q,max                      |
| WE      | C3S        | WE-C3S          | v.0.0.1     | none                       | none                        | hourly -> daily             | mean,min,max,mode depending on the variable |
| WE      | C3S        | WE-C3S          | v.1.0.0     | none                       | none                        | hourly -> daily             | mean,min,max,mode depending on the variable |
| EM      | CAMS       | EM-CAMS         | v.0.0.1     | none                       | none                        | monthly-> daily             | piecewise constant function                 |

<p>&nbsp;</p>

#### Outputs
_Table 3: Summary of outputs_
| **Dim** | **Source** | **GitHub repo** | **version** | **period** | **temporal resolution** | **spatial resolution** | **#files** | **overall output dimension** | **format** |
|---------|------------|-----------------|-------------|------------|-------------------------|------------------------|------------|------------------------------|------------|
| AQ      | EEA        | AQ-EEA          | v.1.0.0     |            | -                       | -                      | -          | -                            | -          |
| AQ      | EEA        | AQ-EEA          | v.1.0.0     | 2013-2023  | daily                   | point-ref              | 1          | 160/870 Mb                   | Rdata/csv  |
| AQ      | EEA        | AQ-EEA          | v.1.0.0     | 2013-2023  | daily                   | point-ref              | 1          | 160/870 Mb                   | Rdata/csv  |
| AQ      | CAMS       | AQ-CAMS         | v.1.0.0     | 2013-2023* | daily                   | 0.1° x 0.1°            | 80         | 2.4 Gb                       | Rdata      |
| WE      | C3S        | WE-C3S          | v.0.0.1     | 2019-2023  | daily                   | 0.1° x 0.1°            | 1          | 1 Gb                         | netcdf     |
| WE      | C3S        | WE-C3S          | v.0.0.1     | -          | -                       | -                      | -          | -                            | -          |
| WE      | C3S        | WE-C3S          | v.1.0.0     | 2013-2023  | daily                   | 0.1° x 0.1°            | ?          | ?                            | ?          |
| WE      | C3S        | WE-C3S          | v.1.0.0     | 2013-2023  | daily                   | 0.25° x 0.25°          | 1          | 54 Mb                        | Rdata      |
| EM      | CAMS       | EM-CAMS         | v.0.0.1     | 2019-2023  | daily                   | 0.1° x 0.1°            | 1          | 1.83 Gb / 83 Mb              | csv/Rdata  |


### Air Quality data (AQ)

Air quality data are usually **observed** or **modeled**. **Observed** data represent the measurements made by operators and machines. They reflect the best approximation of the reality but they are prone to missingness, measurement errors, heterogeneity among measurements procedures, sparse availability, and other issues. **Modeled** data, on the other hand, generally show completeness and uniformity but they can significantly differ from the reality. Almost all mathematical models generating modeled data are divided in two different categories: **deterministic** and **stochastic**.

For the Italian domain, we retrieve AQ data from two different sources: the European Environmental Agency (**EEA**) and the Copernicus Atmosphere Monitoring Service (**CAMS**). **EEA** data are **observed** from the air quality monitoring stations and **CAMS** data are based on an ensemble of nine air quality data assimilation systems across Europe that use CTMs as based. Technical details about the sources are contained in the respective repositories. EEA data are available just at specific locations (the air quality monitoring network) while CAMS products are available on a full grid (cell centers lie on orthogonal straight lines) and cropped over the Italian domain. To use both the EEA and CAMS data simultaneously, data fusion techniques are required. 

### Weather data (WE)

Meteorology plays a crucial role in studying air quality because atmospheric conditions directly influence the dispersion, concentration, and movement of pollutants. Wind patterns can transport contaminants over long distances, while temperature, humidity, and pressure affect chemical reactions in the air. These meteorological variables also capture the seasonal effects, as air quality tends to fluctuate with different weather patterns throughout the year. For instance, winter inversions can trap pollutants, while summer heat can intensify smog. Accurate meteorological monitoring is therefore essential to predict air quality changes and develop effective environmental protection strategies.

### Emissions data (EM)

Emissions play a vital role in studying air quality, as they are the primary source of pollutants released into the atmosphere from various activities, such as transportation, industry, and agriculture. Emission data can be represented in different forms, such as spatially explicit maps or point measurements, and they can be aggregated on various time scales, ranging from annual inventories to more detailed monthly or even daily estimates. These datasets are developed using either top-down approaches, which rely on large-scale inventories, satellite data, and atmospheric modeling, or bottom-up methods that compile detailed local measurements from specific sources, such as factories or traffic data. The combination of these approaches allows for a comprehensive view of emission patterns. By using statistical space-time models, researchers can integrate these datasets, capturing the variability of emissions across both space and time, and analyze how they interact with weather conditions and other factors to impact air quality. This approach enables more precise identification of pollution sources and supports the design of targeted mitigation strategies.

## Statistical modelling

To reach the ultimate goal of the GRINS project, we need an harmonised dataset at municipal level, daily, containing all the variables considered. However, while administrative data come naturally at municipal level, environmental data can have different resolutions, as points-referenced or grids, but almost never at municipal level. For the change of the spatial resolution we use a statistical modelling approach. The repositories linked to these operations are under the dimension **FRK-Modelling** (Fixed Rank Kriging) that is the acronym of the model used to tackle the problems of change of support and up/down-scaling faced during the change of spatial resolution. For meteorological variables, considering the high-quality of ERA5s products, a simple Inverse Distance Weighted (IDW) interpolation is made to convert to municipal data. 

# For AMELIA

| **Modules Level 1** | **Modules Level 2**   | **Modules Level 3**       | GitHub Repo           | version | R core scripts        | Additional R scripts                                                        |
|---------------------|-----------------------|---------------------------|-----------------------|---------|-----------------------|-----------------------------------------------------------------------------|
| 123_Input           | 1_Download            | 1_Download_AQ_EEA         | AQ-EEA                | v.1.0.0 | EEA_download.R        | EEA_download(for).R                                                         |
|                     |                       | 1_Download_AQ_CAMS        | AQ-CAMS               | v.1.0.0 | CAMS_download.R       | functions.R                                                                 |
|                     |                       | 1_Download_WE_C3S         | WE-C3S                | v.1.0.0 | C3S_download.R        |
|                     |                       | 1_Download_EM_CAMS        | EM-CAMS               | v.1.0.0 | ? | ? |
|                     | 2_Preprocessing       | 2_Preprocessing_AQ_EEA    | AQ-EEA                | v.1.0.0 | EEA_preprocessing.R   | EEA_descriptive_statistics.R, classify_problematic_rawfiles.R, functions.R  |
|                     |                       | 2_Preprocessing_AQ_CAMS   | AQ-CAMS               | v.1.0.0 | CAMS_download.R       | functions.R                                                                 |
|                     |                       | 2_Preprocessing_WE_C3S    | WE-C3S                | v.1.0.0 | C3S_HtoD.R            | functions.R                                                                 |
|                     |                       | 2_Preprocessing_EM_CAMS   | EM-CAMS               | v.1.0.0 | ? | ? |
|                     | 3_Daily               | 3_Daily_AQ_EEA            | AQ-EEA                | v.1.0.0 | EEA_HtoD.R            | EEA_metadata.R, EEA_merging.R, functions.R                                  |
|                     |                       | 3_Daily_AQ_CAMS           | AQ-CAMS               | v.1.0.0 | CAMS_HtoD.R           | functions.R, CAMS_export.R, functions.R                                     |
|                     |                       | 3_Daily_WE_C3S            | WE-C3S                | v.1.0.0 | C3S_HtoD.R            | C3S_QualityCheck.R, functions.R                                             |
|                     |                       | 3_Daily_EM_CAMS           | EM-CAMS               | v.1.0.0 | ? | ? |
| 45_Output           | 4_HighResolution      | 4_HighResolution_WE_Modelling             | ?        | ? | ? |
|                     |                       | 4_HighResolution_EM_Modelling             | ?        | ? | ? |
|                     |                       | 4_HighResolution_AQ_Modelling             | AQ-Modelling | v.3.0.2 | AQ_Modelling_v302_FRK_NO2.R | all the repo |
|                     | 5_Municipalities      | 5_Municipalities_AQ                 | ?        | ? | ? |
|                     |                       | 5_Municipalities_WE                 | ?        | ? | ? |
|                     |                       | 5_Municipalities_EM                 | ?        | ? | ? |





