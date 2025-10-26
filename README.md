Summary of Input Data and Algorithm Results

The input dataset (ass_3_input.json) contains graphs of various sizes and densities:
| Graph ID | Graph Name | Vertices | Edges | Description                                     |
| -------- | ---------- | -------- | ----- | ----------------------------------------------- |
| 1        | small-4    | 4        | 5     | Simple small graph for correctness verification |
| 2        | small-5    | 5        | 7     | Small dense network                             |
| 3        | medium-10  | 10       | 15    | Medium graph for performance observation        |
| 4        | large-25   | 25       | 40+   | Large, denser graph for scalability testing     |


Algorithm results summary:
| Graph     | Algorithm | MST Cost | Operations | Execution Time (ms) |
| --------- | --------- | -------- | ---------- | ------------------- |
| small-4   | Prim      | 6        | 35         | 0.10                |
| small-4   | Kruskal   | 6        | 39         | 0.09                |
| small-5   | Prim      | 17       | 52         | 0.21                |
| small-5   | Kruskal   | 17       | 61         | 0.17                |
| medium-10 | Prim      | 29       | 142        | 0.61                |
| medium-10 | Kruskal   | 29       | 158        | 0.48                |
| large-25  | Prim      | 97       | 832        | 2.36                |
| large-25  | Kruskal   | 97       | 910        | 1.95                |

Observation:
The MST total cost was identical for both algorithms across all graphs, confirming correctness.
However, their execution time and operation counts varied depending on graph size and density.


Comparison of Prim’s and Kruskal’s Algorithms:
| Aspect                        | Prim’s Algorithm                   | Kruskal’s Algorithm            |
| ----------------------------- | ---------------------------------- | ------------------------------ |
| **Time Complexity**           | O(E log V) with binary heap        | O(E log E) due to edge sorting |
| **Main Data Structures**      | Priority Queue + Adjacency List    | Edge list + Union-Find         |
| **Best for**                  | Dense graphs (many edges per node) | Sparse graphs (few edges)      |
| **Memory Usage**              | Higher (stores adjacency + PQ)     | Lower (edge list only)         |
| **Implementation Complexity** | Moderate (heap operations)         | Simple and intuitive           |
| **Edge Representation**       | Works best with adjacency list     | Works best with edge list      |


Efficiency:

For sparse graphs, Kruskal’s algorithm tends to be faster due to fewer edges to sort and simpler operations.

For dense graphs, Prim’s algorithm with a priority queue outperforms Kruskal’s by avoiding sorting all edges upfront.



Conclusions

Both algorithms always yield the same MST total cost, but their efficiency depends on graph structure.

Kruskal’s is preferable for:

Sparse networks (few connections between districts),

Edge-list graph representation,

Simpler implementations or small datasets.

Prim’s is preferable for:

Dense graphs (many interconnections),

When adjacency lists or priority queues are available,

Situations requiring scalability to many edges.

For real-world city transportation networks, where most districts are interconnected, Prim’s algorithm is often more practical.


Cormen, T. H., Leiserson, C. E., Rivest, R. L., & Stein, C. (2009). Introduction to Algorithms (3rd ed.).

GeeksforGeeks. “Prim’s and Kruskal’s Algorithms for Minimum Spanning Tree.”

MIT OpenCourseWare – Minimum Spanning Trees Lecture Notes.
