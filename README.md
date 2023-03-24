# ML-projects
Machine learning projects
This repository contains 3 machine learning projects.

## Hybrid solar/fossil-fuel gas turbine power system
This project focuses on the implementation of a hybrid solar/fossil-fuel gas turbine power system. The following files are included:

- `First_Principles_implementation.ipynb`: This notebook contains the implementation of a first-principles model of the system (neural network designed from scartch).

- `Keras_NN_Prediction.ipynb`: This notebook uses a neural network to predict the performance of the system.

- `Keras_First_Principles_comparison.ipynb`: This notebook compares the results of the neural network and first-principles models.

## Design and control of a solar PV power generation system:

This project focuses on the design and control of a solar PV power generation system. The following files are included:
- `Performance_Solar_PV.ipynb`: Part 1 of this project considers the performance of the solar panel design show above. The panel contains 72 solar cells connected in series, each with an area of 173 cm2 as shown below. Input data provided for this project is a collection of data at solar radiation intensities up to the peak incident levels of solar radiation usually possible on the surface of the collector panel (maximum of about 1300 W/m2). This type of panel is now proposed for use in a system that will have an array of tracking mirrors to reflect additional solar radiation onto the panels. In this system, the panels will receive incident radiation that is as much as 50% more than the direct incident radiation maximum of 1300 W/m2. Some limited performance data for flux levels above 1300 W/m2 are available for testing. The overall goal is to develop a machine-learning-based model of the performance of the panel based mainly on data at flux levels below 1300 W/m2, and validate it against data at higher flux levels. The intent is to then use the model to predict performance of the solar PV panel at higher flux levels that should shift the V-I performance curve to higher current and/or voltage levels. 
<img width="460" alt="Solar_PV" src="https://user-images.githubusercontent.com/124940176/227656685-b79e255b-8a8d-49f6-b33e-f7819b32120f.png">

## Dual_Electronic_Components_Cooling

- `PV_panel_electrical_power_system.ipynb`: Part 2 of the project considers a solar PV system comprised of 4 solar panels of the type described in Part 1. They will be installed in a close-spaced rectangular array, but will be wired with switches so it is possible to connected the four in parallel (mode 0), 2x2 in series/parallel (mode 1), or with the four in series (mode 2). As shown in figure below, these changes combine the V-I characteristics of the individual modules to produce three very different overall system V-I characteristics. This notebook therefore contains the implementation of the NN for optimal mode (configuration) prediction for maximum power output generation.
-  <img width="432" alt="4-panel system" src="https://user-images.githubusercontent.com/124940176/227655937-eb566405-e7d1-4df6-bc49-abf6871f6ec1.png">



