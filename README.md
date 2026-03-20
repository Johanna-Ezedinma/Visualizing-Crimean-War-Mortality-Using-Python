# Visualizing the Causes of Death in the Crimean War Using a Coxcomb Plot

This project recreates Florence Nightingale's famous Coxcomb chart using Python. 
Nightingale used this visualization in 1858 to convince the British government to 
reform military hospital sanitation, making it one of the most influential data 
visualizations in history.

## Chart Preview
![Nightingale Coxcomb Chart](Replicated nightingale_coxcomb.png)
```

## Project Overview

Florence Nightingale collected data on causes of death among soldiers during the 
Crimean War (1853–1856). She discovered that most deaths were not from battle wounds 
but from preventable diseases caused by poor sanitation. This project recreates her 
polar area chart to tell that same story using modern Python tools.

## Tools and Technologies

- **Python** (Pandas, NumPy, Matplotlib, Janitor, Lets-Plot) for data manipulation and visualization
- **Jupyter Notebook** for code development and documentation

## Dataset

- raw_night_1854_1855.xlsx — monthly death counts from April 1854 to March 1855
- raw_night_1855_1856.xlsx — monthly death counts from April 1855 to March 1856

Each dataset contains:
- -Month
- Average Army Size
- Disease Deaths
- Wounds
- Other Causes

## Key Findings

- Preventable disease (blue) was the dominant cause of death throughout 1854–1855
- Deaths from disease dropped dramatically in the second period (1855–1856) following 
  Nightingale's sanitation reforms
- The early months of April to June 1854 show almost no disease deaths — troops had 
  only just arrived and the outbreak had not yet begun
- Wound-related deaths remained consistently small throughout both periods

## Project Benefits

- Demonstrates how data visualization can communicate life-saving insights to 
  non-technical audiences
- Shows the complete data analysis workflow: raw data → cleaning → exploration → visualization
- Recreates a historically significant chart using modern open-source Python tools

## Libraries Used

| Library | Purpose |
|---|---|
| pandas | Loading and organizing data |
| numpy | Mathematical calculations (square root transformation) |
| janitor | Data reshaping using pivot_longer |
| lets-plot | Creating the coxcomb polar area chart |
