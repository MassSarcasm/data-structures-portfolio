# [Josiah Bradshaw](index.md){: .site-title}

<div class="profile-links">

<a href="{{ '/assets/resume.pdf' | relative_url }}" download>
  Resume<br>
  <span class="download-text">Download</span>
</a>

<a href="https://github.com/MassSarcasm" target="_blank">
  GitHub<br>
  <span class="download-text">Link</span>
</a>

<a href="https://www.linkedin.com/in/josiahbradshaw/" target="_blank">
  LinkedIn<br>
  <span class="download-text">Link</span>
</a>

</div>

<div class="nav-links">

<a href="{{ '/' | relative_url }}">Home</a>
<a href="{{ '/aboutme' | relative_url }}">About Me</a>
<a href="{{ '/projects' | relative_url }}">Projects</a>
<a href="{{ '/blog' | relative_url }}">Blog</a>
<a href="{{ '/links' | relative_url }}">Links</a>

</div>

---

# Drone Battery Consumption Analysis

<div class="project-repo">

<a href="https://github.com/MassSarcasm/Battery-Consumption-Drone-Project" target="_blank" class="project-repo-button">
  View Project on GitHub
</a>

</div>

---

## Research Question

**Can we predict how much battery energy (in watt hours) a drone will use on a flight, based on its payload weight, flight speed, and altitude?**

---

## Introduction

I chose this topic as it pertains to my personal hobbies in flying different kinds of drones. As Zhang et al. (2021) put it, "Energy consumption is a critical constraint for drone delivery operations to achieve their full potential of providing fast delivery, reducing cost, and cutting emissions" (Abstract). I find this interesting and personally I relate to this being I fly several different drones of varying sizes under several different conditions. Being able to create a prediction model based off several features helps give easier numbers to read and make additional calculations on. It can also speed up the calculation process if you have to do this for different types/size drones.

Depending on the types of drones and several features, we can predict the energy watt-hours consumed from a battery. This can help reduce and relieve the amount of work needed when carrying out UAV drone procedures. There are an overwhelming amount of factors that go into play when using an unmanned UAV drone to do payload delivery. So if we can create a prediction model that can predict how many watt-hours consumed from a battery, that helps reduce several calculations down into one accurate prediction model.

That is what my models do in the demonstration below. Using flight data from Carnegie Mellon University (CMU) (Rodrigues et al., 2021), I used about 240,000 sensor readings from 181 flight logs and was able to use that data to create a prediction of how much a battery is consumed per flight depending on features such as payload weight, drone speed, and drone altitude using linear regression and decision trees. I was able to take the data from the CSV and create my own variable for watt hours, which I will discuss further in how I handled the data.

---

## Data

For this research project I chose to use linear regression and decision trees since watt-hours is a continuous number making it a regression problem. For the data I used a detailed csv document that detailed several variables and flights provided by CMU. The data itself was fairly neat and had most of the variables I needed. I had to create my own variable for "watt-hours" which I detail below.

I started by taking the csv file and checking for any missing values, which there were none. I then took the csv data and sorted it by routes down to "R1" (route 1) narrowing down the csv to 182 flights. One single flight had a payload of 750g so it was removed as it was an outlier. I also ended up removing average wind as a feature from the model. As we can see per the scatter plot. Average wind speed did not show a consistency in energy consumed. We also have to consider since the sensor for this is on the drone, it could be picking up the drone's wind from the propellers. 

I ended up removing average wind as a feature being it showed no clear relationship with energy which matches Rodrigues et al. (2022). I verified this showing model improvement without it vs with it.

The power for drones can be represented multiple ways. The amount of wattage a drone consumes is typically referred to as "watt-hours". Being so, I had to create my own variable to calculate the amount of watt-hours since the csv did not have that. No problem, I had enough data to be able to do that.

The csv had "battery_voltage" and "battery_current", multiplying those allowed me to create my own wattage variable called "power_W", W being for watts. During each flight, the drones sensor is constantly recording and reporting about five times per second. To consolidate that I calculated the time between readings within each flight to a variable called "dt".

I then created a variable for Joules called "energy_J" by multiplying "power_W" by "dt" (battery voltage x battery current X time step), which is needed to calculate watt-hours. I was able to prevent leakage by only using battery voltage and current to calculate watt hours and not using those as features. 

Now I can finally create watt-hours and group the data. Since each flight is reporting data several times throughout the whole flight I simply divide "energy_J" by 3600 to get watt hours and aggregate the data to finalize the flight logs needed to train my models.

I can now start to train linear regression and decision tree models using watt hours in combination with the features such as drone speed, payload weight, and altitude.

---

## Ethics and Limitations

All of my data was ethically sourced. The Carnegie Mellon University has the documentation and records for the flights made available to the public for use. While all the data needed was ethically pulled I did encounter some limitations.
To accurately train my model I needed "watt-hours" which is used to show how much power a drone consumes from a battery. I had to create this variable myself and was able to achieve this in python.

Consequences of wrong/under predictions can lead to safety issues and loss of equipment. If a drone were to run out of battery mid flight several issues present themselves. The drone and or package itself can be damaged or lost. The drone could also cause damage to property, for example it runs out of battery over someone's property or vehicle. Overestimating is safer in this specific research problem.

Real world usage of this model can be used as a planning aid. For example, companies such as Walmart have started using drones to deliver packages to houses. Having a model that can predict battery consumption can be vastly important to this specific example to help guarantee more deliveries and prevent any loss described above.

Possible limitations to this problem could be that this is based off of one drone model, the DJI Matrice 100, so this may not apply to other drones or additional calculations will be required to fit the model to that specific drone. More expansive testing could help improve model accuracy. So using more than one route or testing site could help improve accuracy. This model should be used as a planning aid in drone routes rather than as a specific guarantee.  

---

## Visualizations

### Distribution of Energy Used

<img src="{{ '/assets/images/Distro_Energy_Used.png' | relative_url }}"
     alt="Distribution of Energy Used"
     class="project-graph">

---

### Variables Compared to Other Variables

<img src="{{ '/assets/images/Variables_VS_Variables.png' | relative_url }}"
     alt="Variables Compared to Other Variables"
     class="project-graph">

---

### Model Improvement After Training

<img src="{{ '/assets/images/modelimprovement.png' | relative_url }}"
     alt="Model Improvement After Training"
     class="project-graph">

---

### Predicted vs Actual

<img src="{{ '/assets/images/PredictedVsActual.png' | relative_url }}"
     alt="Predicted vs Actual"
     class="project-graph">

---

## Results

The results proved to be fairly successful for the models trained. Each model was trained on 144 flights and tested on 37 flights it had never seen. The baseline for each model was a prediction of an average 21 watt hour for every flight without features. Then with features applied the model was trained giving its predictions. 

The MAE, which is the average prediction error in watt-hours (Wh), had a baseline of 3.72 before training the model. After training the linear regression model improved to a MAE of 1.29 and R² of 0.895. The decision tree model performed best with a MAE of 0.56 and R² of 0.970 with an 85% improvement from the baseline. Speed and altitude had the biggest effect on the trees with payload weight being the least.
After training each model, it has been shown that yes a drone's battery energy consumption can be predicted accurately by payload, speed, and altitude.

---

## Code & AI Disclosure
AI was used, specifically Claude AI by Anthropic, Opus 5.5 to help create visuals for research question, help clean up typos, and help properly cite APA citations. GitHub link above provides link to Jupyter Notebook showing code and models trained. 


## APA Citations

Rodrigues, T. A., Patrikar, J., Choudhry, A., Feldgoise, J., Arcot, V., Gahlaut, A., Lau, S., Moon, B., Wagner, B., Matthews, H. S., Scherer, S., & Samaras, C. (2021). In-flight positional and energy use data set of a DJI Matrice 100 quadcopter for small package delivery. Scientific Data, 8, 155. https://doi.org/10.1038/s41597-021-00930-x

Rodrigues, T. A., Patrikar, J., Oliveira, N. L., Matthews, H. S., Scherer, S., & Samaras, C. (2022). Drone flight data reveal energy and greenhouse gas emissions savings for very small package delivery. Patterns, 3(8), 100569. https://doi.org/10.1016/j.patter.2022.100569

Zhang, J., Campbell, J. F., Sweeney, D. C., II, & Hupman, A. C. (2021). Energy consumption models for delivery drones: A comparison and assessment. Transportation Research Part D: Transport and Environment, 90, 102668. https://doi.org/10.1016/j.trd.2020.102668
