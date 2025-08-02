# FINAL__27074_BD_SOCIO-CONFICT_RESEARCH
# 🌍 Global Security & Socio-Economic Impact of Conflict (2000–2009)

## 📘 Project Overview

This capstone project analyzes how **wars, armed conflicts, and insecurity** impacted global security and **socio-economic progress** during the decade **2000 to 2009**. Using a comprehensive dataset from the World Bank, we investigate the relationship between violence, governance, aid distribution, and development across regions and countries.

## 🎯 Research Objectives

- Measure the **rate and intensity of conflict** globally.
- Assess how **rule of law and governance** relate to conflict severity.
- Identify the **top regions and countries** most affected by conflict.
- Compare socio-economic progress in **conflict vs non-conflict** nations.
- Provide visual, data-driven evidence to guide **policy and aid planning**.

## 📊 Dataset

- **Source**: [World Development Report 2011 Dataset](https://datacatalog.worldbank.org/search/dataset/0039027/World-Development-Report-2011)
- **Data Collection:
```python
import pandas as pd

# Try with ISO-8859-1 encoding
df = pd.read_csv("WDR2011.csv", encoding='ISO-8859-1')
```
- **Years Analyzed**: 2000–2009
- ``` python
  df_recent = df[df['Year'].between(2000, 2009)]

  ```
- **Shape**: 10,550 rows × 145 columns
- **Key Data Features**:
  - Battle deaths, conflict intensity (`PRIO_UCDP`)
  - One-sided violence, non-state violence
  - Governance indicators (`Ruleoflaw_WGI`)
  - Aid flows (`MileduFromUS_USAID`)
  - Regional and country identifiers

## 🧼 Data Cleaning Steps

- Filtered dataset to include only **2000–2009** entries.
- Selected relevant columns for conflict and governance analysis.
- Handled missing values and created binary indicators (e.g., `Missing_RuleofLaw`).
- Created `ConflictStatus` column to classify countries.

## 📈 Visualizations & Insights

| Plot Title                         | Purpose                                      |
|-----------------------------------|----------------------------------------------|
| 🔥 Battle Deaths Over Time        | Understand global trends in battle deaths     |
| 🌍 Deaths by Region               | Compare conflict impact across regions        |
| ⚖️ Rule of Law vs Battle Deaths   | Examine correlation between governance & war |
| 📦 Conflict Intensity Distribution| Visualize spread of conflict intensity levels |
| 🗺️ Top 10 Affected Countries      | Identify countries with highest battle deaths|

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
