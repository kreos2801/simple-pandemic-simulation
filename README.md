# simple-pandemic-simulation
A code in C that can simulate a pandemic with different settings

To install the library that allows you to visualize graphs, run sudo apt-get install gnuplot.

Fill in the configuration file as follows: The configuration file is used to define the initial parameters of the simulation. It is divided into two main sections: the list of nodes and the list of arcs. Here is how to fill in each section and what each parameter means.

File Header The first line of the file specifies the number of nodes and the number of arcs in the simulation.

NbNodes NbArcs

NbNodes: The total number of nodes in the simulation.

NbArcs: The total number of arcs (connections) between the nodes.

List of Nodes This section defines the properties of each node. Each line represents a node with its respective parameters.

Node List

ID Population Exposed Infected Recovered Dead Vaccination Exposure Infectiousness Beta Gamma Mortality ConfinementRate VaccinationCenter TriggerDay

ID: The unique identifier of the node. It must start from 0 and cannot be a decimal or negative number.

Population: The initial total population of the node. Cannot be a decimal or negative number.

Exposed: The initial number of exposed people in the node. Cannot be a decimal or negative number.

Infected: The initial number of infected people in the node. Cannot be a decimal or negative number.

Recovered: The initial number of recovered people in the node. Cannot be a decimal or negative number.

Dead: The initial number of dead people in the node. Cannot be a decimal or negative number.

Vaccination: The vaccination rate in the node (probability of vaccination). Between 0 and 1.

Exposure: The exposure rate in the node (probability of becoming exposed). Between 0 and 1.

Infectiousness: The probability that an exposed person becomes infected. Between 0 and 1.

Beta: The transmission rate of the infection. Between 0 and 1.

Gamma: The recovery rate of infected people. Between 0 and 1.

Mortality: The mortality rate of infected people. Between 0 and 1.

ConfinementRate: The confinement threshold based on the infection rate. Between 0 and 1.

VaccinationCenter: Indicates if the node is a vaccination center (1 for yes, 0 for no).

TriggerDay: The day the vaccination center starts operating. Cannot be a decimal or negative number.

Example of Node List

0 1000 50 25 0 0 0.01 0.5 0.5 0.01 0.01 0.01 0.01 1 2

1 500 80 20 0 0 0.01 0.5 0.5 0.01 0.01 0.01 0.01 0 800

2 800 100 10 0 0 0.01 0.5 0.5 0.01 0.01 0.01 0.01 0 800

3 1200 150 0 0 0 0.01 0.5 0.5 0.01 0.01 0.01 0.01 0 800

List of Arcs This section defines the connections between the nodes. Each line represents an arc with its respective parameters.

Arc List

SourceID TargetID Ts Ti Tr Te

SourceID: The identifier of the source node. Must be an existing ID.

TargetID: The identifier of the target node. Must be an existing ID.

Ts: The probability of transferring susceptible people. Between 0 and 1.

Ti: The probability of transferring infected people. Between 0 and 1.

Tr: The probability of transferring recovered people. Between 0 and 1.

Te: The probability of transferring exposed people. Between 0 and 1.

Example of Arc List

0 1 0.05 0.02 0.03 0.01

0 2 0.05 0.1 0.01 0.01

2 1 0.03 0.01 0.01 0.01

1 2 0.07 0.04 0.01 0.01

By following this guide, you should be able to correctly fill in the configuration file for the simulation.

Finally, you will need to compile your code and run it with:

./Prog.exe config.txt nbiteration node_to_observe_in_real_time

Example

./prog.exe config.txt 50 1
