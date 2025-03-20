<div align="center">
   
  <h3>AIML Project</h3>
  <h1>Analysis of Air Quality and Health Impact</h1>
</div>

## Aim

To select real datasets and analyze the same using the concepts and tools studied. The analysis includes:
- Exploratory Data Analysis (EDA)
- Regression and Correlation analysis
- Hypothesis testing

Further, to formulate a few research questions and try to answer the same based on the dataset.

## About Dataset

The data required to carry out the analysis was obtained from Central Pollution Control Board (CPCB) by accessing the publicly available API hosted
on their server. The API provides real-time air quality data from various monitoring stations across India. By making a GET request, users will receive data in JSON format that includes current hour AQI data values for key air quality indicators such as PM2.5, PM10, NO2, Ozone, CO, SO2, as well as the geographical coordinates of the monitoring stations. The data is updated every hour and can be used for monitoring air quality trends in different regions.  

Data Values:
1. State
2. City
3. Station Name
4. Latitude
5. Longitude
6. Time Stamp
7. Pollutant wise Sub-Indexes with Min., Max. Avg. values
8. Overall AQI
9. Prominent Pollutant



To know more about the API used [click here](https://directory.apisetu.gov.in/api-collection/cpcb).  
  
The data received through the API was in XML format.
So for analysis purposes, the XML file was converted to CSV file in Python.  
The CSV file was further used for preliminary exploration in Google Sheets. Some minor changes were made such as formatting column names, removing underscores etc. The file was finally
exported into XLSX format.
[Click here](https://github.com/mg270524/AIML-Project/raw/refs/heads/main/outfile(1).xlsx) to download the XLSX file.


## Dataset Cleaning

1. Handling Missing Values
-
-
-
-



**Understanding the pollutants briefly**:  
  
1. **PM2.5 (Fine Particulate Matter)**
   -    **How it’s produced**: PM2.5 consists of tiny particles with a diameter of 2.5 micrometers or smaller. It is emitted directly from sources like vehicle exhaust, power plants, industrial processes, wildfires, and burning of fossil fuels. It can also form in the atmosphere from chemical reactions involving gases like NO₂ and SO₂.

   - **Impact**: PM2.5 can penetrate deep into the lungs and even enter the bloodstream, causing respiratory and cardiovascular diseases, aggravated asthma, reduced lung function, and premature death. It is also linked to lung cancer and developmental issues in children.

3. **PM10**
    - **How it’s produced**: PM10 includes larger particles with a diameter of 10 micrometers or smaller. It is produced by dust from construction sites, unpaved roads, agriculture, mining, and industrial activities. It can also come from natural sources like pollen and sea spray.

    - **Impact**: PM10 can irritate the eyes, nose, and throat and worsen respiratory conditions like asthma and bronchitis. While it doesn’t penetrate as deeply as PM2.5, it still poses significant health risks, especially to vulnerable populations.
4. **NO2**
    - **How it’s produced**: NO₂ forms when fossil fuels (e.g., coal, oil, gas) are burned at high temperatures, primarily from vehicle emissions, power plants, and industrial facilities. It is also a precursor to ground-level ozone and particulate matter.

    - **Impact**: NO₂ irritates the respiratory system, aggravates asthma, and increases susceptibility to respiratory infections. Long-term exposure can lead to chronic lung disease and contribute to the formation of smog and acid rain.
5. **SO2** 
    - **How it’s produced**: SO₂ is emitted from burning sulfur-containing fuels like coal and oil, primarily from power plants, refineries, and industrial processes. It can also be released during volcanic eruptions.

    - **Impact**: SO₂ irritates the respiratory system, worsens asthma, and can lead to the formation of fine particulate matter (PM2.5) and acid rain, which harms ecosystems, soils, and water bodies.
6. **CO** 
    **How it’s produced**: CO is produced by the incomplete combustion of carbon-based fuels, such as gasoline, natural gas, coal, and wood. Major sources include vehicle exhaust, industrial processes, and residential heating systems.

    **Impact**: CO reduces the blood’s ability to carry oxygen, leading to headaches, dizziness, and, at high concentrations, can be fatal. It is particularly dangerous in enclosed spaces.
7. **OZONE**
    - **How it’s produced**: Ground-level ozone is not emitted directly but forms when nitrogen oxides (NOx) and volatile organic compounds (VOCs) react in the presence of sunlight. Sources include vehicle emissions, industrial facilities, and chemical solvents.

    - **Impact**: Ozone is a major component of smog and can cause respiratory problems, aggravate asthma, reduce lung function, and lead to chronic lung diseases. It also harms crops and ecosystems.

   <img alt="Health Impact" src="assets/health indication.png"> </img>
   _[Source](https://cpcb.nic.in/index.php)_





## EDA  

1. Graphs
2. Boxplot
3. Pointplot
4. Heatmap
5. RegPlot







## Regression Analysis




## Correlation Analysis




## Hypothesis Testing
 ### Hypotheses 
 1. **H1: Urban vs. Rural Differences**: Air quality and health impacts differ significantly between urban and rural areas.
 2. **H2: Pollutant Concentration Effects**: Higher concentrations of specific pollutants correlate with increased health issues.
 3. **H3: Policy Impacts**: Locations with stricter air quality regulations exhibit better air quality and fewer health impacts.




## Research Questions

1. **Understanding Air Quality Patterns**: Investigating how air quality varies across different locations.
2. 

