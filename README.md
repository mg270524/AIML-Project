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
The XLSX file has 461 rows and 31 columns. 


The following table shows the first 10 rows of the dataset.  
| State          | City              | Station ID                                                                 | Last Update         | Latitude   | Longitude  | PM2.5 Min | PM2.5 Max | PM2.5 Avg | PM2.5 Hourly sub index | PM10_Min | PM10_Max | PM10_Avg | PM10_Hourly_sub_index | NO2_Min | NO2_Max | NO2_Avg | NO2_Hourly_sub_index | NH3_Min | NH3_Max | NH3_Avg | NH3_Hourly_sub_index | SO2_Min | SO2_Max | SO2_Avg | SO2_Hourly_sub_index | CO_Min | CO_Max | CO_Avg | CO_Hourly_sub_index | OZONE_Min | OZONE_Max | OZONE_Avg | OZONE_Hourly_sub_index | AQI Value | Predominant_Parameter |
| -------------- | ----------------- | -------------------------------------------------------------------------- | ------------------- | ---------- | ---------- | --------- | --------- | --------- | ---------------------- | -------- | -------- | -------- | --------------------- | ------- | ------- | ------- | -------------------- | ------- | ------- | ------- | -------------------- | ------- | ------- | ------- | -------------------- | ------ | ------ | ------ | ------------------- | --------- | --------- | --------- | ---------------------- | --------- | --------------------- |
| Andhra Pradesh | Amravati          | Secretariat, Amaravati - APPCB                                             | 19-03-2025 19:00:00 | 16.5150833 | 80.5181667 | 2         | 17        | 9         | 8                      | 13       | 38       | 23       | 32                    | 5       | 9       | 7       | 8                    | 4       | 5       | 4       | 4                    | 10      | 15      | 13      | 13                   | 3      | 34     | 18     | 12                  | 1         | 26        | 22        | 14                     | 23        | PM10                  |
| Andhra Pradesh | Anantpur          | Gulzarpet, Anantapur - APPCB                                               | 19-03-2025 19:00:00 | 14.675886  | 77.593027  | 39        | 61        | 51        | 48                     | 41       | 66       | 54       | 51                    | 26      | 49      | 33      | 41                   | 6       | 14      | 8       | 10                   | 6       | 14      | 11      | 9                    | 10     | 20     | 20     | 20                  | 8         | 39        | 31        | 31                     | 54        | PM10                  |
| Andhra Pradesh | Chittor           | Gangineni Cheruvu, Chittoor - APPCB                                        | 19-03-2025 19:00:00 | 13.20488   | 79.097889  | 21        | 314       | 88        | NA                     | 19       | 173      | 68       | NA                    | 10      | 15      | 13      | NA                   | 3       | 3       | 3       | NA                   | 2       | 3       | 3       | NA                   | 6      | 10     | 6      | NA                  | 21        | 43        | 34        | NA                     | 88        | PM2.5                 |
| Andhra Pradesh | Kadapa            | Yerramukkapalli, Kadapa - APPCB                                            | 19-03-2025 19:00:00 | 14.465052  | 78.824187  | 28        | 47        | 38        | 34                     | 30       | 49       | 40       | 36                    | 15      | 29      | 21      | 22                   | 5       | 6       | 5       | 5                    | 14      | 16      | 15      | 15                   | 26     | 30     | 30     | 29                  | 30        | 30        | 30        | 30                     | 40        | PM10                  |
| Andhra Pradesh | Rajamahendravaram | Anand Kala Kshetram, Rajamahendravaram - APPCB                             | 19-03-2025 19:00:00 | 16.9872867 | 81.7363176 | 5         | 19        | 12        | 10                     | 14       | 31       | 21       | 25                    | 3       | 21      | 11      | 21                   | 4       | 7       | 5       | 6                    | 8       | 12      | 10      | 11                   | 10     | 32     | 17     | 30                  | 6         | 7         | 6         | 6                      | 21        | PM10                  |
| Andhra Pradesh | Tirumala          | Toll Gate, Tirumala - APPCB (Formerly known as Tirumala, Tirupati - APPCB) | 19-03-2025 19:00:00 | 13.67      | 79.35      | 2         | 36        | 21        | 31                     | 8        | 46       | 27       | 46                    | 11      | 22      | 16      | 22                   | 1       | 1       | 1       | 1                    | 1       | 8       | 4       | 4                    | 2      | 69     | 26     | 18                  | 8         | 29        | 24        | 19                     | 27        | PM10                  |
| Andhra Pradesh | Tirupati          | Vaikuntapuram, Tirupati - APPCB                                            | 19-03-2025 19:00:00 | 13.615387  | 79.40923   | 37        | 102       | 58        | 50                     | 35       | 87       | 51       | 45                    | 7       | 28      | 14      | 15                   | 1       | 4       | 2       | 2                    | 3       | 4       | 3       | 3                    | 8      | 23     | 14     | 16                  | 49        | 49        | 49        | 49                     | 58        | PM2.5                 |
| Andhra Pradesh | Vijaywada         | HB Colony, Vijayawada - APPCB                                              | 19-03-2025 19:00:00 | 16.536107  | 80.594233  | 49        | 63        | 53        | 49                     | 48       | 66       | 52       | 48                    | 12      | 14      | 13      | 14                   | 1       | 4       | 2       | 3                    | 3       | 4       | 4       | 4                    | 22     | 32     | 27     | 28                  | 4         | 26        | 7         | 4                      | 53        | PM2.5                 |
| Andhra Pradesh | Vijaywada         | Kanuru, Vijayawada - APPCB                                                 | 19-03-2025 19:00:00 | 16.486692  | 80.699436  | 59        | 83        | 74        | 68                     | 62       | 81       | 74       | 73                    | 9       | 50      | 19      | NA                   | 4       | 6       | 5       | NA                   | 4       | 9       | 7       | 6                    | 7      | 26     | 12     | 15                  | 16        | 26        | 22        | 26                     | 74        | PM10                  |
| Andhra Pradesh | Vijaywada         | Rajiv Gandhi Park, Vijayawada - APPCB                                      | 19-03-2025 19:00:00 | 16.509717  | 80.612222  | 50        | 81        | 66        | 81                     | 54       | 83       | 69       | 83                    | 43      | 62      | 52      | 44                   | 3       | 5       | 4       | 5                    | 6       | 10      | 9       | 10                   | 38     | 46     | 40     | 39                  | 5         | 13        | 10        | 7                      | 69        | PM10                  |

## Dataset Cleaning

### 1. Handling Missing Values
   Since we already know that our dataset contains missing values , and we need to fill them for our further analysis . We will be using KNNImputation to fill in our missing values. Imputation is the process of replacing missing data with substituted values . Because missing data can create problems for analyzing data, imputation is seen as a way to avoid pitfalls involved with listwise deletion of cases that have missing values. The following columns were dropped for Imputation process.  
   
   
- _State_
- _City_
- _Station ID_
- _Last Update_
- _PM2.5 Hourly sub index_
- _PM10_Hourly_sub_index_
- _NO2_Hourly_sub_index_
- _NH3_Hourly_sub_index_
- _NO2_Hourly_sub_index_
- _CO_Hourly_sub_index_
- _OZONE_Hourly_sub_index_
- _NH3_Min_
- _NH3_Max_
- _NH3_Avg_
- _Latitude_
- _Longitude_
- _Time Stamp_
- _AQI Value_
- _Predominant_Parameter_

  
**Note**: The columns - Station ID, LAst Update, hourly sub indices of each pollutant, NH3 indexes were removed completly from the dataset becasue they are not very useful for analysis. Since NH3 is not officially used in calculation of AQI related terms, it was also removed.  

So, our cleaned dataset looks like this:  

  | State          | City              | Latitude   | Longitude  | PM2.5 Min | PM2.5 Max | PM2.5 Avg | PM10_Min | PM10_Max | PM10_Avg | NO2_Min | NO2_Max | NO2_Avg | SO2_Min | SO2_Max | SO2_Avg | CO_Min | CO_Max | CO_Avg | OZONE_Min | OZONE_Max | OZONE_Avg | AQI Value | Predominant_Parameter |
| -------------- | ----------------- | ---------- | ---------- | --------- | --------- | --------- | -------- | -------- | -------- | ------- | ------- | ------- | ------- | ------- | ------- | ------ | ------ | ------ | --------- | --------- | --------- | --------- | --------------------- |
| Andhra Pradesh | Amravati          | 16.5150833 | 80.5181667 | 2         | 17        | 9         | 13       | 38       | 23       | 5       | 9       | 7       | 10      | 15      | 13      | 3      | 34     | 18     | 1         | 26        | 22        | 23        | PM10                  |
| Andhra Pradesh | Anantpur          | 14.675886  | 77.593027  | 39        | 61        | 51        | 41       | 66       | 54       | 26      | 49      | 33      | 6       | 14      | 11      | 10     | 20     | 20     | 8         | 39        | 31        | 54        | PM10                  |
| Andhra Pradesh | Chittor           | 13.20488   | 79.097889  | 21        | 314       | 88        | 19       | 173      | 68       | 10      | 15      | 13      | 2       | 3       | 3       | 6      | 10     | 6      | 21        | 43        | 34        | 88        | PM2.5                 |
| Andhra Pradesh | Kadapa            | 14.465052  | 78.824187  | 28        | 47        | 38        | 30       | 49       | 40       | 15      | 29      | 21      | 14      | 16      | 15      | 26     | 30     | 30     | 30        | 30        | 30        | 40        | PM10                  |
| Andhra Pradesh | Rajamahendravaram | 16.9872867 | 81.7363176 | 5         | 19        | 12        | 14       | 31       | 21       | 3       | 21      | 11      | 8       | 12      | 10      | 10     | 32     | 17     | 6         | 7         | 6         | 21        | PM10                  |
| Andhra Pradesh | Tirumala          | 13.67      | 79.35      | 2         | 36        | 21        | 8        | 46       | 27       | 11      | 22      | 16      | 1       | 8       | 4       | 2      | 69     | 26     | 8         | 29        | 24        | 27        | PM10                  |
| Andhra Pradesh | Tirupati          | 13.615387  | 79.40923   | 37        | 102       | 58        | 35       | 87       | 51       | 7       | 28      | 14      | 3       | 4       | 3       | 8      | 23     | 14     | 49        | 49        | 49        | 58        | PM2.5                 |
| Andhra Pradesh | Vijaywada         | 16.536107  | 80.594233  | 49        | 63        | 53        | 48       | 66       | 52       | 12      | 14      | 13      | 3       | 4       | 4       | 22     | 32     | 27     | 4         | 26        | 7         | 53        | PM2.5                 |
| Andhra Pradesh | Vijaywada         | 16.486692  | 80.699436  | 59        | 83        | 74        | 62       | 81       | 74       | 9       | 50      | 19      | 4       | 9       | 7       | 7      | 26     | 12     | 16        | 26        | 22        | 74        | PM10                  |
| Andhra Pradesh | Vijaywada         | 16.509717  | 80.612222  | 50        | 81        | 66        | 54       | 83       | 69       | 43      | 62      | 52      | 6       | 10      | 9       | 38     | 46     | 40     | 5         | 13        | 10        | 69        | PM10                  |



## **Understanding the pollutants briefly**:  
  
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

### 1. Count Plot
![](https://github.com/mg270524/AIML-Project/blob/main/assets/countplot.png)

### 2. Scatter Plot
![](https://github.com/mg270524/AIML-Project/blob/main/assets/scatterplt.png)

### 3. Box Plot
![](https://github.com/mg270524/AIML-Project/blob/main/assets/boxplot.png)

### 4. Pair Plot
![](https://github.com/mg270524/AIML-Project/blob/main/assets/pairplot.png)

### 5. Heatmap
![](https://github.com/mg270524/AIML-Project/blob/main/assets/heatmap1.png)
   
   







## Regression Analysis




## Correlation Analysis




## Hypothesis Testing
 ### Hypotheses 
 1. **H1: Urban vs. Rural Differences**: Air quality and health impacts differ significantly between urban and rural areas.
 2. **H2: Pollutant Concentration Effects**: Higher concentrations of specific pollutants correlate with increased health issues.
 3. **H3: Policy Impacts**: Locations with stricter air quality regulations exhibit better air quality and fewer health impacts.




## Research Questions

1. **Understanding Air Quality Patterns**: Investigating how air quality varies across different locations.
2. **Identifying Health Impact across Cities**: Determining the cities which are most affected due to air quality.

