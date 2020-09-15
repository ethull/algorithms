# graph
- abstract ds
- parent abstract ds: set

## about
    group of vertices and edges used to connect them
    cyclic tree with a complex relationship instead of parent-child
    G(V, E), V(G) E(G) vertices/edges set
    terms
        path: sew of nodes between two nodes
        closed path: end node same as start node
        simple path: If all the nodes of the graph are distinct (not including start node), such path is the simple path
        cycle: path with no repeated edges (except first and last)
        connected graph: exists path between two vertices, no isolated nodes
        complete graph: every node connected with all other nodes, n(n-1)/2 edges
        weighted graph: each edge assigned length/weight, this + val indicates the edges traversal cost
        acyclic graph: graph with no cycles (any two vertices are connected <=1 path)
    loop: an edge associated with the similar end points
    degree of the node: number of edges that are connected to a node. degree 0 = isolated node

## types
    undirected
        edges not associated with directions
    directed (digraph)
        edges ordered pair
        arrow starts at initial node and ends at terminal node
    weighted directed graph

## repersentation
    sequential
        adjacency matrix
        rows and cols repersent vertices, n vertices = n*n
            undirected
                1 repersents edge from node (row) to node (col)
            directed graph
                1 repersents edge from initial node (row) to terminal node (col)
            weighted graph
                uses edge weight instead of 1
                this is also called a cost graph
                
    linked
        adjacency list
            undirected
                adjacency list is maintained for each node present
                stores the node value and a pointer to the next adjacent node to the respective node
                sum of the lengths of adjacency lists is equal to the twice of the number of edges present in an undirected graph
            directed
                sum of lengths of all the adjacency lists is equal to the number of edges present in the graph
            weighted directed graph
                each node has na extra field for the weight

    other
        implicit graphs
            compute local structure on the fly, requires zero space
        object-oriented
            obj for each vertex v
            v.neighbours = list of all neighbours
            suites implicit graphs
        incidence lists
            obj for each edge
            v.edges = list of outgoing edges


## operations
### graph traversal
    graph traversal is a complicated algorithm in itself, to traverse a graph between two points the single source shortest path problem algorithms are needed
    (see graphs README under ####variants/single-source spp (shortest path problem))[../../algorithms/graph/README.md]
