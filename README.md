# Autonomous Delivery Agent

##  Project Overview
This project implements an **autonomous delivery agent** that navigates a 2D grid city to deliver packages efficiently.  
It supports multiple search strategies, handles varying terrain costs, and adapts to dynamic obstacles (e.g., moving vehicles).

Implemented algorithms:
- **BFS** (Uninformed Search)  
- **Uniform Cost Search (UCS)**  
- **A*** (Informed Search, Manhattan/Euclidean heuristics)  
- **Simulated Annealing** (Local Search replanning)  

The project is developed as part of **CSA2001 – Fundamentals of AI and ML** coursework.  

---

##  Features
- Grid environment with multiple terrain types (`road`, `grass`, `water`, `building`, `obstacle`)  
- Terrain-specific costs (road = 1, grass = 2, water = 5, obstacles/buildings = impassable)  
- Support for **dynamic obstacles** that move over time  
- Multiple pathfinding strategies with performance comparison  
- Metrics reporting:  
  - Path cost  
  - Path length  
  - Nodes expanded  
  - Computation time  
- Map visualization using **Matplotlib**  

---


##  Installation
1. Clone or download the repository.
2. Install dependencies:
   ```bash
   pip install numpy matplotlib
   ```

---

##  Usage
### 1. Run with defaults
```bash
python autonomous_delivery_agent.py
```
This will:
- Create test maps (`small.map`, `medium.map`, `large.map`, `dynamic.map`)  
- Run **A*** on the small map  
- Show visualization  

---

### 2. Run with custom arguments
```bash
python autonomous_delivery_agent.py <map_file> <start_x> <start_y> <goal_x> <goal_y> \
  --algorithm <algo> --heuristic <h> --visualize
```

#### Arguments:
- `map_file`: Path to the map file (`small.map`, `medium.map`, `large.map`, `dynamic.map`)  
- `start_x start_y`: Start coordinates  
- `goal_x goal_y`: Goal coordinates  
- `--algorithm, -a`: `bfs`, `ucs`, `astar`, `sa`  
- `--heuristic`: `manhattan`, `euclidean` (only for A*)  
- `--visualize, -v`: Show visualization  
- `--fuel, -f`: Set fuel constraint (default: ∞)  
- `--compare, -c`: Run all algorithms on all maps and compare  

#### Example:
```bash
python autonomous_delivery_agent.py medium.map 0 0 9 9 -a astar --heuristic manhattan -v
```

---

### 3. Compare algorithms
```bash
python autonomous_delivery_agent.py small.map 0 0 4 4 --compare
```
This will run BFS, UCS, A*, and Simulated Annealing on all maps and print performance metrics.

---

##  Sample Output
```
Algorithm Comparison Results
================================================================================

Map: small.map
----------------------------------------
BFS   : Found=True, Cost=8.00, Nodes=15, Time=0.0003s
UCS   : Found=True, Cost=8.00, Nodes=12, Time=0.0005s
ASTAR : Found=True, Cost=8.00, Nodes=10, Time=0.0002s
SA    : Found=True, Cost=9.00, Nodes=50, Time=0.0056s
```

---

##  Deliverables
- **Source Code**: `autonomous_delivery_agent.py`  
- **Maps**: `small.map`, `medium.map`, `large.map`, `dynamic.map`  
- **Report**: Analysis of algorithm performance (separate PDF, not included here)  
- **Demo**: Run with `--visualize` or record execution  

---

