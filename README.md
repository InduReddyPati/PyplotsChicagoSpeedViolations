## **SPEED CAMERA VIOLATIONS**
  
Team COD
  
Shiva Praveen Donga (UIN: 676463688)
  
Indu Reddy Pati (UIN: 657783668)

## 1. **Introduction:**
  
In this project, we used a Speed Camera Violation dataset to visualize the attributes of interest. The main goal of this project is to explore data visualization. We used Pandas, GeoPandas, Matplotlib and Jupyter to import, transform, visualize and analyze a dataset. Before visualizing the dataset, we have done data preprocessing and data cleaning. We comprehensively explored the dataset using different plotting techniques. We explored every insight possible in the dataset using multiple attributes.

## 2. **Data Description:**

**2.1. Dataset Overview:**

The dataset is obtained from the [Chicago Data portal](https://data.cityofchicago.org/Transportation/Speed-Camera-Violations/hhkd-xvj4). The camera and radar system has recorded the violations that have been reported. The data that we considered is from July 1st 2014 to August 31st 2022. This dataset has 9 attributes (Columns) and 309,320 data rows. The attributes are: ADDRESS, CAMERA\_ID, VIOLATION\_DATE, VIOLATIONS, X\_COORDINATE, Y\_COORDINATE, LATITUDE, LONGITUDE and LOCATION.

![alt text](https://github.com/uic-vis/project-1-team-cod/blob/main/images/Initial_DF.png?raw=true)

**2.2. Data Cleaning:**

The dataset consists of null values so we tried to remove NAN or null values. There are a total 309,320 data rows of which 11,782 rows have null values. So, we used .dropna() to remove (or drop) all the null values. After dropping all the null values, the dataset has 297,538 rows in total.

![alt text](https://github.com/uic-vis/project-1-team-cod/blob/main/images/Clean_DF.png?raw=true)

**2.3. Data Profiling:**

We aggregated the dataset as follows

- Max Violation: 827
- Minimum Violation: 1

![alt text](https://github.com/uic-vis/project-1-team-cod/blob/main/images/Describe.png?raw=true)

**2.4. Extraction:**

We extracted the required extra columns from already present columns Dataset - weekday, year, month, day from VIOLATION\_DATE.

![alt text](https://github.com/uic-vis/project-1-team-cod/blob/main/images/WeekDay_DF.png?raw=true)

**Checked Unique Addresses and count. Found Addresses with Average Max and Min Violations:**

- There are a total 160 unique Addresses.
- Avg Maximum violations is 202.716567 violations at address 4909 N CICERO AVE.
- Avg Minimum violations is 1.320225 violations at address 18 W SUPERIOR ST

**Bar Plot for Average Speed Violations per Address:**

![alt text](https://github.com/uic-vis/project-1-team-cod/blob/main/images/SpeedViolations_Address.png?raw=true)

**Checked Unique Camera Ids and count. Found Camera Ids with Max and Min Violations:**

- There are total 158 unique Cameras
- Maximum violations is 2976 violations with CHI083
- Minimum violations is 178 violations with CHI131

**Bar Plot for Speed Violations per Camera Id:**

![alt text](https://github.com/uic-vis/project-1-team-cod/blob/main/images/SpeedViolations_CameraId.png?raw=true)

## **3.Hypothesis:**

We had various hypotheses about Speed Violation in Chicago. Further, we tried to analyze and visualize the derived data to conclude if the assumed hypothesis is True or False.

**3.1. Hypothesis - 1:**

Speed Violations must have decreased over years due to Awareness and Strict Reinforcement of Speed Rules. For this hypothesis we plotted the number of violations over the years.

**Bar Plot for Speed Violation in Chicago Over Years (2014-2022)**

![alt text](https://github.com/uic-vis/project-1-team-cod/blob/main/images/Bar_Year.png?raw=true)

**Hypothesis - 1 Conclusion: False.**

- As speed violations across years look similar for 2015-2019 and 2021.
- 2020 decreased speed violations might be due to CoVid Lockdown.
- 2014 (from July-Dec) and 2022 (from Jan-Aug) are exceptions as data not available for the entire year.

**3.2. Hypothesis - 2:**

Speed Violation must be less during the winter/summer breaks. As most people will be on vacations and no worries to be not late to work.

**Speed Violations in Chicago for months over years (2014 - 2022):**

![alt text](https://github.com/uic-vis/project-1-team-cod/blob/main/images/Bar_Months.png?raw=true)

**Hypothesis - 2 Conclusion: True.**

- Speed violations during breaks are less. Summer breaks have much less violations than Winter.
- One more factor for high violations during Feb - May could be cold weather contributing to brake lock up.

**3.3. Hypothesis - 3:**

Speed Violation must be similar across days in months. The days in the month don't affect the violations . For we plotted bar plots for violations per day across the month.

**Speed Violations in Chicago for Days in Months over Years (2014-2022)**

![alt text](https://github.com/uic-vis/project-1-team-cod/blob/main/images/Bar_Days.png?raw=true)

**Hypothesis-3 Conclusion: True.**

- Speed violations are the same across days in months.
- As, no reason for speed violations being less for any day during the month.

**3.4. Hypothesis - 4:**

Weekdays have more Speed Violations than Weekends. For this hypothesis 4 we plotted violations per weekday

**Speed Violations in Chicago during Weekends and Weekdays**

![alt text](https://github.com/uic-vis/project-1-team-cod/blob/main/images/Bar_Week.png?raw=true)

![alt text](https://github.com/uic-vis/project-1-team-cod/blob/main/images/HeatMap_Week.png?raw=true)

**Hypothesis-4 Conclusion: True.**

- Speed violations are less on weekends - Saturday and Sunday compared to weekdays Monday-Friday.
- Reason - No rush to workplace and People on trips to Chicago Suburbs for Visiting, Hiking etc.
- No violations (Blank White Space in Heat Map) in certain Zip codes - Ashburn, Beverly etc.

## **4. Heat Map for Whole Speed Violations Data**

![alt text](https://github.com/uic-vis/project-1-team-cod/blob/main/images/HeatMap_SpeedViolations.png?raw=true)

**Conclusions from above Heat Map**

- No speed violations for certain zip codes - Downtown and Loop, Douglas, Oakland, Englewood etc.
- Most Violations:
  - North-West Neighborhoods to Downtown Chicago - Jefferson Park, Belmont, Garfield Park etc.
  - South-West Neighborhoods to Downtown Chicago - Ashburn, Bridgeport etc.
