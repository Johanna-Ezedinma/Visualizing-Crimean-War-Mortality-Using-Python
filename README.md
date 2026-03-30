# Visualizing-Crimean-War-Mortality-Python

**Description:**
```
Coxcomb chart recreating Florence Nightingale's 1858 visualization of 
Crimean War mortality data using Python. Reveals that preventable disease,
not battle wounds was responsible for the majority of soldier deaths.
```

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![Status](https://img.shields.io/badge/Status-Complete-success?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)

# Crimean War Mortality Analysis 

**Python | Data Visualization | Historical Data Analysis**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/johanna-ezedinma/)

---

## 📊 Project Overview

Recreation of Florence Nightingale's famous Coxcomb chart using Python,
analyzing **24 months** of mortality data from the Crimean War (1854–1856)
across **3 causes of death** to reveal the devastating impact of preventable
disease on British soldiers.

**Key Metrics:**
- Total months analyzed: 24 (April 1854 — March 1856)
- Peak disease deaths: 2,761 (January 1855)
- Disease reduction by March 1856: 99.5% (from 2,761 to 15)
- Wounds as % of total deaths: consistently below 15%

---

## 🎯 Analysis Questions Answered

1. **What was the leading cause of death among soldiers?**
   - Preventable disease dominated overwhelmingly across both periods
   - Disease deaths dwarfed wounds and other causes in every winter month

2. **Did Nightingale's sanitation reforms make a measurable difference?**
   - Disease deaths fell from 2,761 in January 1855 to just 15 by March 1856
   - The reduction was gradual but consistent: reform worked month by month

3. **When did the outbreak begin and why?**
   - April to June 1854 show almost zero disease deaths
   - The outbreak escalated sharply from July 1854 as winter set in and
     hospitals became overcrowded

4. **How do wounds compare to disease as a cause of death?**
   - Wound deaths remained small throughout both periods
   - This directly contradicted public perception that battle injuries
     were the primary killer

---

## 📸 Chart Preview

![Nightingale Coxcomb Chart](Nightingale%20Coxcomb%20Chart.png)

---

## 🛠️ Technical Implementation

### Data Structure
- **Two Excel files** — one per 12-month period
- **5 columns per file:**
  - Month
  - Average Army Size
  - Disease Deaths
  - Wounds
  - Other Causes

### Data Cleaning Steps
1. Loaded both Excel files using pandas
2. Separated Month and Year into individual columns using `str.split()`
3. Reshaped data from wide to long format using `pivot_longer()` from janitor
4. Applied square root transformation to death counts for accurate area representation
5. Set correct chronological month ordering using `pd.Categorical`
6. Combined both periods using `pd.concat()`

### Key Transformation — Square Root Scaling
```python
# Square root ensures wedge AREA is proportional to deaths
# not just the radius without this large values will be exaggerated
nd1d["Sqrt_Count"] = np.sqrt(nd1d["Count"])
```

### Chart Code
```python
p1 = (ggplot(nd1d, aes("Month_Name", "Sqrt_Count", fill="Cause Of Death"))
+ geom_bar(stat="identity", alpha=0.6)
+ scale_fill_manual(values=["#D2BEB7", "#969696", "#4393c3"])
+ coord_polar()
+ labs(fill="Cause Of Death",
       subtitle="April 1854 to March 1855")
+ theme(
    axis_text_y=element_blank(),
    axis_title_y=element_blank(),
    axis_title_x=element_blank(),
    axis_ticks=element_blank(),
    panel_grid=element_blank(),
    panel_border=element_blank(),
    legend_position="bottom"
  )
+ ggsize(900, 600)
)
```

### Features Implemented
- ✅ Data reshaping from wide to long format
- ✅ Square root transformation for accurate area scaling
- ✅ Chronological month ordering using pd.Categorical
- ✅ Two-panel layout using gggrid
- ✅ Color-coded causes of death
- ✅ Clean polar coordinate chart matching Nightingale's original

---

## 💡 Key Findings & Recommendations

### Finding 1: Disease Was the Primary Killer
**Insight:** Preventable disease accounted for the overwhelming majority of
deaths throughout 1854–1855, far exceeding both wounds and other causes.

**Historical significance:** This directly contradicted the assumption that
battle wounds were the main cause of soldier deaths.

---

### Finding 2: Sanitation Reforms Saved Lives
**Insight:** After Nightingale implemented sanitation improvements in early
1855, disease deaths fell consistently month by month — from 2,761 in
January 1855 to just 15 by March 1856.

**Historical significance:** This is measurable proof that hygiene
intervention, not medical treatment, was the key to saving lives.

---

### Finding 3: The Outbreak Was Not Inevitable
**Insight:** April to June 1854 recorded almost zero disease deaths,
confirming that the later outbreak was caused by environmental conditions
— overcrowding, poor sanitation, contaminated water not by the war itself.

---

### Finding 4: Visualization Changes Decisions
**Insight:** A table of numbers could not communicate the same urgency that
the coxcomb chart delivered instantly. One glance at the two circles tells
the entire story.

**Historical significance:** This project is considered one of the earliest
examples of data visualization being used to drive policy change.

---

## 📈 Impact of Nightingale's Findings

| Period | Peak Disease Deaths | Wound Deaths | Outcome |
|---|---|---|---|
| Jan 1855 (before reform) | 2,761 | 83 | Crisis point |
| Jun 1855 (reform begins) | 802 | 31 | Gradual decline |
| Mar 1856 (post reform) | 15 | 0 | Near elimination |

---

## 🔧 Tools & Technologies

- **Python** — core programming language
- **pandas** — data loading and manipulation
- **numpy** — square root transformation
- **janitor** — pivot_longer for data reshaping
- **lets-plot** — coxcomb polar area chart
- **Jupyter Notebook** — development environment

---

## 📂 Repository Structure
```
Visualizing-Crimean-War-Mortality-Python/
├── README.md                        # This file
├── Nightingale_Viz.ipynb            # Full Jupyter notebook
├── raw_night_1854_1855.xlsx         # Dataset 1
├── raw_night_1855_1856.xlsx         # Dataset 2
└── nightingale_coxcomb.png          # Final chart
```

---

## 📊 Data Source

**Historical Crimean War Dataset**
- Collected by Florence Nightingale during the Crimean War (1853–1856)
- 24 months of mortality data
- 3 causes of death: Disease, Wounds, Other Causes
- Average army size recorded per month

---

## 🎓 Learning Outcomes

This project demonstrates:
- Data cleaning and reshaping using pandas and janitor
- Wide to long format transformation using pivot_longer
- Polar area chart construction using lets-plot
- Square root scaling for accurate visual representation
- Historical data storytelling through visualization

---

## 📝 Background

Florence Nightingale was a British nurse and statistician who served in
military hospitals during the Crimean War. She collected detailed mortality
data and used her Coxcomb chart to communicate her findings to British
government officials — convincing them to reform military hospital sanitation.

Her chart is considered one of the most influential data visualizations in
history, demonstrating that **most soldier deaths were preventable**.

---

## 👤 Author

**Johanna Ezedinma**
- 📧 Email: johannaezedinna@gmail.com
- 💼 LinkedIn: https://www.linkedin.com/in/johanna-ezedinma/
- 🐙 GitHub: https://github.com/Johanna-Ezedinma

---

## 🏆 Acknowledgments

- **Florence Nightingale** for the original dataset and visualization concept
- **SheCodeAfrica community** for continued learning opportunity and support

---

## 📌 Tags

`#Python` `#DataVisualization` `#FlorenceNightingale` `#CoxcombChart`
`#HistoricalData` `#pandas` `#LetsPlot` `#DataAnalysis`
`#CrimeanWar` `#PolarAreaChart`

---

**⭐ If you found this project helpful, please star this repository!**
