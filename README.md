# SIMPLE ML MODELS FOR PREDICTING THERMODYNAMIC PROPERTIES OF N-HEXANE
![Python](https://img.shields.io/badge/Python-3.x-blue)
![pandas](https://img.shields.io/badge/pandas-✓-green)
![matplotlib](https://img.shields.io/badge/matplotlib-✓-green)
[NIST Database](https://webbook.nist.gov/cgi/fluid.cgi?TLow=&THigh=&TInc=&Digits=5&ID=C110543&Action=Load&Type=SatP&TUnit=K&PUnit=bar&DUnit=mol%2Fl&HUnit=kJ%2Fmol&WUnit=m%2Fs&VisUnit=uPa*s&STUnit=N%2Fm&RefState=DEF)

## Description 
Imagine if you had a molecule which you had to know its vapour pressure property at any given temperature, some would turn to ecuations or formulas, others to programs. What if you could use ML as a tool to predict those values?
In this project i seek to know which simple ML model can reliably predict the thermodynamic properties of Vapour Pressure, Specific Heat Capacity for Liquid and Vapour states of N-Hexane.

## Data use and Methodology
- The data used for this project is for free use at https:/nist.gov, specifically at the Saturation Properties for Hexane - Temperature Increments webhook.

- For practical reasons, the temperature range was truncated from 177.8 K to 490 K, this to avoid, for reasons of linearity and simplicity, the data belonging to the critical point area and adjacent areas.

- The variables were transformed with ln() to improve linear correlation and three independent models were specified, T→ln(P), T→ln(Cp_L), T→ln(Cp_V). Being P: Vapour Pressure, Cp_L: Specific Heat Capacity for Liquid State, Cp_V: Specific Heat Capacity for Vapour State.

## Results

| Model | R² Lineal | R² Polynomial |R² Random Forest| RMSE Lineal | RMSE Polynomial | RMSE Random Forest |
|--------|-----------|---------------|--------------|-------------|-----------------|------------------|
| T→ln(P) | 0.909 | 0.999 |0.999996| 1.182 | 0.100 |0.023|
| T→ln(Cp_L) | 0.934 | 0.990 |0.999995| 0.057 | 0.019 |0.002|
| T→ln(Cp_V) | 0.950 | 0.990 |0.999995| 0.073 | 0.031 |0.001|

Practically, a random forest model would be recommended for the prediction of the thermodynamic properties of vapor pressure, Liquid Cp and Vapor Cp,likewise, this model can be applied to petrochemical, vegetable oil and chemical synthesis industries.


