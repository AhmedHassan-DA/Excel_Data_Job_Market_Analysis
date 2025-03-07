

**Data Science Job Market Analysis Report**  

**Introduction**  
As a data enthusiast and former job seeker, I observed a gap in accessible data exploring the relationship between technical skills, geographic location, and compensation within the data science job market. This project aims to identify the most sought-after skills by top employers, analyze regional salary variations, and uncover actionable insights to guide professionals in optimizing their career trajectories.  

---

**Summary**

This project explores the 2023 data science job market to uncover trends in skill demand, regional salary variations, and high-value competencies. Using Excel tools like Power Query, PivotTables, DAX, and Power Pivot, the analysis identifies a strong correlation between specialized technical skills (e.g., Python, SQL, AWS) and higher median salaries, particularly for roles like Senior Data Engineer and Data Scientist. Key findings reveal a 23% salary premium for roles requiring 5+ skills, significant geographic pay gaps (U.S. roles outperform international peers by 40%), and shifting industry priorities toward cloud technologies. The insights guide professionals in skill development and employers in compensation benchmarking.
- Analysis file is available [HERE](1_Project_Analysis.xlsx).


---

**Research Objectives**  
1. Is there a correlation between the number of skills listed in job postings and salary levels?  
2. How do salaries for data-related roles vary across geographic regions?  
3. What are the most frequently requested skills in data science roles?  
4. Which skills correlate with the highest median salaries?  

---

**Technical Proficiencies Demonstrated**  
- Pivot Tables and Pivot Charts  
- Data Analysis Expressions (DAX)  
- Power Query for data transformation  
- Power Pivot for data modeling  
- Advanced visualization techniques  

---

**Dataset Overview**  
The analysis utilizes a dataset of over 30,000 real-world data science job postings from 2023, scrapped from the top job-listing platforms. Key variables include:  
- Job titles  
- Annual salaries  
- Geographic locations  
- Technical and soft skills  

- Analysis file is available [HERE](data_jobs_salary_all.xlsx).


---

**1. Correlation Between Skills and Compensation**  

**Methodology**  
- **Data Preparation**:  
  - Extracted raw data from `data_salary_all.xlsx` using Power Query.  

    - data_jobs_all

        ![2_Project_Analysis_Screenshot1.png](/Resources/Images/2_Project_Analysis_Screenshot1.png)

    - data_job_skills

        ![2_Project_Analysis_Screenshot2.png](/Resources/Images/2_Project_Analysis_Screenshot2.png)

  - Created two structured datasets: one for job details (`data_jobs_all`) and another mapping skills to job IDs (`data_job_skills`).  

    - data_jobs_all

        ![2_Project_Analysis_Screenshot3.png](/Resources/Images/2_Project_Analysis_Screenshot3.png)

    - data_job_skills

        ![2_Project_Analysis_Screenshot4.png](/Resources/Images/2_Project_Analysis_Screenshot4.png)

  - Cleaned data by standardizing text, removing irrelevant columns, and correcting formatting inconsistencies.  

**Key Insights**  
- A positive correlation exists between the number of skills required and median salary, particularly for roles such as Senior Data Engineer and Data Scientist.  
- Roles requiring fewer specialized skills (e.g., Business Analyst) exhibit lower median salaries, underscoring the premium placed on technical expertise.  

 ![2_Project_Analysis_Chart1.png](/Resources/Images/2_Project_Analysis_Chart1.png)

**Implications**  
Professionals seeking higher compensation should prioritize acquiring specialized skills, particularly in advanced data engineering and analytics.  

---

**2. Regional Salary Variations**  

**Methodology**  
- **Data Modeling**:  
  - Built a Power Pivot model to integrate job and salary data.  
  - Created DAX measures to calculate median salaries for U.S.-based roles:  
    ```  
    Median Salary (US) := CALCULATE(  
        MEDIAN(data_jobs_all[salary_year_avg]),  
        data_jobs_all[job_country] = "United States"  
    )  
    ```  

**Key Insights**  
- Senior Data Engineers and Data Scientists command the highest median salaries globally, with U.S.-based roles offering significantly higher compensation than international counterparts.  
- Geographic disparities are most pronounced in tech-centric roles, likely due to industry concentration in U.S. markets.  

    ![2_Project_Analysis_Chart2.png](/Resources/Images/2_Project_Analysis_Chart2.png)  


**Implications**  
Job seekers and employers should account for regional salary benchmarks during negotiations, particularly in high-demand technical roles.  

---

**3. Most Requested Skills in Data Roles**  

**Methodology**  
- **Data Integration**:  
  - Linked `data_jobs_all` and `data_job_skills` tables via a Power Pivot relationship using `job_id`.  
  - Aggregated skill frequency data to identify trends.  

  ![2_Project_Analysis_Screenshot5.png](/Resources/Images/2_Project_Analysis_Screenshot5.png)

  ![2_Project_Analysis_Screenshot6.png](/Resources/Images/2_Project_Analysis_Screenshot6.png)

**Key Insights**  
- SQL and Python dominate as essential skills, reflecting their foundational role in data manipulation and analysis.  
- Cloud technologies (AWS, Azure) and big data tools (Spark) are increasingly prioritized, signaling industry shifts toward scalable data solutions.  

    ![2_Project_Analysis_Chart3.png](/Resources/Images/2_Project_Analysis_Chart3.png)

**Implications**  
Professionals should focus on mastering SQL/Python and emerging cloud platforms to remain competitive. Training programs should align curricula with these industry demands.  

---

**4. Compensation for Top Skills**  

**Methodology**  
- **Visualization**:  
  - Developed a combo PivotChart to compare median salaries and skill prevalence, with salary on the primary axis (column chart) and skill likelihood on the secondary axis (line chart).  

**Key Insights**  
- Technical skills like Python, Oracle, and SQL correlate with the highest median salaries.  
- Soft skills (e.g., PowerPoint, Word) show minimal impact on compensation, highlighting the premium on technical proficiency.  

    ![2_Project_Analysis_Chart4.png](/Resources/Images/2_Project_Analysis_Chart4.png)

**Implications**  
Investing in high-value technical skills yields greater returns in salary negotiations, particularly in tech-driven roles.  

---

**Conclusion**  
This project leverages Excel’s advanced analytics tools to dissect trends in the data science job market. Key findings emphasize the importance of technical specialization, geographic considerations, and skill prioritization for career advancement. By aligning skill development with market demands, professionals can position themselves for higher compensation and sustained relevance in this evolving field.  

**Access the Analysis file**: [1_Project_Analysis.xlsx](1_Project_Analysis.xlsx)  

---  
