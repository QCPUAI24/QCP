## Quantum Conformal Prediction (QCP)

This repository contains code for "[Reliable Uncertainty Quantification in Quantum Machine Learning via Quantum Conformal Prediction]" submitted to UAI 2024.

### Dependencies

This program is written in python 3.9.7 and uses PyTorch 1.10.2.

### Basic Usage

- All the essential components of QCP can be found in the file 'classical_regression/set_predictors/quantum_conformal_prediction.py' (for classical regression eq.(22)) and in the file 'quantum_classification/quantum_conformal_prediction/qcp.py' (for quantum classification eq.(23)).
- PQC with different angle encodings (fixed, linear, non-linear angle encoding, see Fig. 4 of the Supplementary Material) can be found in the file 'classical_regression/quantum_circuit/PQC.py'.
- In order to deploy the above PQC to IBM Quantum NISQ devices, 'classical_regression/quantum_circuit/PQC_with_qiskit.py' can be useful.

### Regression task for classical data
    
-  Main file is 'classical_regression/main_regression.py', while the 'runs/regression' folder contains the required running shell scripts. 

### Classification task for quantum data
    
-  Main file is 'quantum_classification/main_classification.py'. By running 
    ```
    python main_classification.py --temperature <T for Gibbs state> --mode <'naive' or 'qcp'> --mode_cp <'vanilla' or 'weighted_histo'>
    ```
    one can execute "naive prediction" via 'naive'+'vanilla'; "QCP" via 'qcp'+'weighted_histo'; "CP" via 'qcp'+'vanilla'. Other settings can be found at the beginning of the main file.