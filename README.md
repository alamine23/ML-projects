# ML-projects
Machine learning projects
This repository contains 3 machine learning projects.

## Hybrid solar/fossil-fuel gas turbine power system
This project focuses on the implementation of a hybrid solar/fossil-fuel gas turbine power system. The following files are included:
Part 1 of this project deals with comparison of a first-principles neural network implementation and the corresponding calculation using the keras Python software.

<img width="465" alt="Simple_NN" src="https://user-images.githubusercontent.com/124940176/227660211-dc6d4153-4b9c-451e-95f1-930d986c450a.png">

- `First_Principles_implementation.ipynb`: This notebook contains the implementation of a first-principles model of the system (neural network designed from scartch).
- `Keras_First_Principles_comparison.ipynb`: This notebook compares the results of the neural network and first-principles models.
Part 2 of this project deals with analysis of the hybrid solar fossil-fuel gas turbine system in the figures below.
<img width="370" alt="Screenshot 2023-03-24 at 4 31 38 PM" src="https://user-images.githubusercontent.com/124940176/227661388-04f810f8-836c-4387-b757-07cd4130948c.png">
In this system, air at atmospheric pressure = 101 kPa and at a temperature enters thecompressor inlet at a flow rate typically about 6.0 kg/s. The air flowing out of the compressor at the high-side pressure first is heated to temperature in the regenerator, transferring waste heat from the turbine exhaust stream. The gas is then heated further in an exchanger that delivers solar thermal heat input, raising the temperature to . Finally, the air flows into a
burner where fuel is injected and burned to raise the temperature to . Having as high as possible is thermodynamically advantageous, resulting in higher system efficiency for higher $T_4$. However, if is too high, the components of the turbine may be damaged, and for that reason, an optimal temperature is usually specified which is the highest value that can be tolerated by the blade materials in the turbine. Recent development efforts have resulting in
turbine designs, with special blade materials, that can operate at 1600 K. Here the system is specified to operate at 1473 K (1200 °C), with a pressure ratio $P_2$/$P_1$ of 14. 
The burner in the system is designed to burn pure methane or a mixture of methane (CH4) with some added propane (C3H8). The mixture ratio may be dictated by cost factors and availability, resulting in the mole fraction of the fuels ranging from 0% propane and all methane, to 50% propane and 50% methane, by mole. Key parameters here are the molar air-to-fuel ratio $alpha$ and the fuel propane mole fraction $gamma$ defined as:
$alpha$=(moles of air)/(total moles of propane and methane in mixture) in inlet flow to burner.
$gamma$=(moles of propane)/(moles of propane and methane in fuel mixture).
Air inlet temperature, solar heat input , and the fuel mixture fraction vary during system operation, and consequently, the rate of fuel injection in the burner must be varied to hold the turbine inlet temperature at the target level of 1473 K. To facilitate model-based control of , a model that predicts the required air-to fuel ratio to achieve this turbine inlet temperature under varying conditions can be used by a controller to set the fuel flow rate at the proper values. Two ways of constructing a model are:
1. Construct a physical model based on thermodynamics, fluid dynamics and heat transfer.
2. Run performance tests for the system over the expected range of operating conditions and
construct a mathematical/computational fit to the experimental data using machine learning
methods.
Option 1, construction of a physical model, has advantages and drawbacks. Use of a theoretical model can avoid the need for building a prototype system and obtaining test data. However, physical models generally incorporate idealizations that may not be completely accurate, and they may require knowledge of system parameters that may not be known with complete accuracy. For example, the regenerative heat exchanger may be modeled with the assumption that its heat transfer conductance is uniform throughout the unit, which may not be accurate. Also, the value of the conductance may not be known precisely. Other parameters such as the compressor isentropic efficiency and the turbine isentropic efficiency also may vary with conditions, and not be known to high accuracy. Creating an accurate model this way may be challenging.
Option 2 requires obtaining test data. However, creating a machine learning model to fit the multivariate data accounts for all the real system parametric effects and requires no assumptions or idealizations. If a good fit to the data is obtained, the predictions of the resulting model can be accurate to the level of the uncertainty in the data and the mean absolute error or RMS error of the fit. In addition, data obtained during field operation of the systems can be used to update the model accounting for variation in its performance during its operational lifetime.
The objective of Part 2 of this project is to construct a neural network model of the performance of the gas turbine system shown in Figures above.
- `Keras_NN_Prediction.ipynb`: This notebook uses a neural network to predict the performance of the system.


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





