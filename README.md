# Aircraft Safety Analysis
Author: [Chris Kucewicz](cfkucewicz@gmail.com)
## Business Understanding
### Background:
My company is planning to diversify its porfolio by extending to different markets. More specifically, my company is looking to invest in airplanes in order for their expansion to different markets to be successful.

### Business Goals:
The primary focus of this data science project is to assess and mitigate the risks associated with various aircraft models. Specifically, we aim to identify and recommend aircraft types that carry the least potential risk. This information is crucial for making informed decisions regarding aircraft investments and ensuring the success of our company's expansion into new markets.

### Business Success Criteria:
The success of this project will be measured by providing three well-supported recommendations on the least risky aircraft models for our company to invest in. For this project, the term least risky refers to types of aircrafts with the least amount of crashes, the least number of casualties, and the lowest fatality rate.

## Data Understanding
The National Transportation Safety Board (NTSB) collects data on aviation accidents and incidents that occur in the United States (which include its territories) as well as international waters. This dataset includes 31 features and 88,889 observations or entries.

Each entry in the dataset represents an aircraft involved in an accident (or incident). For each aircraft there is a unique ID associated with the specific accident (or incident) the aircraft was involved in. Additional information is included about each entry, such as the accident (or incident) date, location, and number of injuries, as well as characteristics about the aircraft, such as the make, model, and number of engines.

### Data Preparation
In data preparation, I created three functions (`display_df_information()`, `multiple_value_counts()`, and `examine_features()`) to assess data types, NaN values, and entry details. Columns with high NaN values or high cardinality with a uniform distribution were dropped: `Longitude`, `Latitude`, `FAR.Description`, `Schedule`, `Air.carrier`, `Airport.Code`, `Airport.Name`, `Publication.Date`, `Report.Status`, `Registration.Number`, `Investigation.Type`, `Purpose.of.flight`.

Focused on professionally built airplanes, I filtered rows where `Aircraft.Type` was 'airplane' and `Professionally.Built` was 'yes'. `Injury.severity` values were grouped into 'Non-Fatal', 'Fatal', and 'Unavailable', consolidating data from `Total.Fatal.Injuries`.

Using a lambda function, I standardized case sensitivity and removed duplicates in the Make column. Rows with a small percentage of NaN values were dropped using `.dropna()`.

Remaining NaN values in `Total.Fatal.Injuries`, `Total.Serious.Injuries`, `Total.Minor.Injuries`, and `Total.Uninjured` were retained due to their significant count, avoiding noise addition. The cleaned dataframe now has 18 columns and over 65,000 entries.

## Exploratory Data Analysis
The following are findings from this analysis:

![alt text](https://github.com/ckucewicz/aircraft_safety_project/blob/master/Type%20of%20Engines.png)
* Almost 90% of reported accidents involved aircraft with a Engine Type classified as 'Reciprocating'

 ![alt text](https://github.com/ckucewicz/aircraft_safety_project/blob/master/Number%20of%20Engines.png)
* ~98% of reported accidents involved aircraft with either 1 or 2 engines

 ![alt text](https://github.com/ckucewicz/aircraft_safety_project/blob/master/Accidents%20by%20Flight%20Phase.png)
* Almost one-third of accidents (~31%) occurred during either the 'Landing' or 'Takeoff' phases of the flight

![alt text](https://github.com/ckucewicz/aircraft_safety_project/blob/master/Non-fatal_rates.png)
![alt text](https://github.com/ckucewicz/aircraft_safety_project/blob/master/death_toll.png)
* Based on metrics for lowest fatality rate, least number of deaths, and lowest number of deaths per flight, the safest brands of airplanes include:
  * Hiller
  * Schweizer
  * Stinson
  * Maule
  * Enstrom
  * Luscombe
  * Aeronca

## Conclusion

### Limitations 
While this dataset offers valuable information, it only includes data on flights which were involved in an accident or incident. As a result, any flights that result in a completely safe flight are not part of this data. Because of this, the analysis was limited to simply making recommendations regarding the least risky aircrafts. In other words, the least risky aircraft might not be the safest aircraft from the pool of all possible aircrafts, but within the data we have access to we are restricted to equating the least amount of risk with being the safest aircraft. A more comprehensive dataset including data on all flights (accidents as well as no accidents) would provide a more complete analysis with more informed recommendations about the safest aircrafts.

### Recommendations
This analysis leads to three recommendations for choosing the safest aircrafts:

* **Invest in aircraft that have more than two engines and are not classified as a reciprocating engine.** Aircraft with reciprocating engines are prone to more accidents (~90%). Similarly, aircraft with one or two engines were involved in ~98% of reported accidents.

* **Focus training of pilots on the Takeoff and Landing phases.** While there are many phases that pilots must master, accidents during the Takeoff and Landing phases account for almost one-third of all accidents (~31%).

* **Select aircraft made by one of the following companies: Hiller, Schweizer, Stinson, Maule, Enstrom, Luscombe, Aeronca, Air Tractor, Ayres.** Planes made by these aircraft manufacturers were found to hold the least amount of risk based on a combination of their non-fatal rate, deaths per flight, and overal number of deaths.
  
### Next Steps 
With these recommendations in mind, for next steps I would be interested in gathering and looking into two sets of data:

* price data for aircraft from the recommended companies, as the price will be a major factor in deciding which aircraft(s) to invest in
* pilot training program data to help make an informed decision for where to hire the pilots from

## Additional Information
View the full analysis in the [Jupyter Notebook](https://github.com/ckucewicz/aircraft_safety_project/blob/master/Notebook.ipynb).

View the [presentation](https://github.com/ckucewicz/aircraft_safety_project/blob/master/presentation_deliverables/Phase%201%20Final%20Project%20Presentation.pdf)

View the [dashboard](https://public.tableau.com/app/profile/chris.kucewicz/viz/AircraftSafetyDashboard/Dashboard2)

Contact Chris Kucewicz at [cfkucewicz@gmail.com](cfkucewicz@gmail.com) with additional questions.

## Repository Structure
```
├── analysis_visualizations
    ├── ...                                   # Visualizations from analysis
├── presentation_deliverables                 
    ├── Jupyter Notebook                      # pdf version of notebook used for analysis
    ├── Phase 1 Final Project Presentation    # non-technical presentation slideshow
    ├── aircraft_safety_dashboard             # Tableau dashboard
    └── ckucewicz_aircraft_safety_github.pdf  # pdf version of github repo
├── AviationData.csv
├── Notebook.ipynb
├── README.md
└── aircraft_safety_cleaned.csv
```

