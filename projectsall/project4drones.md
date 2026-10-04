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

## Research Question
**Can we predict how much battery energy (in watt hours) a drone will use on a flight, based on its payload weight, flight speed, altitude, and weather conditions?**

---

## Introduction
I chose this topic as it pertains to my personal hobbies in flying different kinds of drones. As Zhang puts it in his article "Energy consumption is a critical constraint for drone delivery operations to achieve their full potential of providing fast delivery, reducing cost, and cutting emissions." Zhang. I find this interesting and personally I relate to this being I fly several different drones of varying sizes under several different conditions. Being able to create a prediction model based off several features helps give easier numbers to read and make additional calculations on. It can also speed up the calculation process if you have to do this for different types/size drones.

Depending on the types of drones and several features, we can predict the energy watt-hours consumed from a battery. This can help narrow reduce and relieve the amount of work needed when carrying out UAV drone procedures. There are an overwhelming amount of factors that go into play when using an unmanned UAV drone to do payload delivery. So if we can create a prediction model that can predict how many watt-hours consumed from a battery, that helps reduce several calculations down into one accurate prediction model.

That is what my models do in the demonstration below. Using flight data from Carnegie Mellon University (CMU) (Rodriguez), I had took thousands of flight logs and was able to use that data to create a prediction of how much a battery is consumed per flight depending on features such as flight time, payload weight, drone speed, drone altitude, and the average wind speed using linear regression and decision trees. I was able to take the data from then CSV and create my own variable for watt hours, which I will discuss further in how I handled the data.

---

## Data

For this research project I used a detailed CSV document that detailed several variables and flights provided by CMU. The data itself was fairly neat and had all the variable I needed for this project. I started by taking the csv file and checking for any missing values, which there were none. I then took the CSV and sorted it by routes down to "R1" (route 1) narrowing down the csv to 182 flights. 

The power for drones can be represented multiple ways. The amount of wattage a drone consumes is typically referred to as "watt-hours". Being so, I had to create my own variable to calculate the amount of watt-hours since the csv did not have that. No problem, I had enough data to be able to do that.  The csv had "battery_voltage" and "battery_current" which allowed me to create my own wattage variable called "power_W", W being for watts. During each flight, the drones sensor is constantly recording and reporting data by the second. To consolidate that I grouped the data by it's "flight" and "time" which shows the seconds between readings within each flight. I then created a variable for Joules called "energy_J" by multiplying "power_W" by "dt" (battery coltage x battery current X time step), which is needed to calculate watt-hours.

Now I can finally create watt-hours and group out data.. Since each flight is reporting data several times throughout the whole flight I simply divide "power_J" by 3600 to get watt hours and aggregate the data to finalize the flight logs needed to train my models.

## APA Citations

Rodrigues, T. A., Patrikar, J., Choudhry, A., Feldgoise, J., Arcot, V., Gahlaut, A., Lau, S., Moon, B., Wagner, B., Matthews, H. S., Scherer, S., & Samaras, C. (2021). In-flight positional and energy use data set of a DJI Matrice 100 quadcopter for small package delivery. Scientific Data, 8, 155. https://doi.org/10.1038/s41597-021-00930-x

Rodrigues, T. A., Patrikar, J., Oliveira, N. L., Matthews, H. S., Scherer, S., & Samaras, C. (2022). Drone flight data reveal energy and greenhouse gas emissions savings for very small package delivery. Patterns, 3(8), 100569. https://doi.org/10.1016/j.patter.2022.100569

Zhang, J., Campbell, J. F., Sweeney, D. C., II, & Hupman, A. C. (2021). Energy consumption models for delivery drones: A comparison and assessment. Transportation Research Part D: Transport and Environment, 90, 102668. https://doi.org/10.1016/j.trd.2020.102668
