#DTA400_Project

JIT Store Simulation
This project simulates a Just-In-Time (JIT) store using an M/M/1 queue model. It models a system where customer orders arrive randomly, and a single machine processes them on demand. The simulation tracks key performance metrics like average wait time, queue length, server utilization, and throughput.

Features
Simulates customer order arrivals using a Poisson process.
Processes orders with a single machine using exponentially distributed service times.
Dynamically adjusts arrival rates to analyze system performance under varying load conditions.
Tracks and computes performance metrics including:
Average wait time
Average queue length
Server utilization
Throughput rate
Visualizes the results with graphs for better understanding of system behavior.
Requirements
The simulation is written in Python and uses the following libraries:

numpy: For statistical distributions like Poisson and Exponential.
simpy: For simulating discrete event systems.
matplotlib: For plotting performance metrics.

Install dependencies using pip:
pip install simpy numpy matplotlib

How It Works
Simulation Environment:
Orders arrive at random intervals following a Poisson distribution.
A single machine processes each order, with service times following an exponential distribution.

Key Components:
JITstore: Represents the store with a single machine for processing orders.
Statistics: Tracks metrics such as arrival times, wait times, queue lengths, utilization, and throughput.

Simulation Process:
setup: Initializes the simulation and generates orders at regular intervals.
order: Simulates the lifecycle of a single order, from arrival to completion.
run_simulation: Runs the simulation and calculates key metrics for each run.

Dynamic Load Testing:
Each run decreases the average arrival interval, increasing the load on the system.
The simulation stops when server utilization exceeds 100%, indicating system overload.

Usage
To run the simulation:
python <script_name>.py

Key Parameters
You can adjust these parameters in the script to customize the simulation:
RANDOM_SEED: Ensures reproducibility of random events.
NUM_MACHINES: Number of machines available for processing orders (default: 1).
PRODUCTION_TIME: Average time to produce one order (default: 2 minutes).
ARRIVAL_TIME: Initial average arrival interval between orders (default: 10 minutes).
SIM_TIME: Total simulation time (default: 100,000 minutes).

Outputs
Console
For each run, the simulation prints:
Service rate (orders/minute)
Arrival rate (customers/minute)
Average wait time (minutes)
Average queue length (customers)
Server utilization (%)
Throughput rate (orders/minute)
The simulation will stop if server utilization exceeds 100%, indicating system overload.

Graphs
After the simulation ends, the following performance metrics are plotted:
Average Wait Time per Run
Average Queue Length per Run
Utilization per Run
Throughput Rate per Run

Example Run
Sample output from the simulation:
Run: 1
Service Rate (𝜆): 0.50 orders/minute
Arrival Rate (𝜇): 0.10 customers/minute
Average Wait Time (W): 0.20 minutes
Average Queue Length (L): 0.02 customers
Utilization (𝜌): 20.00%
Throughput Rate: 0.10 orders/minute
...
SYSTEM OVERLOAD!!! Arrival rate is higher than service rate

Visualization
At the end of the simulation, graphs provide insights into how the system performed under varying loads, highlighting when it approaches or exceeds capacity.

Customization and Experimentation
You can modify the simulation parameters to explore different scenarios:
Increase the number of machines (NUM_MACHINES) to compare single and multi-server systems.
Adjust ARRIVAL_TIME to model environments with higher or lower traffic.
Change PRODUCTION_TIME to simulate slower or faster production rates.
License
This project is released under the MIT License. Feel free to use, modify, and distribute it.

Author
This simulation is designed for educational purposes to demonstrate queueing theory concepts and system performance analysis using SimPy.
