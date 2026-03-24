# SIMPLE ML MODELS FOR PREDICTING THERMODYNAMIC PROPERTIES OF N-HEXANE
![Python](https://img.shields.io/badge/Python-3.x-blue)
![pandas](https://img.shields.io/badge/pandas-✓-green)
![matplotlib](https://img.shields.io/badge/matplotlib-✓-green)
![scikit-learn](https://img.shields.io/badge/scikitlearn-✓-green)
![seaborn](https://img.shields.io/badge/seaborn-✓-green)
[NIST Database](https://webbook.nist.gov/cgi/fluid.cgi?TLow=&THigh=&TInc=&Digits=5&ID=C110543&Action=Load&Type=SatP&TUnit=K&PUnit=bar&DUnit=mol%2Fl&HUnit=kJ%2Fmol&WUnit=m%2Fs&VisUnit=uPa*s&STUnit=N%2Fm&RefState=DEF)

## Installation

pip install numpy pandas matplotlib scipy sklearn

## Description 
Imagine having a molecule whose vapour pressure you need to know at any given temperature, some would turn to equations or formulas, others to programs. What if you could use ML as a tool to predict those values?
In this project i seek to know which simple ML model can reliably predict the thermodynamic properties of Vapour Pressure, Specific Heat Capacity for Liquid and Vapour states of N-Hexane.

## Data use and Methodology
- The data used for this project is for free use at https:/nist.gov, specifically at the Saturation Properties for Hexane - Temperature Increments database.

- For practical reasons, the temperature range was truncated from 177.8 K to 490 K, this to avoid, for reasons of linearity and simplicity, the data belonging to the critical point area and adjacent areas.

- The variables were transformed with ln() to improve linear correlation and three independent models were specified, T→ln(P), T→ln(Cp_L), T→ln(Cp_V). Being P: Vapour Pressure, Cp_L: Specific Heat Capacity for Liquid State, Cp_V: Specific Heat Capacity for Vapour State.

<img width="1567" height="603" alt="N-HEXANE_EXP_GRAPHS" src="https://github.com/user-attachments/assets/9fff617c-fcae-4304-962b-5d1c00e0ae6d" />


## Results

| Model | R² Lineal | R² Polynomial |R² Random Forest| RMSE Lineal | RMSE Polynomial | RMSE Random Forest |
|--------|-----------|---------------|--------------|-------------|-----------------|------------------|
| T→ln(P) | 0.909 | 0.999 |0.999996| 1.182 | 0.100 |0.023|
| T→ln(Cp_L) | 0.934 | 0.990 |0.999995| 0.057 | 0.019 |0.002|
| T→ln(Cp_V) | 0.950 | 0.990 |0.999995| 0.073 | 0.031 |0.001|

# Final conclusion; ¿Can ML Reliably Predict Thermodynamic Properties of N-hexane From Just Temperature?
The answer to this question is YES, ML can predict the thermodynamic properties of n-hexane from just temperature, but only in a defined range. In this project it is proved that the models used have a strong and clear limitation, they cannot predict properties and do not generalize correctly outside of the defined range, and also, The Random Forest cannot physically interpret the properties of n-hexane. Thus, we can infer that if we give the models data greater than 490 Kelvin (close to the critical point), the predictions become unreliable and the models do not adapt to the data.
