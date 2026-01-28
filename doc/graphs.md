---
title: Graphs
layout: default
nav_order: 12
---

### Graphs

A graph represents a set of **objects** and **pairwise connections** between them. In the example below, there are five objects (called **nodes**, here labled a,b,c,d,e) and six directed connections (called **directed edges**).  

<p align="center">
  <img src="/figs/graph-example.png" alt="graph example"/>
</p>

Graphs are mathematical objects, and there are many relationships that can be captured by graphs. For example, in a Twitter network, the nodes may be people and directed edges may indicate who follows whom (image from a [nice introduction to graph theory](https://medium.com/basecs/a-gentle-introduction-to-graph-theory-77969829ead8)).  In this example, the post's author Vaidehi follows Beyonc\`{e} but Beyonc\`{e} doesn't follow her back.

![Twitter network](https://miro.medium.com/max/1400/1*urJTrfWn8aZdhb9A-HXZVg.jpeg)

In this class, we will describe a graph as a list of nodes and a list of edges.  

1. The list of nodes will be a list of strings.   In the example above, the node list is
```
['a','b','c','d','e']
```

2. Each directed edge will be a list with **two** strings (e.g., `['a','b']` denotes that an edge starts at `a` and ends at `b`).  The list of edges will be a list of these two-element lists (so it's a **list of lists**).  In the example above, the edge list is
```
[['a','b'],['c','e'],['b','d'],['a','d'],['c','b'],['e','d']]
```

### NetworkX

We have already seen [built-in functions](#built-in-functions) such as `type()` and `print()`, and we've seen how to work with functions imported from another file (e.g. `helper_functions.py`).  The Python community has developed substantial modules that we can use, allowing us to work with new objects and call functions that they have written.  The [`networkx`](https://networkx.github.io/documentation/stable/index.html) module is a Python library for working with graphs.

### NetworkX: Creating a Graph

The following import statement imports this module and nicknames it `nx` so we can refer to it that way:

```
import networkx as nx
```

The lab and homework assignments will walk through how to make a graph and add nodes and edges. For more information beyond this crashcourse [see this tutorial for undirected graphs](https://networkx.github.io/documentation/stable/tutorial.html) (which uses `nx.Graph()` instead of `nx.DiGraph()` or `nx.MultiDiGraph()`).

Suppose we have a `nodes` variable and an `edges` variable as described above.  We can create a `networkx` graph with the following code:
```
G = nx.DiGraph()
G.add_nodes_from(nodes)
G.add_edges_from(edges)
```
The variable `G` represents a `networkx` object.  There are a number of functions that work directly on these graphs - see the [MultiDiGraph Methods List](https://networkx.github.io/documentation/stable/reference/classes/multidigraph.html) for all possibilities.

| Function Name  | Description (click for more information) |
| --- | --- |
| `G.add_node(n)` | [Add node `n` to `G`](https://networkx.github.io/documentation/stable/reference/classes/generated/networkx.MultiDiGraph.add_node.html#networkx.MultiDiGraph.add_node) |
| `G.has_node(n)` | [Checks if `n` is in `G`](https://networkx.github.io/documentation/stable/reference/classes/generated/networkx.MultiDiGraph.has_node.html#networkx.MultiDiGraph.has_node) |
| `G.number_of_nodes()` | [Returns the number of nodes in `G`](https://networkx.github.io/documentation/stable/reference/classes/generated/networkx.MultiDiGraph.number_of_nodes.html#networkx.MultiDiGraph.number_of_nodes) |
| `G.add_edge(u,v)` | [Add edge `[u,v]` to `G`](https://networkx.github.io/documentation/stable/reference/classes/generated/networkx.MultiDiGraph.add_edge.html#networkx.MultiDiGraph.add_edge) |
| `G.has_edge(u,v)` | [Checks if `[u,v]` is in `G`](https://networkx.github.io/documentation/stable/reference/classes/generated/networkx.MultiDiGraph.has_edge.html#networkx.MultiDiGraph.has_edge) |
| `G.number_of_edges()` | [Returns the number of edges in `G`](https://networkx.github.io/documentation/stable/reference/classes/generated/networkx.MultiDiGraph.number_of_edges.html#networkx.MultiDiGraph.number_of_edges) |
| `G.neighbors(n)` | [Returns the neighbors of `n` in `G`](https://networkx.github.io/documentation/stable/reference/classes/generated/networkx.MultiDiGraph.neighbors.html#networkx.MultiDiGraph.neighbors) |
| `G.succesors(n)` | [Return an iterator over the successors (outgoing nodes) of `n`](https://networkx.github.io/documentation/stable/reference/classes/generated/networkx.MultiDiGraph.successors.html?highlight=successors#networkx.MultiDiGraph.successors)<br> (use `list()` to convert to a list) |
| `G.predecessors(n)` | [Return an iterator over the predecessors (incoming nodes) of `n`](https://networkx.github.io/documentation/stable/reference/classes/generated/networkx.MultiDiGraph.predecessors.html?highlight=successors#networkx.MultiDiGraph.predecessors)<br> (use `list()` to convert to a list) |

### NetworkX: Drawing a Graph

We can visualize a `networkx` graph by drawing it to an output file with the `draw()` function. The syntax for drawing a graph is
```
nx.draw(G, with_labels=True)
```
where `with_labels=True` is an optional argument (if this is `True` then the labels are displayed on the nodes).  We then need to save the file (like we did when making plots or bar graphs with `matlplotlib`).  We'll also "clear" the plot in order to draw new things.
```
plt.savefig('graph.png')
plt.clf()
```

There are many ways to customize the `draw()` function with additional optional arguments; [see this page for a full list of options](https://networkx.github.io/documentation/stable/reference/generated/networkx.drawing.nx_pylab.draw_networkx.html#networkx.drawing.nx_pylab.draw_networkx).  Note that all optional arguments have a **default value** in case that argument is not specified.  

The `pos` optional argument specifies the way the nodes are positioned on the page.  There are functions that compute node positions in different ways, resulting in very different drawn graphs.  The [full list of layouts is available online](https://networkx.github.io/documentation/stable/reference/drawing.html#module-networkx.drawing.layout), and the `nx.spring_layout(G)` is the default layout algorithm when the `pos` argument is not specified.These functions can be called as an optional argument within the `draw()` function like so:
```
nx.draw(G, pos=nx.spring_layout(G), with_labels=True)
nx.draw(G, pos=nx.random_layout(G), with_labels=False)
```

### NetworkX: Finding Paths and Cycles

There are many networkx functions to work with directed graphs with multiple edges (called `MultiDiGraphs` in networkx).  [See this page for a full list of all networkx algorithms](https://networkx.github.io/documentation/stable/reference/algorithms/index.html).  Note that many of these functions are part of the `networkx` module, and pass the `networkx` graph as an input.  For these example functions, we assume that you've imported `networkx` like so:

```
import networkx as nx
```

| Function Name  | Description (click for more information) |
| --- | --- |
| `nx.find_cycle(G,orientation='original')` | [Find a cycle in `G`](https://networkx.github.io/documentation/stable/reference/algorithms/generated/networkx.algorithms.cycles.find_cycle.html) (use `orientation='original'`) |
| `nx.has_eulerian_path(G)` | [Checks if `G` has an Elerian path](https://networkx.github.io/documentation/stable/reference/algorithms/generated/networkx.algorithms.euler.has_eulerian_path.html) |
| `nx.eulerian_path(G)` | [Return an Eulerian path](https://networkx.github.io/documentation/stable/reference/algorithms/generated/networkx.algorithms.euler.eulerian_path.html) (use `list()` to convert to a list) |
| `nx.is_eulerian(G)` | [Checks if `G` has an Elerian circuit (cycle)](https://networkx.github.io/documentation/stable/reference/algorithms/generated/networkx.algorithms.euler.is_eulerian.html#networkx.algorithms.euler.is_eulerian) |
| `nx.eulerian_circuit(G)` | [Return an Eulerian cycle](https://networkx.github.io/documentation/stable/reference/algorithms/generated/networkx.algorithms.euler.eulerian_circuit.html) (use `list()` to convert to a list) |
| `nx.isolates(G)` | [Return nodes with no in or out edges](https://networkx.github.io/documentation/stable/reference/algorithms/generated/networkx.algorithms.isolate.isolates.html#networkx.algorithms.isolate.isolates) (use `list()` to convert to a list) |
