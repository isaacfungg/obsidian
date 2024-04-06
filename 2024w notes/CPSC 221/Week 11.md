***
`Complete Graph`: Maximum number of edges
`Connected Graph`: Path exists between every pair of vertices
`Connected Component`: Maximal connected subgraph
`Acyclic Graph`: No cycles (DFS would not encounter any back edges)
`Cyclic Graph`: Has cycles (DFS would encounter back edges)
`Weighted Graph`: Each edge is assigned a weight


#### Connectivity
`Undirected graphs`: Connected if there is a path between any two vertices
`Directed graphs`: Strongly connected if there is a directed path from any vertex to any other
`Digraphs`: Weakly connected if there is a path between any two vertices, ignoring direction
`Complete graph`: Has an edge between every pair of vertices

#### Graph Density
`Sparse graph`: Has $O(|V|)$ edges
`Dense graph`: Has $\theta(|V^2|)$

`Degree`
* Number of edges a vertex has
* To calculate the total number of edges in a graph $degree/2$
	* Total Degree is odd [cannot exist]
	* Edges > vertex - 1 [has a cycle]
	* Edges <= vertex - 1 [has no cycle]

#### Calculations
`DFS Back edges`
* Total edges - Tree edges = Back Edges
* Tree edges = n - 1

#### Running Time
For a simple connected graph with n vertices and m edges, what is the tightest worst case running time for removing a vertex, if the graphs are represented with Edge List, Adjacency List, Adjacency Matrix
* O(m), O(deg(v)), O(n)

