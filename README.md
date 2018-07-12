# Prediction of Heparin Resistance--Pediatric Data

## Heparin Resistance

Heparin Resistance is defined by the inability to reach therapeutic level with rising doses of Heparin.

#### Important Indicators

- Heparin(Units/kg/hr)
- Antithrombin
- Lab values for monitoring the effectiveness of Heparin:
  - PTT (sec)
  - Anti-Xa (I.U./mL)


<img src="https://github.com/yx1201/Prediction-of-Heparin-Resistance----Pediatric-Data/blob/master/picture/eid_example.png" width="30%">

## Objective

Predict whether a child will be Heparin Resistance after a period of measurement of physiologic observations, laboratory results, administered drugs and interventions.
- Prediction at the time before Heparin dosage
- Prediction at the time after certain hours of Heparin administered



## Data Set
Patients in both PICU and Cticu who had Heparin administered at any time and had either PTT or Anti-Xas measurement
-Total Patients: 14940 

<img src="https://github.com/yx1201/Prediction-of-Heparin-Resistance----Pediatric-Data/blob/master/picture/Population_Distribution.png" width="30%">

-Target Patients: 708  (around 4.74%) 

<img src="https://github.com/yx1201/Prediction-of-Heparin-Resistance----Pediatric-Data/blob/master/picture/total_age_bin.png" width="25%">


## Preprocessing
### Create a list of resonable binary target varaibla that defines Heparin Resistance

- Heparin dosage of 35/40/45 unites in each encounter at any time
  - Children who aquired maximum of Heparin Dosage larger than 30/35/40 are considered to be Heparin Resistance.
- Titration Difficulty: Some kids were harder to titrate
  - Children who had number of Heparin Titration larger than 15/20 are considered to be Heparin Resistance
- Two lab indicator that monitor the effect of Heparin
  - Children who had either maximum of PTT less than 50 or maximum of Anti-Xa less than 0.3 are considered to be Heparin Resistance.
- Antithrombin: When Heperin Resistance occurs, increasing dosage of Heparin is insufficient. Then, we treat the kid with the Antithrombin Supplemantation, which active the anticoagulate effect of Heparin.
  - Children who had Antithrombin administered are considered to be Heparin Resistance.
  
Then, we have the following table shows the distribution of classes and age-bin for each defined target variable.
<img src="https://github.com/yx1201/Prediction-of-Heparin-Resistance----Pediatric-Data/blob/master/picture/Y_Distribution.png" width="80%">

### Create a time reference (in hour) for the initial administration of Heparin

<img src="https://github.com/yx1201/Prediction-of-Heparin-Resistance----Pediatric-Data/blob/master/picture/Absolute_Time.png" width="20%"><img src="https://github.com/yx1201/Prediction-of-Heparin-Resistance----Pediatric-Data/blob/master/picture/hour.png" width="20.5%">

### Cut data for a specific time period after the first administration of Heparin
-0 hour 
  - cut the data at hour 0, where is right at the time of the Administration of Heparin 
  - predict whether a child will be Heparin Resistance using the data before Heparin Administered.
<img src="https://github.com/yx1201/Prediction-of-Heparin-Resistance----Pediatric-Data/blob/master/picture/0-hr_cut.png" width="30%">

-24 hours
  - cut the data at hour 24, where is 24 hours after the first administration of Heparin
   - predict whether a child will be Heparin Resistance after 24 hours of the Heparin Administration.
<img src="https://github.com/yx1201/Prediction-of-Heparin-Resistance----Pediatric-Data/blob/master/picture/24-hr_cut.png" width="31%">


