# Maji Ndogo Water Crisis Analysis – README

## 📌 Project Overview
The **Maji Ndogo Water Crisis Analysis** investigates water accessibility, contamination levels, infrastructure challenges, and community burden across the Maji Ndogo region. Using integrated datasets—water sources, pollution results, visits, and geographical information—the project generates insights and targeted recommendations for improving clean water availability.

---

## 🗂️ Datasets Used
### **1. Water Source Data (`water_source`)**
- Source ID
- Location ID
- Type of water source

### **2. Pollution Test Results (`well_pollution`)**
- Source ID
- Test results (Biological, Chemical, Clean)
- Contamination category

### **3. Visits Data (`visits`)**
- Queue time
- Visit frequency
- Source ID and Location ID

### **4. Location Data (`location`)**
- Address
- Town
- Province

### **5. Combined Analysis Table (`combined_analysis_table`)**
A merged table created for final insights and improvement recommendations.

---

## 🎯 Project Goals
- Evaluate contamination levels across water sources.
- Identify high-risk water sources in need of urgent action.
- Generate automated improvement recommendations.
- Highlight areas with high queue times or poor infrastructure.

---
## Insights
- 43% of our people are using shared taps. 2000 people often share one tap.
- Most water sources are rural.
- 31% of our population has water infrastructure in their homes, but within that group, 45% face non-functional systems due to issues with pipes, pumps, and reservoirs.
- 18% of our people are using wells of which, but within that, only 28% are clean.
- Our citizens often face long wait times for water, averaging more than 120 minutes.
- The queue is longer on Sartuday than other days.
- Queues are longer in the mornings and evenings.
- Wednesdays and Sundays have the shortest queues.

![Description](https://raw.githubusercontent.com/username/repo/main/image.png)

## Recommandations
- Focus our efforts on improving the water sources that affect the most people. Most people will benefit if we improve the shared taps first.
- Wells are a good source of water, but many are contaminated. Fixing this will benefit a lot of people.
- Fixing existing infrastructure will help many people. If they have running water again, they won't have to queue, thereby shorting queue times
for others. So we can solve two problems at once.
- Installing taps in homes will stretch our resources too thin, so for now if the queue times are low, we won't improve that source.

## Practical Solutions
- Drill wells for comminities using rivers
- Install RO filter if the well is contaminated with chemicals.
- Install UV and RO filter if the well is contaminated with biological contaminants.
- Diagnose local infrastructure if tap_in_home_broken.
- Install additional taps for shared taps with long queues(30min or more)

```sql
CASE
    WHEN results = 'Contaminated: Biological' THEN 'Install RO filter and UV filter'
    WHEN results = 'Contaminated: Chemical' THEN 'Install RO filter'
    WHEN source_type = 'river' THEN 'Drill wells'
    WHEN source_type = 'tap_in_home_broken' THEN 'Diagnose local infrastructure'
    WHEN source_type = 'shared_taps' AND time_in_queue >= 30 THEN CONCAT('Install ', FLOOR(time_in_queue / 30), ' taps nearby')
END AS Improvement
```

---

## 🚀 Technologies Used
- SQL (MySQL)
- Jupyter Notebook
- Excel (visualizations)
- GitHub for project documentation

---


## 🤝 Contributing
Contributions are welcome—new datasets, improved logic, documentation updates, or visualization enhancements.

---

## 📬 Contact
For questions or project collaboration:
**Email:** motsoaripuseletso8@gmai.com
