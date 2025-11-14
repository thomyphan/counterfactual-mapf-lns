# Truncated Counterfactual Learning for Anytime Multi-Agent Path Finding

This software is based on the latest MAPF-LNS implementation from [1] and [2]. 

## Usage
The code requires the external libraries `BOOST 1.81.0` and `Eigen 3.3`, and `CMake` for building the code. 
    
After installing both libraries go to the root folder of this repository and run the following commands: 
```shell script
cmake -DCMAKE_BUILD_TYPE=RELEASE .
make
```

Run the code with:
```
./tackle -m Paris_1_256.map -a Paris_1_256-random-1.scen -o test --agentNum=1000 -t 60 --stats "stats.txt" --outputPaths=paths.txt --seed=0 --maxIterations=1000000 --destroyStrategy=RandomWalk --algorithm=tackle-roulette --k=32 
```

- m: the map file from the MAPF benchmark
- a: the scenario file from the MAPF benchmark
- o: the output file name (no need for file extension)
- agentNum: the number of agents
- t: the runtime limit
- outputPaths: the output file that contains the paths
- algorithm: the delay-based algorithm to run (tackle-tabu, tackle-roulette, tackle-random)
- k: the top-K most delayed agents which TACKLE chooses from

You can find more details and explanations for all parameters with:
```
./tackle --help
```

The benchmarking test suite for MAPF problems can be downloaded from the MovingAI MAPF benchmark.

## References

- [1] J. Li et al. *"Anytime Multi-Agent Path Finding via Large Neighborhood Search"*. IJCAI 2021.
- [2] T. Phan et al. *"Anytime Multi-Agent Path Finding with an Adaptive Delay-Based Heuristic"*. AAAI 2025.
