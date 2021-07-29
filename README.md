# A Model-Based Simulation Tool for Smart Homes

Link to download the project tools:
https://drive.google.com/file/d/1hMDeY8y_AGmyXg7wsQuyrdM_zOkDw0VK/view?usp=sharing

Inside the google drive folder you will find three tools:
- *Simulator_v1.0*, the main tool to start a simulation run in the context of a smart home;
- *HomeDesigner_v1.0*, the tool to design the smart environment filled with sensors used within the simulation;
- *HumanDesigner_v1.0*, the tool to create human profiles which characterize the inhabitant(s) within the simulation.

After downloading them, to run each tool, double-click on the corresponding executable (*.exe* files).

The repository does not only include the executables needed to run the tool, but also a set of models including human models, house models, acting models and behaviour patterns. The goal of this repository is to provide a shared workspace the community can contribute to. The creation of models is indeed an expensive task, thus the availability of such a repository can speed up the definition of common scenarios to be used to produce workbenches.

# Simulation Models

The following repository contains models for the *Simulator_v1.0* tool. In particular:
- *Acting_models*, containing models describing main-events/activities which follow the original language of the simulator;
- *System_Model*, containing models describing main-events/activities which follow the task-model language.

Models from these folders can be integrated within the simulation by adding them to the corresponding folders inside the *Data* folder already present within the *Simulator_v1.0* tool.

# Tool Description

Once the user starts the tool, the following interface is shown:

![alt text](https://github.com/silvestroveneruso/smart_space_model_based_simulation/blob/main/figures/sim_screenshot_01.png)

Notice that the term \emph{user} is used throughout the entire paper to denote the researcher who uses the tool, whereas the term \emph{inhabitant} is used to denote the virtual avatar simulating a person's behaviour.

On the left side, organized in two columns, there are all the available settings to customize a simulation run. From the left column, starting from the top, we have:
\begin{itemize}
    \item \texttt{Simulation length}. It determines how many \textit{days} the simulation will last. Therefore, how many days the resulting dataset will cover.
    \item \texttt{Simulation stepsize}. It establishes how often the variables of the system (i.e., environmental and human needs parameters) will be checked and updated. It is expressed in \textit{seconds}. For example, by setting a simulation stepsize of one second, the simulator will check every second the thirstness parameter of the simulator's inhabitant(s), to eventually starts the \emph{drink} activity.
    \item \texttt{Simulation name}. The identifier of the current simulation run.
    \item A drop-down menu to select the \texttt{starting day} of the simulation. For example, if we are interested in a ``weekend log" we can select Saturday from this menu.
    \item A drop-down menu to select the \texttt{type of control} of the simulation. \textit{Native control} if we are interested in a simulation regarding only activities from the original simulator language (i.e., events described as \ref{fig:mainevent} and \ref{fig:bottomevent}). \textit{Mixed control} if we want to introduce also the activities modeled by using the task-model language.
\end{itemize}
From the right column, starting from the top, we have:
\begin{itemize}
    \item \texttt{Human type}. It allows to select the \textit{human model} for the inhabitant(s) of the simulation. The \emph{human model} consists of a set of constants defining the parameters of a person such as his/her speed, or his/her frequency at feeling different needs (e.g., need for sleeping or eating).
    \item \texttt{Number of humans}. It determines how many inhabitants are involved within the simulation run.
    \item \texttt{House model}. It allows to select the smart environment among the ones created within the \textit{Home Designer tool} (see Figure \ref{fig:add_customsensor}).
    \item \texttt{Reduce Noise}. A drop-down menu to select the level of \textit{noise} produced by the simulator within the output logs. This feature has been added due to the fact that the original simulator inserted a large amount of noise by default. Now, noise can be reduced or completely removed from output logs.
\end{itemize}
Once selected the preferred configuration, depending on design choices, the simulation can start by pressing the \texttt{Simulate} button.
After some time, depending on the chosen settings, the tool ends the simulation run and produces in output an alert indicating the folder location for the output logs. Additionally, the list of main events produced within the simulation (i.e., the activities performed by the inhabitant(s)) is shown in the upper-right section.

As we can see in Figure \ref{fig:sim_screen_end}, the tool produces also some graphs on the bottom part of the interface. These graphs represent the evolution of some environmental variables over the simulation time (e.g., power usage and temperature). Buttons \texttt{Zoom+}, \texttt{Zoom-} and \texttt{Zoom reset} on the top-right corner of the tool interface, allow to manipulate the zoom level on these graphs. On the same section, there is also an \texttt{Above} button that shows general information about the tool.
