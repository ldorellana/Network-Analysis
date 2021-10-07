# Network-Analysis

Networks can give us insights like:
- iportant entities (influencers)
- pathfinder (efficient transportation routes)
- clustering (finding communities)

#### Networks are composed of:
Nodes: entities that are part of the network
- name: name of the node
- metadata: id, age, etc
Edges: connection between nodes
- (u,v): the 2 nodes coneted by the edge
- metadata: date, weight, etc. 

### NetworkX API

Basic systanxis
'''python
import networkx as nx
G = nx.Graph()

G.add_nodes_from([1, 2, 3])
G.nodes()

G.add_edge(1, 2)
G.edges()
'''


# INDEX

## Intro to NetworkX
- Basic commands
- Simple graphs
- Draw graph



## Types of graph

- indirected: no direccion on the association
- directed: directly associated nodes
- multi(di)graph: multiple edges in between nodes is possible
- weighted: insted of multiiple edges, a weight is assigned
- self-loop: a node has an edge to himself

## Visualizing Networks

#### Matrix Plot
Matrix with columns and rows for each node
The insides are colored if there is an edge

### Arc Plots
Nodes ordered in a line, edges represented by semicircles

### Circle Plots
Nodes are ordered in a cirucalr way and arc lines represent the edges


### nxviz API

Ovierview
'''python
import nxviz as nv

ap = nv.ArcPlot(G)
ap.draw()
plt.show()

'''

### Degree Centrality
How many neighboars does a node have
- If self loops are allowed
N neighbors / Total nodes
- if self loops are not allowed
N neighbors / (Total nodes - 1)

'''python
G.neighors(node)
nx.degree_centrality(G)
'''

### Path Finding
It is important for:
- Optimization: shortest transport path
- Modeling: disease spread, information passing

Breath-first Search

### Betweenness centrality

N shortest paths thru node / all possible shortes paths

Catches bottle neck nodes rather than highly connected nodes

### Communities & Cliques

Groups completely connected between themselves
Nodes completely connected to every node by edges.

Simples clique possible is a triangle (3 fully connected nodes)

Possible for friend recommendations (1 knows 2 people but the other dont know eachother)