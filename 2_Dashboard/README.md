

**Excel-Based Data Science Salary Dashboard Report**  

---

**Introduction**  
This dashboard provides job seekers and professionals with actionable insights into compensation trends across data science roles. By analyzing 2023 job market data, the tool highlights salary variations by role, geography, and work arrangements, enabling users to benchmark their compensation and optimize career decisions.  

---

**Research Objectives**  
1. Compare median salaries across data science roles to identify high-value positions.  
2. Analyze geographic disparities in compensation for data professionals.  
3. Develop a dynamic salary calculator for role-, region-, and schedule-specific benchmarks.  
4. Evaluate the impact of job schedule types (e.g., remote, hybrid) on salary offers.  

---

**Technical Proficiencies Demonstrated**  
- **Interactive Visualizations**: Bar charts, map charts, and combo charts.  
- **Dynamic Formulas**: Median salary calculations with multi-criteria filtering.  
- **Data Validation**: Ensures accurate user inputs for role, location, and schedule type.  
- **Advanced Excel Features**: Power Query, PivotTables, and DAX.  

---

**Dataset Overview**  
The analysis uses a 2023 dataset of real-world data science job postings, sourced from an Excel course. Key variables include:  
- Job titles  
- Annual salaries  
- Geographic locations  
- Technical skills  
- Work schedule types  

---

**1. Salary Benchmarking by Role**  

**Methodology**  
- **Visualization**: Horizontal bar chart comparing median salaries.  
- **Data Preparation**:  
  - Cleaned and structured data using Power Query.  
  - Filtered roles by job title, country, and schedule type.  

  ![Salary Comparison Chart](/Resources/Images/1_Salary_Dashboard_Chart1.png)  

**Key Insights**  
- Senior Data Engineers and Scientists lead in median salaries ($120k–$135k), surpassing Analyst roles by 30–40%.  
- Technical specialization (e.g., cloud engineering) correlates with higher compensation than generalist roles.  

**Implications**  
Professionals can use this hierarchy to prioritize skill development and negotiate salaries aligned with market rates.  

---

**2. Geographic Salary Disparities**  

**Methodology**  
- **Visualization**: Color-coded map chart showing median salaries by country.  
- **Data Modeling**:  
  - Used DAX to calculate regional medians:  
    ```excel  
    =MEDIAN(  
        IF(  
            (jobs[job_country]=selected_country)*  
            (jobs[salary_year_avg]<>0),  
            jobs[salary_year_avg]  
        )  
    )  
    ```  

  ![Global Salary Map](/Resources/Images/1_Salary_Dashboard_Country_Map.gif)  

**Key Insights**  
- U.S.-based roles average $118k, outpacing European and APAC markets by 40–60%.  
- Remote roles in emerging tech hubs (e.g., India, Eastern Europe) show competitive salaries.  

**Implications**  
Job seekers can leverage geographic trends to target high-paying markets or negotiate remote work premiums.  

---

**3. Dynamic Salary Calculator**  

**Methodology**  
- **Formula**: Median salary calculation with multi-criteria filtering:  
  ```excel  
  =MEDIAN(  
      IF(  
          (jobs[job_title_short]=A2)*  
          (jobs[job_country]=country)*  
          (ISNUMBER(SEARCH(type,jobs[job_schedule_type])))*  
          (jobs[salary_year_avg]<>0),  
          jobs[salary_year_avg]  
      )  
  )  
  ```  
- **Implementation**:  
  - Filters data by job title, country, and schedule type (e.g., remote, hybrid).  

  ![Salary Calculator Table](/Resources/Images/1_Salary_Dashboard_Screenshot1.png)  

**Key Insights**  
- Enables users to input criteria (e.g., "Data Scientist," "U.S.," "Remote") for tailored salary benchmarks.  

**Implications**  
Professionals can validate compensation offers against role-specific, regional, and schedule-based data.  

---

**4. Job Schedule Type Analysis**  

**Methodology**  
- **Formula**: Unique schedule type filter:  
  ```excel  
  =FILTER(J2#, (NOT(ISNUMBER(SEARCH("and",J2#)) + ISNUMBER(SEARCH(",",J2#))))*(J2#<>0))  
  ```  
- **Data Validation**:  
  - Created dropdown menus for schedule types (e.g., "Remote," "Hybrid") to prevent input errors.  

  ![Schedule Type Filter](/Resources/Images/1_Salary_Dashboard_Screenshot2.png)  

**Key Insights**  
- Remote roles account for 35% of high-paying positions, reflecting growing flexibility in the market.  

**Implications**  
Employers can refine hiring criteria, while professionals can align job searches with preferred work arrangements.  

---

**Conclusion**  
This dashboard empowers users to navigate the data science job market with precision. Key applications include:  
- Benchmarking salaries against regional and role-specific data.  
- Identifying high-value skills and certifications (e.g., cloud platforms).  
- Optimizing job search strategies for remote or hybrid opportunities.  

**Access the Dashboard**: [1_Salary_Dashboard.xlsx](1_Salary_Dashboard.xlsx)  
**Dataset and Files**: Available on GitHub for reproducibility.  

---  
