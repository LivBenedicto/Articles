### GRAPH Coloring

Problem :  
> "Assign colors to certain elements of a graph subject to certain constrains". - Geeks for Geeks  

**>> Coloring in a graph context:**
A way to color adjacent vertices in a different color.
* Chromatic number : smallest number of colors needed to color a G graph.  
    * Is a NP-Complete.  
    * Can be the least number of color needed or not.
        ** Discovered by counting of colors in a graph.
    * k = chromatic number, writes k-Colorable.  

**>> Theorem:**
* Vertices coloring
- Every 2-chromatic graph is bipartite graph or is a tree.
- Complete graph is a λ(Kn) = n, - chromatic number arbitrarily large.  
- λ(G) = 1 : null graph.  
- λ(G) = 2 : bipartite graph non-null or a tree.  
- 3-chromatic : Cn and Wn, with odd n, and Petersen Graph.
- 4-chromatic : wheel graph with a even vertex.

> Petersen Graph
- Undirected graph with 10 vertices and 15 edges.
- Chromatic number : 3
- Chromatic index : 4

> Four Color Theorem
- Proposed in 1852 and resolved in 1976 by K. Appele W. Haken.
- A chromatic number in a planar graph isn't greater than 4.

* Coloring of circuits
- Circuit composed by n >= 3 vertices.
    * 2-chromatic : even n.
    * 3-chromatic : odd n.
- Simple graph G, with least one edge.
    * 2-chromatic if G don't contain an odd circuit.


**>> Solution steps:**
- #1 step : Find out which is the **highest** adjacent vertex and color it with any color.  
    * Maximum degree vertex starts.   
    * Note: this color will be used to color all the non-adjacents vertices.  
- #2 step : Repeat the #1 step for all non-colored vertices but with a new color.  
- #3 step : The #1 step is repeated until all vertices are colored.  

_#TIP_  
* Only for simple connected graph G = (V,E).  
- Don't consider a disconnect graph : the colors used in one component don't affect another component.  
- Parallel edges don't affect the coloration.  
- Graph cannot contain loops.  

* Bipartite  
- Represent as λ(Kn,m) = n.  
_#End TIP_  

**#SOURCE**  
Graph Coloring | Set 1 (Introduction and Applications) - https://www.geeksforgeeks.org/graph-coloring-applications/  
Coloring Graphs Part 1: Coloring and Identifying Chromatic Number - https://www.youtube.com/watch?v=-gOh1aG0_zQ  
University - class notes.