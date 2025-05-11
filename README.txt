README.txt
==========

Benchmark Runner for SAT Solver Comparison
-------------------------------------------

This repository contains the benchmark runner used for the experimental evaluation in the paper:
"A Theoretical and Experimental Comparison of SAT Solving Algorithms: Resolution, DP, DPLL, and CDCL".

The purpose of this runner is to systematically compare the performance of different SAT solving algorithms on a variety of CNF instances, with a focus on both synthetic and real-world datasets.

Contents:
---------

Experiment_benchmark/
├── benchmark_runner.py    # Main script to execute benchmarks
├── cnfs_for_cdcl/			# input folders with cnfs for solvers
├── cnfs_for_dp/			# input folders with cnfs for solvers
├── cnfs_for_dpll/			# input folders with cnfs for solvers
├── cnfs_for_resolution/              
├── solvers/               # SAT solvers
│   ├── dpll.py
│   ├── gsat.py
│   ├── walksat.py
│   └── walksat_probabilistic.py
├── cnf_parser.py      
├── plot_runtime.py        # Creates diagrams via results.csv
└── results.csv      		# Output folder for logs and result files

Dependencies:
-------------
You need Python 3.7+ and the following Python libraries:
- pandas
- matplotlib
- pysat

Install them using pip:
> pip install pandas matplotlib python-sat

Usage:
------
1. Open a terminal and navigate to the directory where this project is saved.
2. Run the benchmark with the following command structure:

> python benchmark_runner.py --solver <solver_name> --input <input_folder> --timeout <seconds> --output <output_file>

Example:
> python benchmark_runner.py --solver dpll --input cnfs_for_dpll --timeout 60 --output result.csv

The script will:
- Run the specified solver on all CNF files in the given input folder.
- Record runtime, satisfiability result, and solver-specific stats.
- Save the results to the given output file (CSV format).

Benchmark Structure:
--------------------
- Benchmarks include small handcrafted CNFs, randomly generated 3-SAT instances, and select industrial SAT problems.
- All files are in standard DIMACS format (.cnf).

Author:
-------
[Bacalete Benjamin]  
[UVT Computer Science, Year 1]

