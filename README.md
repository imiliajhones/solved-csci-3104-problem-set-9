Download Link: https://assignmentchef.com/product/solved-csci-3104-problem-set-9
<br>
<ol>

 <li>(10 pts) Let <em>G </em>= (<em>V,E</em>) be a graph with an edge-weight function <em>w</em>, and let the tree <em>T </em>⊆ <em>E </em>be a minimum spanning tree on <em>G</em>. Now, suppose that we modify <em>G </em>slightly by decreasing the weight of exactly one of the edges in (<em>x,y</em>) ∈ <em>T </em>in order to produce a new graph <em>G</em><sup>0</sup>. Here, you will prove that the original tree <em>T </em>is still a minimum spanning tree for the modified graph <em>G</em><sup>0</sup>.</li>

</ol>

To get started, let <em>k </em>be a positive number and define the weight function <em>w</em><sup>0 </sup>as

)            if (<em>u,v</em>) 6= (<em>x,y</em>)

(<em>u,v</em>) =

<em>w</em>(<em>x,y</em>) − <em>k        </em>if (<em>u,v</em>) = (<em>x,y</em>) <em>.</em>

Now, prove that the tree <em>T </em>is a minimum spanning tree for <em>G</em><sup>0</sup>, whose edge weights are given by <em>w</em><sup>0</sup>.

<ol start="2">

 <li>(20 pts) Professor Snape gives you the following unweighted graph and asks you to construct a weight function <em>w </em>on the edges, using positive integer weights only, such that the following conditions are true regarding minimum spanning trees and singlesource shortest path trees:

  <ul>

   <li>The MST is distinct from any of the seven SSSP trees.</li>

   <li>The order in which Jarn´ık/Prim’s algorithm adds the safe edges is different from the order in which Kruskal’s algorithm adds them.</li>

   <li>Boru˙vka’s algorithm takes at least two rounds to construct the MST.</li>

  </ul></li>

</ol>

Justify your solution by (i) giving the edges weights, (ii) showing the corresponding MST and all the SSSP trees, and (iii) giving the order in which edges are added by each of the three algorithms. (For Boru˙vka’s algorithm, be sure to denote which edges are added simultaneously in a single round.)

1

<ol start="3">

 <li>(10 pts extra credit) Crabbe and Goyle think they have come up with a way to get rich by playing the foreign exchange markets in the wizarding world. Their idea is to exploit these exchange rates in order to transform one unit of British wizarding money into more than one unit of British wizarding money, through a sequence of money exchanges. For instance, suppose 1 British wizarding penny buys 0.82 French wizarding pennies, 1 French wizarding penny buys 129.7 Russian wizarding pennies, and finally 1 Russian wizarding penny buys 0.0008 British wizarding pennies. By converting these coins, Crabbe and Goyle think they could start with 1 British wizarding penny and buy 0<em>.</em>82 × 129<em>.</em>7 × 12 × 0<em>.</em>0008 ≈ 1<em>.</em>02 British wizarding pennies, thereby making a 2% profit! The problem is that those goblins at Gringots charge a transaction cost for each exchange.</li>

</ol>

Suppose that Crabbe and Goyle start with knowledge of <em>n </em>wizard monies <em>c</em><sub>1</sub><em>,c</em><sub>2</sub><em>,…,c<sub>n </sub></em>and an <em>n </em>× <em>n </em>table <em>R </em>of exchange rates, such that one unit of wizard money <em>c<sub>i </sub></em>buys <em>R</em>[<em>i,j</em>] units of wizard money <em>c<sub>j</sub></em>. A traditional <em>arbitrage opportunity </em>is thus a cycle in the induced graph such that the product of the edge weights is greater than unity. That is, a sequence of currencies h<em>c<sub>i</sub></em><sub>1</sub><em>,c<sub>i</sub></em><sub>2</sub><em>,…,c<sub>i</sub></em><em><sub>k</sub></em>i such that <em>R</em>[<em>i</em><sub>1</sub><em>,i</em><sub>2</sub>] × <em>R</em>[<em>i</em><sub>2</sub><em>,i</em><sub>3</sub>] × ··· × <em>R</em>[<em>i<sub>k</sub></em><sub>−1</sub><em>,i<sub>k</sub></em>] × <em>R</em>[<em>i<sub>k</sub>,i</em><sub>1</sub>] <em>&gt; </em>1. Each transaction, however, must pay Gringots a fraction <em>α </em>of the total transaction value, e.g., <em>α </em>= 0<em>.</em>01 for a 1% rate.

<ul>

 <li>When given <em>R </em>and <em>α</em>, give an efficient algorithm that can determine if an arbitrage opportunity exists. Analyze the running time of your algorithm.</li>

</ul>

Hermione’s hint: It is possible to solve this problem in <em>O</em>(<em>n</em><sup>3</sup>). Recall that BellmanFord can be used to detect negative-weight cycles in a graph.

<ul>

 <li>For an arbitrary <em>R</em>, explain how varying <em>α </em>changes the set of arbitrage opportunities that exist and that your algorithm might identify.</li>

</ul>

<ol start="4">

 <li>(40 pts) Bidirectional breadth-first search is a variant of standard BFS for finding a shortest path between two vertices <em>s,t </em>∈ <em>V </em>(<em>G</em>). The idea is to run <em>two </em>breadth-first searches simultaneously, one starting from <em>s </em>and one starting from <em>t</em>, and stop when they “meet in the middle” (that is, whenever a vertex is encountered by both searches). “Simultaneously” here doesn’t assume you have multiple processors at your disposal; it’s enough to alternate iterations of the searches: one iteration of the loop for the BFS that started at <em>s </em>and one iteration of the loop for the BFS that started at <em>t</em>.</li>

</ol>

As we’ll see, although the worst-case running time of BFS and Bidirectional BFS are asymptotically the same, in practice Bidirectional BFS often performs significantly better.

Throughout this problem, all graphs are unweighted, undirected, simple graphs.

<ul>

 <li>Give examples to show that, in the worst case, the asymptotic running time ofbidirectional BFS is the same as that of ordinary BFS. Note that because we are asking for asymptotic running time, you actually need to provide an infinite family of examples (<em>G<sub>n</sub>,s<sub>n</sub>,t<sub>n</sub></em>) such that <em>s<sub>n</sub>,t<sub>n </sub></em>∈ <em>V </em>(<em>G<sub>n</sub></em>), the asymptotic running time of BFS and bidirectional BFS are the same on inputs (<em>G<sub>n</sub>,s<sub>n</sub>,t<sub>n</sub></em>), and |<em>V </em>(<em>G<sub>n</sub></em>)| → ∞ as <em>n </em>→ ∞.</li>

 <li>Recall that in ordinary BFS we used a state array (see Lecture Notes 8) to keep track of which nodes had been visited before. In bidirectional BFS we’ll need <em>two </em>state arrays, one for the BFS from <em>s </em>and one for the BFS from <em>t</em>. Why? Give an example to show what can go wrong if there’s only one state In particular, give a graph <em>G </em>and two vertices <em>s,t </em>such that some run of a bidirectional BFS says there is no path from <em>s </em>to <em>t </em>when in fact there is one.</li>

 <li>Implement from scratch a function BFS(G,s,t) that performs an ordinary BFS in the (unweighted, directed) graph <em>G </em>to find a shortest path from <em>s </em>to <em>t</em>. Assume the graph is given as an adjacency list; for the list of neighbors of each vertex, you may use any data structure you like (including those provided in standard language libraries). Have your function return a pair (<em>d,k</em>), where <em>d </em>is the distance from <em>s </em>to <em>t </em>(-1 if there is no <em>s </em>to <em>t </em>path), and <em>k </em>is the number of nodes popped off the queue during the entire run of the algorithm.</li>

 <li>Implement from scratch a function BidirectionalBFS(G,s,t) that takes in a(n unweighted, directed) graph <em>G</em>, and two of its vertices <em>s,t</em>, and performs a bidirectional BFS. As with the previous function, this function should return a pair (<em>d,k</em>) where <em>d </em>is the distance from <em>s </em>to <em>t </em>(-1 if there is no path from <em>s </em>to <em>t</em>) and <em>k </em>is the number of vertices popped off of both queues during the entire run of the algorithm.</li>

 <li>For each of the following families of graphs <em>G<sub>n</sub></em>, write code to execute BFS and BidirectionalBFS on these graphs, and produce the following output:

  <ul>

   <li>In text, the pairs (<em>n,d</em><sub>1</sub><em>,k</em><sub>1</sub><em>,d</em><sub>2</sub><em>,k</em><sub>2</sub>) where <em>n </em>is the index of the graph, (<em>d</em><sub>1</sub><em>,k</em><sub>1</sub>) is the output of BFS and (<em>d</em><sub>2</sub><em>,k</em><sub>2</sub>) is the output of BidirectionalBFS.</li>

   <li>a plot with <em>n </em>on the <em>x</em>-axis, <em>k </em>on the <em>y</em>-axis, and with two line charts, one for the values of <em>k</em><sub>1 </sub>and one for the values of <em>k</em><sub>2</sub>:</li>

  </ul></li>

</ul>

<ol>

 <li><em>G<sub>n </sub></em>is an <em>n</em>×<em>n </em>grid, where each vertex is connected to its neighbors in the four cardinal directions (N,S,E,W). Vertices on the boundary of the grid will only have 3 neighbors, and corners will only have 2 neighbors. Let <em>s<sub>n </sub></em>be the midpoint of one edge of the grid, and <em>t<sub>n </sub></em>the midpoint of the opposite edge. For example, for <em>n </em>= 3 we have:</li>

</ol>

(When <em>n </em>is even <em>s<sub>n </sub></em>and <em>t<sub>n </sub></em>can be either “midpoint,” since there are two.) Produce output for <em>n </em>= 3<em>,</em>4<em>,</em>5<em>,…,</em>20.

<ol>

 <li><em>G<sub>n </sub></em>is a complete binary tree of depth <em>n</em>. <em>s<sub>n </sub></em>is the root and <em>t<sub>n </sub></em>is any</li>

</ol>

leaf. Produce output for <em>n </em>= 3<em>,</em>4<em>,</em>5<em>,…,</em>15. For example, for <em>n </em>= 3 we have:

<ul>

 <li>•                       <em>t</em><sub>3                                            </sub>•</li>

</ul>

iii. Random graphs. <em>G<sub>n </sub></em>is a graph on <em>n </em>vertices constructed as follows. For each pair of of vertices (<em>i,j</em>), get a random boolean value; if it is true, include the edge (<em>i,j</em>), otherwise do not. Let <em>s<sub>n </sub></em>be vertex 1 and <em>t<sub>n </sub></em>be vertex 2 (food for thought: why does it not matter, on average, which vertices we take <em>s,t </em>to be?) For each <em>n</em>, produce 50 such random graphs and report just the average values of (<em>d</em><sub>1</sub><em>,k</em><sub>1</sub><em>,d</em><sub>2</sub><em>,k</em><sub>2</sub>) over those 50 trials. Produce this output for <em>n </em>= 3<em>,</em>4<em>,</em>5<em>,…,</em>20.