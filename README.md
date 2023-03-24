# ML-projects
Machine learning projects
This repository contains 3 machine learning projects.

## Design and control of a solar PV power generation system:

This project focuses on the design and control of a solar PV power generation system. The following files are included:
- `Performance_Solar_PV.ipynb`: Part 1 of this project considers the performance of the solar panel design show above. The panel contains 72 solar cells connected in series, each with an area of 173 cm2 as shown below. Performance test data forthis type of unit is provided as a dataset that includes the following performance parameters: 
- Specified operating parameters: Outside air temperature, Tair (°C), Incident direct normal solar radiation intensity, ID (W/m^2), Load resistance, RL(Ohms). 
- Performance (output) parameters: Panel output voltage to load VL (V) and Panel power output W (W)
- Input data provided for this project is a collection of data at solar radiation intensities up to the peak incident levels of solar radiation usually possible on the surface of the collector panel (maximum of about 1300 W/m2). This type of panel is now proposed for use in a system that will have an array of tracking mirrors to reflect additional solar radiation onto the panels. In this system, the panels will receive incident radiation that is as much as 50% more than the direct incident radiation maximum of 1300 W/m2. Some limited performance data for flux levels above 1300 W/m2 are available for testing. The overall goal is to develop a machine-learning-based model of the performance of the panel based mainly on data at flux levels below 1300 W/m2, and validate it against data at higher flux levels. The intent is to then use the model to predict performance of the solar PV panel at higher flux levels that should shift the V-I performance curve to higher current and/or voltage levels. 
<img width="460" alt="Solar_PV" src="https://user-images.githubusercontent.com/124940176/227656685-b79e255b-8a8d-49f6-b33e-f7819b32120f.png">

- `PV_panel_electrical_power_system.ipynb`: Part 2 of the project considers a solar PV system comprised of 4 solar panels of the type described in Part 1. They will be installed in a close-spaced rectangular array, but will be wired with switches so it is possible to connected the four in parallel (mode 0), 2x2 in series/parallel (mode 1), or with the four in series (mode 2). As shown in figure below, these changes combine the V-I characteristics of the individual modules to produce three very different overall system V-I characteristics. This notebook therefore contains the implementation of the NN for optimal mode (configuration) prediction for maximum power output generation.
<img width="432" alt="4-panel system" src="https://user-images.githubusercontent.com/124940176/227655937-eb566405-e7d1-4df6-bc49-abf6871f6ec1.png">

## Dual Electronic Components Cooling: 
This project considers natural convection cooling of two discrete heated electronic components mounted on a vertical circuit board, as depicted in Fig below. <img width="275" alt="Circuit_board" src="https://user-images.githubusercontent.com/124940176/227658877-69108793-9f2d-4adb-b064-c10c622ea7de.png">

Previous model generated by a CFD simulation was used to predict the system heat transfer performance for a spectrum of values of the three parameters: Incident flux q1 and q2, and separation distance Δx, both q1 and q2 in the ranges of [50, 600] W/m2 ,and 0 < Δxs < 0.010 m. The maximum surface temperature Ts,max is of primary interest, because keeping the component temperatures within acceptable limits is essential for the reliable performance of the system. For example, it is generally acknowledged that the majority of today's desktop processors should not exceed temperatures of 45-50°C when idle, or 80°C when under full load.
The overall goal is to take performance data generated by a CFD-type model and train a neural network to predict the maximum (component) surface temperature when our input data q1, q2 and separation distance Δx are provided. The neural network model can then be used to explore the parametric trends in performance. The model can also be a design tool that can determine the effect of component spacing on maximum operating temperature at different power consumption levels.

## Hybrid solar/fossil-fuel gas turbine power system
This project focuses on the implementation of a hybrid solar/fossil-fuel gas turbine power system. The following files are included:
Part 1 of this project deals with comparison of a first-principles neural network implementation and the corresponding calculation using the keras Python software.

<img width="465" alt="Simple_NN" src="https://user-images.githubusercontent.com/124940176/227660211-dc6d4153-4b9c-451e-95f1-930d986c450a.png">

- `First_Principles_implementation.ipynb`: This notebook contains the implementation of a first-principles model of the system (neural network designed from scartch).
- `Keras_First_Principles_comparison.ipynb`: This notebook compares the results of the neural network and first-principles models.
Part 2 of this project deals with analysis of the hybrid solar fossil-fuel gas turbine system in the figures below.
<img width="370" alt="Screenshot 2023-03-24 at 4 31 38 PM" src="https://user-images.githubusercontent.com/124940176/227661388-04f810f8-836c-4387-b757-07cd4130948c.png">
For this system, air at 101 kPa and temperature enters the compressor at 6.0 kg/s. The compressed air is heated in the regenerator and solar thermal exchanger, then burned with fuel in a burner to reach the target temperature of 1473 K. The fuel mixture varies and must be adjusted to maintain the temperature. A physical model may not be accurate due to idealizations, while constructing a machine learning model based on test data is more accurate. Part 2 of the project therefore aims to create a neural network model for the gas turbine system.
- `Keras_NN_Prediction.ipynb`: This notebook uses a neural network to predict the performance of the system.








