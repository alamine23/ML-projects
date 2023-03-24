# ML-projects
Machine learning projects
This repository contains 3 machine learning projects.

## Hybrid solar/fossil-fuel gas turbine power system
This project focuses on the implementation of a hybrid solar/fossil-fuel gas turbine power system. The following files are included:
Part 1 of this project deals with comparison of a first-principles neural network implementation and the corresponding calculation using the keras Python software.
<img width="465" alt="Simple_NN" src="https://user-images.githubusercontent.com/124940176/227660211-dc6d4153-4b9c-451e-95f1-930d986c450a.png">
Backpropagation:
Squared error: $E_3=(a_3-y_3)^2$
We want to correct all the weights and bias values to make the squared error close to zero. When we achieve that for a large number of data sets, we have trained the neural network to model the system. 
Consider one of the weights, w_01. If we knew the derivative ∂E3/∂w01, we could use a Newton-Raphson finite difference approximation to find a new value for w_01 that would make the error go to zero:

w01,n = w01 + (0 - E3) / (∂E3 / ∂w01)

However, in our neural network, we have eight weights and biases, so we only want to correct about 1/8th of the total error at each iteration. To do this, we modify the above equation to:

w01,n = w01 + γ(0 - E3) / (∂E3 / ∂w01)

Here, γ is a learning rate parameter that is on the order of 1/total number of weights and biases in the neural network. If we apply this logic to all the weights and biases, we obtain the following set of relations:

w01,n = w01 + γ(0 - E3) / (∂E3 / ∂w01)   (1a)
w02,n = w02 + γ(0 - E3) / (∂E3 / ∂w02)   etc...


- `First_Principles_implementation.ipynb`: This notebook contains the implementation of a first-principles model of the system (neural network designed from scartch).

- `Keras_NN_Prediction.ipynb`: This notebook uses a neural network to predict the performance of the system.

- `Keras_First_Principles_comparison.ipynb`: This notebook compares the results of the neural network and first-principles models.

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





