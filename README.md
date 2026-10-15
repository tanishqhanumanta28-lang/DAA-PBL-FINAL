# CloudPlace DAA — Cloud Task Placement

**Latency-Aware Replica and VM Placement Using MST Backbone, Shortest Paths, and Dynamic Programming**

## 📌 Project Overview

CloudPlace DAA is a cloud task placement project that uses Design and Analysis of Algorithms (DAA) techniques to optimize replica placement across a network of servers.

The main goal is to minimize demand-weighted network latency while ensuring that server capacity constraints are satisfied.

The project combines graph algorithms, greedy algorithms, dynamic programming, exhaustive search, and local search to compare different placement strategies.

## 🎯 Objectives

- Model cloud servers as nodes in a weighted graph.
- Calculate shortest paths between servers.
- Build a Minimum Spanning Tree (MST) backbone.
- Select optimal or near-optimal locations for service replicas.
- Assign server demand without exceeding capacity.
- Compare different algorithms based on latency and execution time.
- Validate results and benchmark algorithm performance.

## ✨ Key Features

- Server network generation and graph modelling.
- Minimum Spanning Tree construction.
- Shortest-path calculation.
- Multiple replica placement strategies.
- Capacity-aware demand assignment.
- One-swap local search optimization.
- Independent solution validation.
- Reproducible experiments and performance analysis.
- Interactive Replica Placement Lab visualization prototype.

## 🧠 Algorithms Used

| Algorithm | Purpose |
|---|---|
| Dijkstra's Algorithm | Calculates shortest paths between servers. |
| Floyd–Warshall Algorithm | Verifies all-pairs shortest-path results. |
| Kruskal's Algorithm | Constructs the Minimum Spanning Tree. |
| Prim's Algorithm | Constructs an MST using a priority queue. |
| Greedy k-Median | Selects replicas to reduce weighted latency. |
| Dynamic Programming | Optimizes placement over contiguous segments of an MST ordering. |
| Exhaustive Search | Finds the exact solution for small instances. |
| One-Swap Local Search | Improves replica placement by replacing selected replicas. |

## ⚙️ System Workflow

1. Generate or load the server network.
2. Calculate shortest-path latencies.
3. Construct the MST backbone.
4. Select replica servers using the placement algorithms.
5. Assign server demand while respecting replica capacity.
6. Improve the placement using local search, when enabled.
7. Validate the solution.
8. Compare average latency and execution time.

**Important:** The MST is used for low-cost backbone provisioning. Requests are routed using shortest paths in the original network because routing only through the MST can increase latency.

## 🛠️ Technology Stack

- **Programming Language:** Python 3
- **Standard Libraries:** `heapq`, `itertools`, `math`, `random`, `time`
- **Visualization:** Matplotlib
- **PDF Report Generation:** ReportLab
- **Interactive Visualization:** Browser-based Replica Placement Lab prototype

## 📊 Experimental Results

The demonstration network contains 12 servers, 25 links, a total demand of 131 units, and 3 replicas.

| Algorithm | Average Latency | Gap to Exact Optimum |
|---|---:|---:|
| Exhaustive Search | 21.14 ms | 0.0% |
| Greedy + Local Search | 21.14 ms | 0.0% |
| Greedy k-Median | 21.80 ms | 3.1% |
| DP over MST Ordering | 25.46 ms | 20.4% |
| Random Placement | 33.52 ms | 58.6% |

### Key Findings

- Greedy placement combined with local search matched the exact optimum in the demonstration network.
- The optimal replica locations for the demonstration were S1, S4, and S6.
- The MST backbone had a total weight of 305.16 ms, representing 28.7% of the total link weight.
- Routing only through the MST increased average path length by approximately 1.48 times.
- Dijkstra was approximately 13.5 times faster than Floyd–Warshall at 300 servers in the reported benchmark.
- Greedy plus local search reached the exact optimum in 27 out of 30 random test instances, with a mean gap of 0.52%.

*These figures are based on the experiments documented in the project report and are not guaranteed for every network.*

## 🧪 Testing and Validation

The project report documents the following checks:

- Dijkstra's results were compared with Floyd–Warshall.
- Kruskal's and Prim's MST weights were compared.
- Heuristic results were evaluated against exhaustive search on small instances.
- Replica capacities and assignments were independently validated.
- Average latency was recalculated to verify reported objective values.
- Seeded random generation was used to support reproducibility.

## 🚀 Getting Started

### Prerequisites

- Python 3
- Matplotlib for generating charts and figures
- ReportLab for generating the PDF report

### Installation

Clone the repository:

```bash
git clone <YOUR_REPOSITORY_URL>
cd <YOUR_REPOSITORY_FOLDER>
```

If the repository contains a `requirements.txt` file, install its dependencies:

```bash
pip install -r requirements.txt
```

Run the project using the appropriate entry-point script included in the repository.

**Note:** Replace the placeholders and add the exact run command after confirming the repository's actual filenames and scripts.

## 🔮 Limitations and Future Scope

### Current Limitations

- Heuristic methods do not guarantee a globally optimal solution for large instances.
- The DP algorithm is exact only for its restricted MST-ordering model.
- Capacity is represented using a single load dimension.
- Network latency is assumed to be static and symmetric.
- Hosting costs are not included in the current objective.
- Experiments use synthetic networks rather than real-world data-centre measurements.

### Future Enhancements

- Support CPU, memory, storage, and bandwidth constraints.
- Include hosting costs and budget restrictions.
- Automatically determine the number of replicas.
- Support dynamic demand and real-time network latency.
- Explore stronger optimization techniques.
- Add fault-tolerant placement.
- Deploy the engine as a service with a web interface.

## 👥 Team Members

**Group 11 — B.Tech, Computer Science and Engineering**

| S. No. | Student Name | Roll Number |
|---:|---|---|
| 1 | Suhaan Kapoor | 25WU0104027 |
| 2 | Sushil Pal | 25WU0101141 |
| 3 | Tanishq Hanumanta | 25WU0101142 |
| 4 | Arjun Pal | 25WU0801004 |
| 5 | OM PILAJI | 25WU0102202 |
## 🎓 Academic Details

- **Institution:** Woxsen University
- **School:** School of Technology
- **Course:** Design and Analysis of Algorithms
- **Project Type:** Project-Based Learning (PBL)
- **Faculty Mentor:** Dr. Monday Jubrin Abdullahi
- **Academic Year:** 2026–2027
- **Group:** 11

## 📚 References

The project draws on established work in graph algorithms, dynamic programming, k-median optimization, and local search.

Selected references:

- Cormen et al. — *Introduction to Algorithms*, 4th Edition.
- Dijkstra — Shortest-path algorithm, 1959.
- Floyd — Shortest-path algorithm, 1962.
- Kruskal — Minimum spanning tree algorithm, 1956.
- Prim — Minimum spanning tree algorithm, 1957.
- Arya et al. — Local search heuristics for k-median and facility location, 2004.

Refer to the project report for the complete bibliography.

---

**CloudPlace DAA | Group 11 | Woxsen University | 2026–2027**
