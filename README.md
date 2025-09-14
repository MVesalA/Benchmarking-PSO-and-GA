# Computational Intelligence: Benchmarking PSO and GA

## Overview

This repository focuses on benchmarking Particle Swarm Optimization (PSO) and Genetic Algorithms (GA) on various unimodal and multimodal benchmark functions. The project aims to compare the performance of these two popular metaheuristic algorithms in solving optimization problems across different complexities and dimensions.

## Project Structure

* `Benchmark_PSO_GA.ipynb`: The main Jupyter Notebook containing the implementation of PSO and GA, the benchmark functions, and the experimental results.
* `benchmarkfcns.py`: A Python script containing the definitions of the benchmark functions used in the experiments.

## Algorithms Implemented

### Genetic Algorithm (GA)

The Genetic Algorithm implemented in this project includes:

* **Initialization**: Random generation of initial population.
* **Selection**: Tournament selection.
* **Crossover**: Blend crossover (BLX-alpha) for real-valued genes.
* **Mutation**: Gaussian perturbation.
* **Elitism**: Preservation of the best chromosome from one generation to the next.

### Particle Swarm Optimization (PSO)

The Particle Swarm Optimization algorithm implemented in this project includes:

* **Initialization**: Random placement of particles within the search space.
* **Velocity Update**: Based on personal best (pbest) and global best (gbest) positions.
* **Position Update**: Particles move according to their updated velocities.
* **Inertia Weight (w)**, **Cognitive Coefficient (c1)**, and **Social Coefficient (c2)** are configurable parameters.

## Benchmark Functions

The project utilizes a comprehensive set of benchmark functions, categorized by their dimensionality and modality:

### Unimodal Functions

* **2D**: AckleyN2, BohachevskyN1, Booth, Brent, dropwave, Exponential, Leon, Matyas, SchafferN1, SchafferN2, SchafferN3, SchafferN4, ThreeHumpCamel
* **nD (30D)**: Brown, Griewank, PowellSum, Ridge, Schwefel2\_20, Schwefel2\_21, Schwefel2\_22, Schwefel2\_23, Sphere, SumSquares, Trid, XinSheYangN3, Zakharov

### Multimodal Functions

* **1D**: Forrester, Gramacy & Lee
* **2D**: Adjiman, Bartels Conn, Beale, Bird, Bohachevsky N. 2, Bukin N. 6, Carrom Table, Cross-in-Tray, Deckkers-Aarts, Easom, Egg Crate, El-Attar-Vidyasagar-Dutta, Goldstein-Price, Himmelblau, Holder-Table, Keane, Levi N. 13, McCormick, Shubert 3, Shubert N. 4, Shubert
* **3D**: Wolfe
* **nD (30D)**: Alpine N. 1, Alpine N. 2, Happy Cat, Periodic, Qing, Quartic, Rastrigin, Rosenbrock, Salomon, Schwefel, Styblinski-Tank, Xin-She Yang, Xin-She Yang N. 2, Xin-She Yang N. 4, Ackley, Ackley N. 4

## Experimental Setup

For both GA and PSO, the following parameters were generally used:

* `pop_size`: 50 (population/swarm size)
* `max_generation`: 40000 (maximum number of generations/iterations)
* `patience`: 1000 (number of generations without improvement before early stopping for GA), 3000 (for PSO)

Specific parameters for GA:

* `crossover_rate`: 0.75
* `mutation_rate`: 0.01

Specific parameters for PSO:

* `w`: 0.74 (inertia weight)
* `c1`: 1.42 (cognitive coefficient)
* `c2`: 1.42 (social coefficient)

## Results and Analysis

The Jupyter Notebook `Benchmark_PSO_GA.ipynb` contains detailed results, including:

* Best solution found for each benchmark function.
* Best fitness achieved for each benchmark function.
* Fitness history plots showing convergence over generations.
* Statistical summaries (mean, standard deviation, median) of fitness values over multiple runs.

**Key Findings (Preliminary - based on notebook output):**

* **GA Performance**: The GA shows good performance on many functions, often converging to near-optimal solutions. Early stopping is frequently observed, indicating convergence before the maximum generation limit.
* **PSO Performance**: PSO demonstrates very strong convergence capabilities, especially on unimodal functions, often reaching the global optimum with very high precision (fitness values close to 0 or -200 for AckleyN2). It also performs well on multimodal functions.
* **Comparison**: While both algorithms are effective, PSO appears to converge more consistently and precisely on certain functions, particularly those with well-defined global optima. GA, with its exploration mechanisms, might be more robust in escaping local optima for some complex multimodal functions, though the current results show PSO often finding better solutions.

Further detailed analysis and comparative plots are available within the notebook.

## How to Run the Project

1. **Clone the repository:**

   ```bash
   git clone https://github.com/your-username/your-repo-name.git
   cd your-repo-name
   ```
2. **Install dependencies:**

   ```bash
   pip install numpy matplotlib pandas jupyter
   ```
3. **Run the Jupyter Notebook:**

   ```bash
   jupyter notebook Benchmark_PSO_GA.ipynb
   ```

   This will open the notebook in your web browser, where you can run all cells to reproduce the results.

## Contributing

We welcome contributions to this project! Please feel free to open issues or submit pull requests.

## License

This project is licensed under the MIT License - see the LICENSE.md file for details.

---

