### How to implement a GRAPH

Is a finite non-linear data structure, that is compose by nodes (circles, - vertices) and edges (lines, - connect a pair of nodes). Used for networks, like path in a city, or social media, as people or cities as a vertex.
* Each node is a structure (seems a object in Js { informations })

**>> Components of a graph:**
- A finite set of nodes: ex.: (node1, node2, node3, node4)
- A finite set of edges connections the needs be ordered: ex.: {(node1, node2), (node2, node3), (node2, node4), (node4, node1)}
	* Read it: (node1 are directly connected with the node2)
	* If the graph is a directed graph (d-graph), the connection needs to be exactly in the orde that apears in the draw graph.
	* So: (u, v) is different from (v, u), in case of a d-graph, the edge indicates the direction that the current node appoints.
	* u: current node, v: node that I want to go.
	* Edge may be valorated (also called cost or weight).

**>> Types of a graph:**
- Undirected: (u, v) = (v, u), read (u, v) is equal to (v, u).
	* Symmetric in adjacent matrix case, because currentNode have only one connection with the
	nodeToGo, and his cost will be the same for any direction.
- Directed: (u, v) <> (v, u), read (u, v) is different to (v, u).
	* d-graph
	* Because currentNode can have one or more connections with any nodeToGo in the graph.

**>> Representation of a graph:**  
It can be divided into two parts, commonly used and not to much used, the choice will totally depends on the situation you need to resolve.

> Commonly:
- Adjacency matrix: it’s a array with a 2Dimension, and his size is equal to V * V, where V represents the sum of all the nodes (vertices) in the graph.
	* ex.: `adjacencyMatrix[currentNode][nodeToGo] = 1`, so “1” indicates that has an connection between the currentNode from nodeToGo.
	* Valorated graph. ex.: `adjacencyMatrix[currentNode][nodeToGo] = weight`, the “weight” is the cost of the currentNode take to get to the nodeToGo.
	- Complexity:  
		O(1): deleting/adding an edge or search if exists an edge connection. ex.: `if matrix[currentNode][nodeToGo] == 1`, then have a connection.  
		O(V):  
		O(V²): adding a new node and memory (memory is defined by V*V, so if it’s dense or sparse the graph will occupy the same space in both cases).

- Adjacency list: it’s an array of lists, where the size is equal to the numbers of vertices, and the entry in the array[nPosition] is a list that contains all the vertices that have a adjacency connection to the vertex nPosition. ex.: `array[nPosition] = [node1, node2, node5]`.
	* Valorated graph: it’s almost the same implementation, with the difference that instead of a list, it’s a list pair list, so the array [nPostion] receves [(node, weight)], but depends on the implemention that you are using for it. ex.: `array[nPosition] = [(node1, 15), (node2, 96), (node5, 47)]`.
	- Complexity:  
		O(V+E): space in memory, but this complexity changes if the array being dense O(V²) or sparse O(V), because the space ocuppied in memory is iterated over the number of connections. Where “E” is equal to the numbers of edges.  
		O(n): adding a new vertex, but if is dense it’s gonna be O(V), in case of a sparse graph that changes to O(1). Where “n” is the numbers of the new neighbors nodes added.  
		O(V): to search if exists an edge connection between u and v node.

> Not much commonly:
- Incidence matrix
- Incidence list

_#TIP_  
Set vs List  
Both things are the same, belongs to the same interfaces. Therefore, the methods are the same, but the implementation of the methods are different, because:
- Set : set of elements. C# : `HashSet<T>()`
	* Doesn’t accept duplicated elements.
- List : set of elements. C# : `ArrayList<T>()`
	* Accept duplicated elements.

LinkedList vs Array
- Linked List : is a collection of Nodes, that’s a type that has two fields, one for data storage and one for a link, it’s a reference to the next node.
	* To figure out the previous or next node: “sucessors” and “predecessors”.
	* First element it’s commonly implements as “Header”. Last element appoints to null.
	* The elements are referenced by a relationship with the predecessor element. ex.: Bread “follows” Milk.
- Array : it’s a collections objects.
	* The elements are referenced by a index (the position that this element are storege in the list). ex.: Bread is in the 2th position and Milk is in the 3th position.  
> Main Difference
The main difference between linked list and array, is deleting or inserting an element. Because, in the linked list don’t have to realocate all the elements in the list, It’s just need to set the  link (reference) of my previous element to the new node and then do the same thing to the next link.
In case of array, that will need realocate all elements to put the new element, depends on the 
index that wants to insert. To deleting it's the same thing, deleting an element in an array, the index still there but empty, so it’s necessary realocate all  elements. Isn’t perfomatic.

Sparse vs Dense
- Sparse: means the graph contains a less number of edges.
- Dense:

Deleting
- Deleting an edge it’s differente than deleting a vertice, even that node appoints to a another node, isn’t means that this “appoints to” is an edge,  because edge is a connection, and node is the data that will be connected.  

_#End TIP_