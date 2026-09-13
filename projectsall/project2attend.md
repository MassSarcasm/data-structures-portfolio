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

# Post Covid-19 High School Attendance Analysis

## Research Question

**Are statewide economic trends associated with changes in Charlotte’s attendance and absence rates from 2019–2025?**

---

## Introduction

In this research project, I pulled several sources of data using APIs from the **United States Census Bureau** and the **Charlotte Quality of Life Explorer** to explore how high school attendance has been affected since the COVID-19 pandemic.

High school attendance has not fully recovered to pre-COVID-19 levels. Thomas S. Dee defines chronic absenteeism as “missing 10 percent or more of school for any reason” (Dee, 2024).

There are several variables that may contribute to chronic absenteeism. Morgan Polikoff and Nicolas Pardo explain that some contributing factors include students with disabilities and homelessness, with low-income students representing one of the largest groups affected by chronic absenteeism (Polikoff & Pardo, 2025).

This project examines economic trends alongside Charlotte-area high school attendance and absence data to explore whether these factors may be associated with changes in attendance following the COVID-19 pandemic.

---

## Data

I pulled several data points from the **United States Census Bureau** for North Carolina, focusing on economic factors that have changed since the COVID-19 pandemic.

The Census data revealed notable increases in several areas, including:

- Median household income
- Median homeowner costs
- Employment among teenagers ages 16–19

To complement these economic indicators, I pulled student absence data from the Charlotte Quality of Life Explorer.

I then combined and cleaned the data from these sources into a single dataset. This allowed me to compare changes in high school attendance and absences with several economic trends occurring during the same period.

Below are two visualizations that help illustrate these relationships.

---

## Visualizations

### High School Attendance and Absences

<div class="project-visual">

<span>Attendance and Absence Graph</span>

</div>

This graph shows the change in high school attendance and absences from 2019 through 2025. Attendance declined significantly during the COVID-19 pandemic and has not returned to pre-pandemic levels.

Student enrollment remained relatively consistent throughout the period, suggesting that changes in enrollment alone do not explain the changes observed in attendance.

Towards the end of the period, there is a slight recovery in attendance and a corresponding decrease in absences. However, the most recent year shows an increase in absences again.

---

### Economic Trends and Teen Employment

<div class="project-visual">

<span>Economic Trends Graph</span>

</div>

The second graph shows three economic factors that may be associated with changes in attendance:

- Median household income
- Median homeowner costs
- Employment among teenagers ages 16–19

While median household income has increased, income alone does not account for changes in the cost of living. Median homeowner costs provide additional context by showing the increasing cost associated with owning and operating a home.

Teen employment is another factor worth considering. Vuolo, Staff, and Mortimer (2012) explain that increased adolescent employment has historically been associated with potential negative effects on school involvement and attendance.

---

## Conclusions

The data collected in this project highlights several factors that may help explain changes in chronic absenteeism among high school students.

The first visualization shows that high school attendance declined significantly during the COVID-19 pandemic and has not fully recovered. At the same time, student enrollment remained relatively consistent, suggesting that enrollment is not a primary explanation for the changes in attendance.

The second visualization highlights several economic trends that may be relevant to student attendance. Median household income has increased since 2019, but rising income does not necessarily mean that families have greater financial flexibility. Median homeowner costs have also increased, providing additional context about the growing cost of housing.

Teen employment also increased during the period examined. Research by Vuolo, Staff, and Mortimer (2012) suggests that increased work responsibilities among adolescents can negatively affect school involvement and attendance.

Together, these trends suggest that economic pressures may be associated with chronic absenteeism. Rising housing costs can place additional financial pressure on families, while increased teen employment may place additional demands on students themselves.

These factors could potentially contribute to increased absences through financial stress, changes in household circumstances, or students spending more time in the workforce.

The data from the U.S. Census Bureau and Charlotte Quality of Life Explorer therefore provides evidence of several trends occurring alongside the persistence of chronic absenteeism in Charlotte-area high schools. However, these trends represent associations rather than proof of direct causation. Further research would be needed to determine the extent to which each individual factor contributes to student absenteeism.

---

## Sources

Dee, T. S. (2024). Higher chronic absenteeism threatens academic recovery from the COVID-19 pandemic. Proceedings of the National Academy of Sciences
[Read the article](https://doi.org/10.1073/pnas.2312249121)

Polikoff, M., & Pardo, N. (2025). Who's absent from school? A two-state examination of trends in absenteeism before and after COVID-19. American Enterprise Institute. 
[Read the report](https://eric.ed.gov/?id=ED677931)

Vuolo, M., Staff, J., & Mortimer, J. T. (2012). Adolescent work, school, and the transition to adulthood. Journal of Research on Adolescence
[Read the article](https://pmc.ncbi.nlm.nih.gov/articles/PMC7822572/)
