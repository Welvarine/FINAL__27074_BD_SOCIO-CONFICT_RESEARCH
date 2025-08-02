# FINAL__27074_BD_SOCIO-CONFICT_RESEARCH
# 🌍 Global Security & Socio-Economic Impact of Conflict (2000–2009)

## 📘 Project Overview

This capstone project analyses how **wars, armed conflicts, and insecurity** impacted global security and **socio-economic progress** during the decade **2000 to 2009**. Using a comprehensive dataset from the World Bank, we investigate the relationship between violence, governance, aid distribution, and development across regions and countries.

## 🎯 Research Objectives

- Measure the **rate and intensity of conflict** globally.
- Assess how the **rule of law and governance** relate to conflict severity.
- Identify the **top regions and countries** most affected by conflict.
- Compare socio-economic progress in **conflict vs non-conflict** nations.
- Provide visual, data-driven evidence to guide **policy and aid planning**.

## 📊 Dataset

- **Source**: [World Development Report 2011 Dataset](https://datacatalog.worldbank.org/search/dataset/0039027/World-Development-Report-2011)
- **Data Collection**:
```python
import pandas as pd

# Try with ISO-8859-1 encoding
df = pd.read_csv("WDR2011.csv", encoding='ISO-8859-1')
```
- **Years Analyzed**: 2000–2009
- **Shape**: 10,550 rows × 145 columns
- **Key Data Features**:
  - Battle deaths, conflict intensity (`PRIO_UCDP`)
  - One-sided violence, non-state violence
  - Governance indicators (`Ruleoflaw_WGI`)
  - Aid flows (`MileduFromUS_USAID`)
  - Regional and country identifiers
<img width="1039" height="178" alt="Final_EX1_rowsandcolumnsPNG" src="https://github.com/user-attachments/assets/4e22c70b-090a-46b4-b663-50bc59b91462" />


## 🧼 Data Cleaning Steps

- Filtered dataset to include only **2000–2009** entries.
  ``` python
  df_recent = df[df['Year'].between(2000, 2009)]

  ```
- Selected relevant columns for conflict and governance analysis.
  ```python
  # Keep rows of battle deaths or war intensity
  df_focus_clean = df_focus.dropna(subset=[
    'Cwbattledeaths_PRIO_UCDP',
    'CWintensity_PRIO_UCDP'
  ])
  selected_columns = [
    'Country', 'Countrycode', 'Year', 'RegionA', 'RegionB',
    'Cwbattledeaths_PRIO_UCDP',
    'CWintensity_PRIO_UCDP',
    'CWtype_PRIO_UCDP',
    'OnesidedStatec_UCDP',
    'OnesidedNonstate_UCDP',
    'Ruleoflaw_WGI',
    'MileduFromUS_USAID'
  ]

  
  ```
## Handled missing values and created binary indicators (e.g., `Missing_RuleofLaw`).
 ``` python
  df_focus_clean['Ruleoflaw_WGI'] = df_focus_clean['Ruleoflaw_WGI'].fillna(0)
  df_focus_clean['MileduFromUS_USAID'] = df_focus_clean['MileduFromUS_USAID'].fillna(0)

  ```
## Checked if the data had missing values
```python
df_focus_clean.isnull().sum()

```
<img width="262" height="286" alt="checking_null" src="https://github.com/user-attachments/assets/e8902230-0c83-4f21-af11-a6c78794265b" />


## Loading the cleaned data set 
  ```python
df_focus_clean.to_csv("cleaned_WDR2011_data.csv", index=False)
  ```

## 📈 Visualizations & Insights

| Plot Title                         | Purpose                                      |
|-----------------------------------|----------------------------------------------|
| 🔥 Battle Deaths Over Time        | Understand global trends in battle deaths     |
| ⚖️ Rule of Law vs Conflict Intensity | Examine correlation between governance & the conflict Intensity |
| 🗺️ Top 20 Affected Countries      | Identify countries with highest battle deaths|

**Battles Deaths, Region**

<img width="810" height="528" alt="BattlevsYear" src="https://github.com/user-attachments/assets/e6e3fe4d-f1a5-402c-a782-6689d9168f28" />

**Rule of Law, Conflict Intensity**

<img width="829" height="545" alt="RulevsConflictIntensity" src="https://github.com/user-attachments/assets/6f393221-d5f7-4471-8f36-67e562f37043" />

**Top 20 Affected  by Conflict Intensity Countries**

<img width="827" height="471" alt="Top20countries" src="https://github.com/user-attachments/assets/7bc282bf-389b-462b-ae87-0bd0c36a5960" />
**Top 5 Countries with Highest Battle death tolls**

<img width="814" height="528" alt="Top5DeathToll" src="https://github.com/user-attachments/assets/5cab4ada-9294-426a-bb1a-18d8d01d659c" />

## 🌐 Region Code Explanation

```python
# RegionB Codes (World Bank classification)
# 'EAP'  - East Asia and Pacific
# 'ECA'  - Europe and Central Asia
# 'LAC'  - Latin America and the Caribbean
# 'MENA' - Middle East and North Africa
# 'NA'   - North America
# 'SA'   - South Asia
# 'SSA'  - Sub-Saharan Africa
```

```python
import pandas as pd

# Try with ISO-8859-1 encoding
df = pd.read_csv("WDR2011.csv", encoding='ISO-8859-1')
```
