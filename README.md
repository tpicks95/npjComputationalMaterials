# Benchmarking model-based design of experiment approaches with a pharmaceutical crystallisation emulator

**Contents**

In this github you will find the following:

1. An interative version of Figure 5 from the manuscript https://tpicks95.github.io/npjComputationalMaterials/plot.html and also Figure 8 (download the HTML file GBvsGP](https://tpicks95.github.io/npjComputationalMaterials/GBvsGP.html)

2. gPROMS population balance model

3. CSV file of the 20,000 generated experiments from the PBM

4. Python notebook with the random forest model and initial sampling and Bayesian optimisation model (Note: the above csv has to be downloaded and filepath changed in the code)


**Instructions for using the emulator**
1. Install the relevent libraries e.g., Obsidian-apo, pandas, scitkit-learn
2. Name the parameters and targets for which you will use later in your optimisation rounds - parameters are important, targets less so (otherwise the RF won't give predictions if parameters are left blank later)
3. State the location of the PBM simulated dataset
4. Run the RF model - it saves the scalar and the model to be used later
5. Scale your experimental suggestions to be used by the model by using: **scaler.transform(df_suggestions)** where df_suggestions is a dataframe of initial experiments or MB-DoE led experiments
6. Emulate results to your suggested experiments by using: **model.predict(df_scaled_suggestions)**
