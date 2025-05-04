# Woody Block Search Algorithm

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Python Version](https://img.shields.io/badge/python-3.8%2B-green.svg)](#requirements)

## 🎲 Overview

Woody Block Search Algorithm is a modular Python framework designed to implement, benchmark, and compare classical uninformed and informed search strategies within the "Woody Block" puzzle environment. This project aims to:

* Showcase core AI search techniques in a unified setting
* Measure each algorithm’s performance: nodes expanded, solution depth, path cost, and runtime
* Provide an extensible platform for experimenting with new heuristics or search variants

## ⚙️ Key Features

* **Uninformed (Blind) Search**

  * Breadth‑First Search (BFS)
  * Depth‑First Search (DFS)
  * Iterative Deepening Search (IDS)
  * Uniform Cost Search (UCS)

* **Informed (Heuristic) Search**

  * Greedy Best‑First Search
  * A\* Search
  * Weighted A\* Search (W-A\*)

* Extensible simulation environment for custom block arrangements and goal states

* Performance logging with automatic metrics export

* Command-line interface for single experiments or batch comparisons

## 🏷️ Repository Structure

```
Woodblock_Algorithm/
├── assets/                 # Sample puzzles and visualization scripts
├── algorithms.py           # Base classes and shared utilities
├── blind_search.py         # Implementations of uninformed search methods
├── informed_search.py      # Implementations of heuristic-based search
├── simulation.py           # Environment setup, state definitions, and helpers
├── main.py                 # CLI entrypoint for running experiments
├── requirements.txt        # Python dependencies
├── LICENSE                 # Project license (MIT)
└── README.md               # Project documentation
```

## 🚀 Installation

1. **Clone the repository**:

   ```bash
   git clone https://github.com/alfredofdlv/Woodblock_Algorithm.git
   cd Woodblock_Algorithm
   ```
2. **(Optional) Create a virtual environment**:

   ```bash
   python3 -m venv venv
   source venv/bin/activate      # macOS / Linux
   venv\Scripts\activate       # Windows
   ```
3. **Install dependencies**:

   ```bash
   pip install -r requirements.txt
   ```

## 🚀 Usage

Run a single search algorithm against a predefined puzzle:

```bash
python main.py --algorithm astar --puzzle assets/puzzle1.json
```

Compare all implemented algorithms over multiple puzzles and export results:

```bash
python main.py --batch assets/*.json --output results.csv
```

Use `--help` to explore additional options.

## 🔍 Algorithm Details

All search classes inherit from the `SearchAlgorithm` interface in `algorithms.py`. Key methods:

* `initialize(start_state)`: Prepare internal data structures
* `step()`: Expand one node, return status (`ongoing`, `success`, `failure`)
* `get_solution()`: Retrieve the solution path and metrics after completion

### Uninformed Searches

* **BFS**: Guarantees shallowest solution but uses more memory.
* **DFS**: Explores deep paths first; can be combined with depth limits.
* **IDS**: Repeated DFS with increasing depth limit; memory-efficient.
* **UCS**: Prioritizes lowest cumulative path cost; optimal for weighted moves.

### Heuristic Searches

* **Greedy Best‑First**: Selects nodes with smallest heuristic estimate to goal; fast but not optimal.
* **A**\*: Balances actual cost (`g`) and heuristic (`h`) via `f(n) = g(n) + h(n)`; optimal if heuristic is admissible.
* **Weighted A**\*: Applies weight `w` to heuristic term (`f(n)=g(n)+w*h(n)`), trading optimality for speed.

## 📊 Metrics & Output

By default, each experiment logs:

* Total nodes expanded
* Maximum frontier size
* Solution depth
* Path cost
* Execution time (seconds)

Exported results (CSV) can be visualized using any data analysis tool.

## In-Game Examples

*Add your own in-game images below:*

```markdown
![In-Game Screenshot](assets/screenshot.png)
```

## 📄 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

*Designed as an educational tool for exploring search algorithms in puzzle-solving contexts.*
