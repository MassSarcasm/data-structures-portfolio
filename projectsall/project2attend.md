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

**Are statewide economic trends including rising cost of homes and teenager employment associated with changes in Charlotte’s attendance and absence rates from 2019–2025 with affects from Covid-19?**

---

## Introduction

In this research project, I pulled several sources of data using APIs from the United States Census Bureau and the Charlotte Quality of Life Explorer to explore how high school attendance has been affected since the COVID-19 pandemic.

High school attendance has not fully recovered to pre-COVID-19 levels. Thomas S. Dee defines chronic absenteeism as “missing 10 percent or more of school for any reason” (Dee, 2024).

There are several variables that may contribute to chronic absenteeism. Morgan Polikoff and Nicolas Pardo explain that some contributing factors include students with disabilities and homelessness, with low-income students representing one of the largest groups affected by chronic absenteeism (Polikoff & Pardo, 2025).

This project examines economic trends alongside Charlotte-area high school attendance and absence data to explore whether these factors may be associated with changes in attendance following the COVID-19 pandemic.

---

## Data

I pulled several data points from the United States Census Bureau for North Carolina, focusing on economic factors that have changed since the COVID-19 pandemic.

The Census data revealed notable increases in several areas, including:

- Median household income
- Median homeowner costs
- Employment among teenagers ages 16–19

To provide additional insight, I pulled student absence data from the Charlotte Quality of Life Explorer.

I then combined and cleaned the data from these sources into a single dataset. This allowed me to compare changes in high school attendance and absences with several economic trends occurring during the same period.

Below are two visualizations that help illustrate these relationships.

---

## Visualizations

### High School Absences & Enrollment Graph

<img src="{{ '/assets/images/absence_enrollment_plot.png' | relative_url }}" 
     alt="High School Attendance, Absences, and Enrollment from 2013 to 2025"
     class="project-graph">

### Economic Conditions & Teenager Employment Graph

<img src="{{ '/assets/images/project2.png' | relative_url }}" 
     alt="Economic Conditions & Teenager Employment Graph from 2019 to 2024"
     class="project-graph">

---

## Conclusions

The data collected revealed several factors that could help explain chronic absenteeism for high schoolers.

The first graph shows that high school attendance dipped heavily during COVID-19 and never fully recovered. It also shows that student enrollment is not a major factor, as enrollment stays relatively consistent throughout the period. Toward the end of the graph, we see a slight recovery in absences, but as of last year, absences began to rise again.

Research findings support that chronic absenteeism increased following the COVID-19 pandemic (Dee, 2024; Polikoff & Pardo, 2025).

The second graph shows three rising factors that could play into attendance. The first is median household income. While household income has risen, it does not account for inflation. To help account for this, we pulled median owner costs, which shows us the rising cost to own and operate a home. These costs are rising at a similar rate to income.

We also pulled the variable for teenager employment for ages 16–19 since 2019. A study published in the Journal of Research on Adolescence found that adolescent employment can be associated with negative educational outcomes, particularly when students work longer hours (Vuolo et al., 2012).

These higher costs and employment factors can add stress to families and students attending high school for the first time. Increased household expenses and homeowner costs not only reduce available budgets but can also contribute to displacement for some families, potentially increasing absences and forcing teenagers to join the workforce at higher rates than we've seen before.

With the data provided by the U.S. Census Bureau and Charlotte Quality of Life Explorer, and the combination of higher teenage employment and rising housing costs, we can more clearly see some factors that may support the increase in chronic absenteeism.

---

## Sources

Dee, T. S. (2024). Higher chronic absenteeism threatens academic recovery from the COVID-19 pandemic. Proceedings of the National Academy of Sciences
[Read the article](https://doi.org/10.1073/pnas.2312249121)

Polikoff, M., & Pardo, N. (2025). Who's absent from school? A two-state examination of trends in absenteeism before and after COVID-19. American Enterprise Institute. 
[Read the report](https://eric.ed.gov/?id=ED677931)

Vuolo, M., Staff, J., & Mortimer, J. T. (2012). Adolescent work, school, and the transition to adulthood. Journal of Research on Adolescence
[Read the article](https://pmc.ncbi.nlm.nih.gov/articles/PMC7822572/)
