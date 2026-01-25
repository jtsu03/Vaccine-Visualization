****Pediatric Therapeutic Errors During the Tripledemic (APAP vs IBU)
Overview****

This project analyzes pediatric poison center case data to visualize therapeutic dosing errors (TEs) involving acetaminophen (APAP) and ibuprofen (IBU) among children under 18. The goal is to compare TE patterns before vs during the tripledemic-era medication shortage, focusing on why dosing errors occurred and whether the distribution of error reasons changed across periods.

**Research Question**
Did the distribution of therapeutic error reasons for pediatric APAP/IBU cases change during the tripledemic medication shortage compared to the prior year?

**Data**

Population: Pediatric cases (age < 18 years)

Medications:

APAP (acetaminophen)

IBU (ibuprofen)

Files Used:

2023_Data_Vaccine.xlsx (sheet: Original)

Data_2022_Vaccine.xlsx (sheet: Sheet1)

Key fields used in analysis/plots:

Date, Case #

Reason For TE(VDL)

Medication indicator (mapped to APAP/IBU)

Sex (mapped to Female/Male)

Due to med shortage (mapped to Yes/No, if present)

**Study Period Definition**

The code creates a custom “season” comparison aligned with the tripledemic window:

Pre-shortage baseline period: 11/01/2021 – 03/31/2022 (labeled "2022" in the code)

Tripledemic/shortage period: 11/01/2022 – 03/31/2023 (treated as the comparison season; labeled "2023" in the code)

Note: In the current code, any date outside 11/01/2021–03/31/2022 is assigned to "2023". If your dataset includes additional months outside 11–03, those will be grouped into "2023" unless filtered.

**Methods**
1) Data Preparation

Loads 2022 and 2023 Excel sheets and combines them using an outer merge

Cleans and standardizes variables, including:

Parsing Date into datetime (with coercion for errors)

Mapping coded categorical fields to readable labels:

Sex: 1 → Female, else Male

Medication: 1 → APAP, else IBU

Due to med shortage: 1 → Yes, else No

Renames columns for clarity (dose, sex, medication, dosage form, outcomes, TE reason)

2) Visualization

Creates bar charts showing case counts:
- Overall counts by Reason For TE(VDL)
- Counts by Year × Reason For TE(VDL)
- Counts by Custom Period (baseline vs tripledemic season) × Reason For TE(VDL)

**Final plot:**

X-axis: Reason For TE (VDL code category)
Y-axis: Number of pediatric cases (Case # count)
Legend: Baseline period vs tripledemic/shortage period

Findings (What the Visualization Shows)

From the “baseline vs tripledemic season” bar chart:
- Therapeutic errors occur across multiple Reason For TE(VDL) categories, and the visualization highlights which TE reasons are most common in each period.
- Comparing the two seasons makes it easy to see whether certain TE reasons become more or less prevalent during the tripledemic/shortage window.
- The results support a practical takeaway: during high illness seasons and shortages, caregiver dosing complexity may shift the mix of error types, even if total volume changes are not the main focus here.

This analysis is descriptive and visualization-based. It shows associations and distributional differences between periods; it does not establish causality.

**Tools & Tech**

Python

pandas, NumPy

matplotlib
