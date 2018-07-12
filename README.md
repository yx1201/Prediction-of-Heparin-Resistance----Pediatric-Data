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
-Target Patients: 708  (around 4.74%)  

<img src="https://github.com/yx1201/Prediction-of-Heparin-Resistance----Pediatric-Data/blob/master/picture/Population_Distribution.png" width="30%">

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
  
```
Give the example
```

And repeat

```
until finished
```

End with an example of getting some data out of the system or using it for a little demo

## Running the tests

Explain how to run the automated tests for this system

### Break down into end to end tests

Explain what these tests test and why

```
Give an example
```

### And coding style tests

Explain what these tests test and why

```
Give an example
```

## Deployment

Add additional notes about how to deploy this on a live system

## Built With

* [Dropwizard](http://www.dropwizard.io/1.0.2/docs/) - The web framework used
* [Maven](https://maven.apache.org/) - Dependency Management
* [ROME](https://rometools.github.io/rome/) - Used to generate RSS Feeds

## Contributing

Please read [CONTRIBUTING.md](https://gist.github.com/PurpleBooth/b24679402957c63ec426) for details on our code of conduct, and the process for submitting pull requests to us.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/your/project/tags). 

## Authors

* **Billie Thompson** - *Initial work* - [PurpleBooth](https://github.com/PurpleBooth)

See also the list of [contributors](https://github.com/your/project/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* Hat tip to anyone whose code was used
* Inspiration
* etc

