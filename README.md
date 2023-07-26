# A Model-Based Simulation Tool for Smart Homes

Link to download the project tools:
https://drive.google.com/file/d/1hMDeY8y_AGmyXg7wsQuyrdM_zOkDw0VK/view?usp=sharing

Inside the Google Drive folder, you will find three tools:
- *Simulator_v1.0*, the main tool to start a simulation run in the context of a smart home;
- *HomeDesigner_v1.0*, the tool to design the smart environment filled with sensors used within the simulation;
- *HumanDesigner_v1.0*, the tool to create human profiles that characterize the inhabitant(s) within the simulation.

After downloading them, to run each tool, double-click on the corresponding executable (*.exe* files).

# Simulation Models

The repository does not only include the executables needed to run the tools but also a set of models, including human models, house models, acting models, and behavior patterns (look at the paper for more details). The goal of this repository is to provide a shared workspace that the community can contribute to. The creation of models is indeed an expensive task, so the availability of such a repository can speed up the definition of common scenarios to be used to produce workbenches.

The following repository contains the following folders:
- *Acting_models*, containing models describing main-events/activities that follow the original language of the simulator;
- *System_Model*, containing models describing main-events/activities that follow the task-model language.
- *House_models*, containing models defining walls and sensors for the smart space in which the inhabitant(s) interact(s). New models can be defined by using the *HomeDesigner_v1.0* tool.
- *Human_models*, containing models defining human profiles for the inhabitant(s) within the simulation. New models can be defined by using the *HumanDesigner_v1.0* tool.
- *SensorTAB*, containing txt files representing values over the simulation time of custom sensors previously defined by using the *HomeDesigner_v1.0* tool.

Models from these folders can be integrated into the simulation by adding them to the corresponding folders inside the *Data* folder already present within the downloadable tools.

# Tool Description

Notice that the term *user* is used throughout the entire paper to denote the researcher who uses the tool, whereas the term *inhabitant* is used to denote the virtual avatar simulating a person's behavior.

Once the user starts the *Simulator_v1.0* tool, the following interface is shown:

![alt text](https://github.com/silvestroveneruso/smart_space_model_based_simulation/blob/main/figures/sim_screenshot_01.png)

On the left side, organized in two columns, are all the available settings to customize a simulation run. From the left column, starting from the top, we have:
* **Simulation length**. It determines how many *days* the simulation will last. Therefore, how many days the resulting dataset will cover.
* **Simulation stepsize**. It establishes how often the variables of the system (i.e., environmental and human needs parameters) will be checked and updated. It is expressed in *seconds*. For example, by setting a simulation stepsize of one second, the simulator will check every second the thirstiness parameter of the simulator's inhabitant(s) to eventually start the *drink* activity.
* **Simulation name**. The identifier of the current simulation run.
* A drop-down menu to select the **starting day** of the simulation. For example, if we are interested in a "weekend log", we can select Saturday from this menu.
* A drop-down menu to select the **type of control** of the simulation. *Native control* if we are interested in a simulation regarding only activities from the original simulator language (as described in the paper). *Mixed control* if we want to introduce the activities modeled by using the task-model language.

From the right column, starting from the top, we have:
* **Human type**. It allows you to select the *human model* for the inhabitant(s) of the simulation. The *human model* consists of a set of constants defining the parameters of a person, such as his/her speed or his/her frequency at feeling different needs (e.g., need for sleeping or eating).
* **Number of humans**. It determines how many inhabitants are involved in the simulation run.
* **House model**. It allows to select the smart environment among the ones created within the *HomeDesigner_v1.0* tool.
* **Reduce Noise**. A drop-down menu to select the level of *noise* produced by the simulator within the output logs. This feature has been added due to the fact that the original simulator inserted a large amount of noise by default. Now, noise can be reduced or completely removed from output logs.

Once the preferred configuration is selected, depending on design choices, the simulation can start by pressing the **Simulate** button.
After some time, depending on the chosen settings, the tool ends the simulation run and produces an alert indicating the folder location for the output logs. Additionally, the list of main events produced within the simulation (i.e., the activities performed by the inhabitant(s)) is shown in the upper-right section.

As we can see in the following screenshot:

![alt text](https://github.com/silvestroveneruso/smart_space_model_based_simulation/blob/main/figures/sim_screenshot_02.PNG)

the tool produces also some graphs on the bottom part of the interface. These graphs represent the evolution of some environmental variables over the simulation time (e.g., power usage and temperature). Buttons **Zoom+**, **Zoom-** and **Zoom reset** on the top-right corner of the tool interface, allow to manipulate the zoom level on these graphs. On the same section, there is also an **Above** button that shows general information about the tool.
