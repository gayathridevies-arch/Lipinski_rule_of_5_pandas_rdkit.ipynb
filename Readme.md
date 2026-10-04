# Lipinski_rule_of_5_pandas_rdkit.ipynb
Evaluating small molecule drug-likeness using Lipinski's Rule of 5 with RDKit and Pandas.
# Small Molecule Lipinski Rule of 5 Analysis

A Python-based computational chemistry workflow that loads small molecule drug candidates, calculates key physicochemical molecular descriptors using **RDKit**, evaluates compliance with **Lipinski's Rule of 5**, and visualizes property distributions using **Pandas** plotting.

---

## Project Overview
Lipinski's Rule of 5 (Ro5) evaluates oral bioavailability and drug-likeness of chemical compounds based on these parameter thresholds:

- **Molecular Weight (MW):** <= 500 g/mol
- **Partition Coefficient (LogP):** <= 5
- **Hydrogen Bond Acceptors (HBA):** <= 10
- **Hydrogen Bond Donors (HBD):** <= 5

---

## Tools & Libraries
- **Python 3.x**
- **RDKit**: Molecular structure parsing (`Chem.MolFromSmiles`) & descriptor calculation (`Descriptors`).
- **Pandas**: Tabular data manipulation and logic filtering.
- **Matplotlib / Pandas Plot**: Scatter plot rendering with threshold boundary lines and annotations.

---

## Analysed Dataset & Results

| Drug Name | Molecular Weight (g/mol) | LogP | HBA | HBD | Lipinski Status |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **Aspirin** | 180.16 | 1.31 | 3 | 1 | **Pass** |
| **Ibuprofen** | 206.29 | 3.07 | 1 | 1 | **Pass** |
| **Caffeine** | 194.19 | -1.03 | 3 | 0 | **Pass** |
| **Atorvastatin** | 558.65 | 6.31 | 4 | 4 | **Fail** |

---

## Key Findings
- **Aspirin, Ibuprofen, and Caffeine** meet all Ro5 criteria (<= 1 violation) and pass the oral bioavailability filter.
- **Atorvastatin** violates two parameters (MW = 558.65 > 500, LogP = 6.31 > 5), correctly failing the Lipinski filter.

