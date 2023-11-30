# linearPrograms
linear problems can be solved in polynomial time.  
integer programming is considerably harder than linear programming  
`Regardless of objective function coefficients, an optimal solution occurs at a vertex`
把可行域的所有顶点找出来，然后比较它们的函数值，最大的那个解一定是最优解
## Convex set(LP feasible region is a convex set)
If two points x and y are in the set,then so is for (Jensen inequality)
### If there exist an optimal solution , then there exists one that is a vertex
## using linear programming for vertex cover

## interior point methods


# A*
At one extreme, if h(n) is 0, then only g(n) plays a role, and A* turns into Dijkstra’s Algorithm, which is guaranteed to find a shortest path.
If h(n) is always lower than (or equal to) the cost of moving from n to the goal, then A* is guaranteed to find a shortest path. The lower h(n) is, the more node A* expands, making it slower.
## Monotone

## Dijkstra 
Dijkstra algorithm is guaranteed to find a shortest path as long as none of the edges have a negative cost.  

# Definition of Efficiency
An algorithm is efficient if it has a polynomial running time.  
## NP 
the set of all problems for which there exists an efficient `certifier`.

# NP-Hardness and Reductions
There are literally thousands of NP-complete problems:
`Independent Set`,`Set Packing`,`Vertex Cover`,`Set Cover`,`Hamiltonian Cycle`,``
## Polynomial-Time Reductions
`Problem X is at least as hard as problem Y`, which means if we are capable of solving X, then we could also solve Y.
`IF X can be solved in polynomial time,then Y can be solved in polynomial time`
`IF Y cannot be solved in polynomial time,then X cannot be solved in polynomial time`
## 

## Polynomial running time
<img width="916" alt="image" src="https://github.com/zhang-mickey/algorithms/assets/145342600/b1141aa5-d5e9-44af-bf98-5fd743407084">

## Asymptotic Upper Bounds
<img width="649" alt="image" src="https://github.com/zhang-mickey/algorithms/assets/145342600/2bfe7975-778f-42a6-be1e-5221250c2da5">

## Asymptotic Lower Bounds
<img width="655" alt="image" src="https://github.com/zhang-mickey/algorithms/assets/145342600/13061e0a-1450-41b3-a5dc-f2b29bc4e630">

## Asymptotic Tight Bounds
<img width="669" alt="image" src="https://github.com/zhang-mickey/algorithms/assets/145342600/dd6e2768-7274-446f-b73a-216e0a4081a8">


# sort
## insertion-Sort
<img width="572" alt="image" src="https://github.com/zhang-mickey/algorithms/assets/145342600/76afa8b4-2c9e-4553-9f7f-bee97b75009f">  

# Knapsack Problem

## Subset Sum



# Graph
## Breath-first search
<img width="396" alt="image" src="https://github.com/zhang-mickey/algorithms/assets/145342600/3fda7d1d-4fb1-4755-8084-8758bc41a8ae">

## The largest independent set
独立集是指图 G 中两两互不相邻的顶点构成的集合

## Vertex Cover

## Set Cover
## Hamiltonian Cycle 
Given a directed graphG=(V,E),a cycle C inG is a Hamiltonian cycle if it visits each vertex exactly once.

## Graph Coloring




# Stable Matching Problem
`perfect match`: A set of edges M is a perfect matching if every node appears in exactly one edge of M. 


A match S is stable if it is perfect and there is no instability with respect to S. 

There exists a stable matching for every set of preference lists among the men and women.  
## Bipartite matching
<img width="388" alt="image" src="https://github.com/zhang-mickey/algorithms/assets/145342600/8a104e17-aae9-4910-b920-026f0fca1c3f">

## Gale-Shapley Stable Matching algorithm

# Greedy
## interval scheduling (maximum with a single resource)
The most obvious rule might be always select the available request that starts earliest, but this method does not yield an iptimal solution.   
requires the smallest interval of time, it still can produce a suboptimal schedule.   
### optimal solution: accept first the request that finishes first

## interval partition(schedule all the requests using as few resources as possible with many resource)
<img width="439" alt="image" src="https://github.com/zhang-mickey/algorithms/assets/145342600/2ed4891a-505d-4108-accc-3520b79d4a36">  
<img width="441" alt="image" src="https://github.com/zhang-mickey/algorithms/assets/145342600/fc9d5de3-f30e-455e-a0b1-8df46db55106">  

### Earliest-start-time-first algorithm is optimal. 

## Scheduling to minimizing lateness

### The earliest-deadline-first schedule S is optimal.

## optimal caching
<img width="570" alt="image" src="https://github.com/zhang-mickey/algorithms/assets/145342600/cafb98c0-d837-457d-8820-3360be520cf0">

### Farthest-in-future is optimal eviction schedule

## Minimum spanning trees

### cycle-cut intersection
A cycle and a cutset intersect in an `even` number of edges.  
<img width="369" alt="image" src="https://github.com/zhang-mickey/algorithms/assets/145342600/d3aecb7e-b71e-48a5-89ef-5b337361dc0a">



# Network Flow
A broad range of network flow problems could be reduced to the max-flow problem. 
## Maximal Flow problem
This problem describes a situation where the material from a source node is sent to a sink node. The source and sink node are connected through multiple intermediate nodes, and the common optimization goal is to maximize the material sent from the source node to the sink node.  

The cost of the flow is at most the capacity of the cut.  
### residual network
<img width="724" alt="image" src="https://github.com/zhang-mickey/algorithms/assets/145342600/a98f67c2-b8d0-4d49-8c9c-08d94000d29f">

### Ford–Fulkerson Algorithm
the most common way to approach the max-flow problem in polynomial time is the Ford-Fulkerson Algorithm (FFA).  
`essentially a greedy algorithm `  
starts from an emptyflow and, as long as it can find an augmenting path, improves the current solution using the path  
(1) find an augmenting path  
do a depth-first search  
(2) compute the bottleneck capacity  
(3) augment each edge and the total flow  

### Max flow Min cut
从网络中选择一些边，使得去掉这些边后，剩下两个不连通的分别包含源点和汇点的点集。割的大小是这些边的容量之和。在所有可行的割中，最小的割称为最小割  
最大流等于最小割  
`Upper bound`: Let f be any s-t flow, and(A,B) any s-t cut. Then v(f) ≤c(A,B).

`Given a flow of maximum value, we can compute an s-t cut of minimum capacity in O(m) time`  

### choose good augmenting paths to minimize the number of iterations
`choose paths with large bottleneck`: finding such paths can slow down each iteration, avoid this slowdown by not worrying about selecting the path that has exactly the largest bottleneck capacity.  
`scaling parameter ▲` : look for paths that have bottleneck capacity of at least ▲.  

### Dinitz blocking flow algorithm
Dinitz’s Algorithm improves the Edmonds-Karp Algorithm by discovering a blocking flow  

# Approximation algorithm 
How should we design algorithms for problems where polynomial time is probably an unattainable goal?  
ρ-approximation algorithm.   
・Runs in polynomial time.   
・Solves arbitrary instances of the problem   
・Finds solution that is within ratio ρ of optimum.  

## greedy algorithms

### Load balancing problem
(1) assign job to the machine whose load is smallest so far. `T≤2T*` 
(2)Longest processing time, sort jobs in decreasing order of processing times ,`T≤3/2T*`
### Center Selection Problem

## pricing method (primal-dual technique)

## linear programming and rounding

## using dynamic programming on a rounded version of the input

# Randomized Algorithm

## Contention Resolution
the processes cannot communicate with one other  


# dynamic programming
## Jump Game
<img width="440" alt="image" src="https://github.com/zhang-mickey/algorithms/assets/145342600/e2732282-804b-400f-81b8-142bcd2a2441">

```
class Solution:
    def canJump(self, nums: List[int]) -> bool:
        reachable_idx = 0
        for i, num in enumerate(nums):
            if i > reachable_idx:
                return False  # Can't move past the current index
            reachable_idx = max(reachable_idx, i + num)
        return reachable_idx >= len(nums) - 1
```
# Graph
## course schedule 
<img width="424" alt="image" src="https://github.com/zhang-mickey/algorithms/assets/145342600/56ef047c-f5a5-4a5b-a8dd-bf5a6f447ee9">
```

```

# Literature:
Jon Kleinberg, Eva Tardos: Algorithm Design  
https://www.cs.princeton.edu/~wayne/kleinberg-tardos/pdf/
