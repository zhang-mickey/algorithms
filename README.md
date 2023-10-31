# Definition of Efficiency
An algorithm is efficient if it has a polynomial running time.  
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



# Graph
## Breath-first search
<img width="396" alt="image" src="https://github.com/zhang-mickey/algorithms/assets/145342600/3fda7d1d-4fb1-4755-8084-8758bc41a8ae">


# Stable Matching Problem
`perfect match`: A set of edges M is a perfect matching if every node appears in exactly one edge of M. 


A match S is stable if it is perfect and there is no instability with respect to S. 

There exists a stable matching for every set of preference lists among the men and women.  
## Bipartite matching
<img width="388" alt="image" src="https://github.com/zhang-mickey/algorithms/assets/145342600/8a104e17-aae9-4910-b920-026f0fca1c3f">

## Gale-Shapley Stable Matching algorithm

# Network Flow
A broad range of network flow problems could be reduced to the max-flow problem. 
## Maximal Flow problem
This problem describes a situation where the material from a source node is sent to a sink node. The source and sink node are connected through multiple intermediate nodes, and the common optimization goal is to maximize the material sent from the source node to the sink node.  

The cost of the flow is at most the capacity of the cut.  
### residual network
<img width="724" alt="image" src="https://github.com/zhang-mickey/algorithms/assets/145342600/a98f67c2-b8d0-4d49-8c9c-08d94000d29f">

### Ford–Fulkerson Algorithm
he most common way to approach the max-flow problem in polynomial time is the Ford-Fulkerson Algorithm (FFA).
`essentially a greedy algorithm `  
starts from an emptyflow and, as long as it can find an augmenting path, improves the current solution using the path  
(1) find an augmenting path  
do a depth-first search
(2) compute the bottleneck capacity  
(3) augment each edge and the total flow  
# Approximation algorithm 

## Randomized Algorithm


# Literature:
Jon Kleinberg, Eva Tardos: Algorithm Design  
https://www.cs.princeton.edu/~wayne/kleinberg-tardos/pdf/
