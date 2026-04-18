## CVRP Hybrid Solver: Clarke-Wright + Tabu Search
This repository contains a high-performance Python implementation for solving the Capacitated Vehicle Routing Problem (CVRP). It combines the classical Clarke-Wright Savings algorithm for initial route construction with a Tabu Search metaheuristic for iterative refinement.
### Key Features
- Dual-Phase Optimization: Rapid construction followed by metaheuristic refinement.
- Neighborhood Operators:
    - 2-Opt: Optimizes individual routes by reversing segments.
    - Relocation: Balances load and reduces distance by moving nodes between routes.
- Efficiency Focus: Relocation deltas are calculated mathematically in $O(1)$ to avoid expensive array copies during neighborhood exploration.
- Vehicle Penalty: Integrated logic to prioritize reducing the total number of vehicles used.
### Performance Benchmark
The solver was tested on standard VRP benchmark instances (e.g., E-n51-k5, c101).
- Average Improvement: 15% – 43% reduction in distance compared to the initial Clarke-Wright solution.
- Execution Speed: Processes instances with up to 100+ nodes in seconds.

### Experimental Results
Instance,Nodes,Routes,CW Distance,TS Distance,Improvement %,Time (s)
C1_2_1.TXT,200,24,"6,078.75","3,458.73",43.10%,1.4s
E-n51-k5.txt,50,7,901.62,595.20,33.99%,0.3s
C1_4_1.TXT,400,64,"15,729.92","11,967.88",23.92%,1.7s
c101.txt,100,11,"1,181.14",979.47,17.07%,0.9s
C1_10_1.TXT,1000,173,"85,144.91","79,646.51",6.46%,2.5s
