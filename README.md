# Aircraft Safety Analysis
Author: [Chris Kucewicz](cfkucewicz@gmail.com)
## Business Understanding
### Background:
My company is planning to diversify its porfolio by extending to different 
markets. More specifically, my company is looking to invest in airplanes 
in order for their expansion to different markets to be successful.

### Business Goals:
This project is focusing on determining the risks of different aircrafts. 
Specifically, this project has the goal of identifying which aircrafts 
pose the least amount of potential risk. This information will be used in 
order to provide three recommendations to my company regarding the least risky
aircrafts to purchase.

### Business Success Criteria:
The success criteria for this project will be to provide three 
recommendations about the least risky aircrafts that my company should invest 
in. For this project, the term _least risky_ refers to types of aircrafts with 
the least amount of crashes, the least number of casualties, and the lowest fatality rate. 

## Data Understanding
The National Transportation Safety Board (NTSB) collects data on aviation 
accidents and incidents that occur in the United States (which include its 
territories) as well as international waters. This dataset includes 31 features and 88,889 observations/entries.

Each entry in the dataset represents an aircraft involved in an accident 
(or incident). For each aircraft there is a unique ID associated with the 
specific accident (or incident) the aircraft was involved in. Additional 
information is included about each entry, such as the accident (or 
incident) date, location, and number of injuries, as well as 
characteristics about the aircraft, such as the make, model, and number of 
engines

### Data Preparation

## Exploratory Data Analysis

## Conclusion

### Limitations 
While this dataset offers valuable information, it only includes data on flights which were involved in an accident or incident. As a result, any flights that result in a completely safe flight are not part of this data. Because of this, the analysis was limited to simply making recommendations regarding the _**least risky**_ aircrafts. In other words, the least risky aircraft might not be the safest aircraft from the pool of all possible aircrafts, but within the data we have access to we are restricted to equating the least amount of risk with being the safest aircraft. A more comprehensive dataset including data on all flights (accidents as well as no accidents) would provide a more complete analysis with more informed recommendations about the safest aircrafts.

### Recommendations
This analysis leads to three recommendations for choosing the safest aircrafts:

* **Invest in aircraft that have more than two engines and are not classified as a reciprocating engine.** Aircraft with reciprocating engines are prone to more accidents (~90%). Similarly, aircraft with one or two engines were involved in ~98% of reported accidents.

* **Focus training of pilots on the Takeoff and Landing phases.** While there are many phases that pilots must master, accidents during the Takeoff and Landing phases account for almost one-third of all accidents (~31%).

* **Select aircraft made by one of the following companies: Hiller, Schweizer, Stinson, Maule, Enstrom, Luscombe, Aeronca, Air Tractor, Ayres.** Planes made by these aircraft manufacturers were found to hold the least amount of risk based on a combination of their non-fatal rate, deaths per flight, and overal number of deaths.
  
### Next Steps 
Moving forward with these recommendations in mind, the company should research price information for aircraft from the recommended companies as the price will also be a major factor in deciding which aircraft(s) to invest in.

## Additional Information
View the full analysis in the Jupyter Notebook.

View the presentation

Contact Chris Kucewicz at [cfkucewicz@gmail.com](cfkucewicz@gmail.com) with additional questions.

## Repository Structure

