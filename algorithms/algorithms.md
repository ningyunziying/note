## Data Structures

+ AVL Tree:自平衡二叉查找树，AVL树得名于它的发明者G. M. Adelson-Velsky和E. M. Landis
+ B-Tree:多路搜索树
+ Binary Heap:二叉堆
+ Binary Search Tree:二叉查找树
+ Compact Suffix Trie(backed by a Patricia Trie):紧凑后缀Trie
+ Disjoint Set:并查集
+ Binary Indexed Tree(B.I.T), Fenwick Tree
+ Graph
  - Undirected
  - Directed (Digraph)
+ Hash Array Mapped Trie(HAMT)
+ Hash Map(associative array)
+ Interval Tree
+ Implicit Key Treap
+ KD Tree(k-dimensional tree or k-d tree)
+ List(backed by an array or a linked list)
+ LCP Array(Longest Common Prefix)(backed by a Suffix Array)
+ Matrix
+ Patricia Trie
+ Quad-Tree(Point-Region or MX-CIF)
+ Queue(backed by an array or a linked list)
+ Radix Trie(associative array)
+ Red-Black Tree
+ Segment Tree
+ Skip List
+ Splay Tree
+ Stack(backed by an array or a linked list)
+ Suffix Array
+ Suffix Tree(Ukkonen's algorithm)
+ Suffix Trie(backed by a Trie)
+ Ternary Search Tree
+ Treap
+ Tree
+ Tree Map(associative array)(backed by an AVL Tree)
+ Trie
+ Trie Map(associative array)(backed by an Trie)

### Mathematics

+ Distance:距离 1.chebyshev: 切比雪夫距离 2.euclidean: 欧几里得距离。
+ Division:除法 1. loop 2. recursion 3.shifts and multiplication 4.only shifts 5.logarithm
+ Multiplication:乘法 1.loop 2. recursion 3. only shifts 4. logarithms 5. Fast Fourier Transform
+ Exponentiation取幂 1. recursive exponentiation 2. fast recursive exponentiation 3. fast modular recursive exponentiation
+ Primes 1. is prime 2. prime factorization 3. sieve of eratosthenes 4. Miller-Rabin test 5. Co-Primes (relatively prime, mutually prime) 6. Greatest Common Divisor 6.1using Euclid's algorithm 6.2 using recursion
+ Permutations 1. strings 2. numbers
+ Modular arithmetic 1. add 2. subtract 3. multiply 4. divide 5. power
+ Knapsack:背包问题(*Knapsack* problem)是一种组合优化的NP完全问题
+ Ramer Douglas Peucker:RDP算法 该算法的目的是为了减少曲线中的点

### Numbers

- Integers
  - to binary String
    - using divide and modulus
    - using right shift and modulus
    - using BigDecimal
    - using divide and double
  - is a power of 2
    - using a loop
    - using recursion
    - using logarithm
    - using bits
  - to English (e.g. 1 would return "one")
- Longs
  - to binary String
    - using divide and modulus
    - using right shift and modulus
    - using BigDecimal
- Complex
  - addition
  - subtraction
  - multiplication
  - absolute value
  - polar value

### Graphs

- Find shortest path(s) in a Graph from a starting Vertex
  - Dijkstra's algorithm (non-negative weight graphs)
  - Bellman-Ford algorithm (negative and positive weight graphs)
- Find minimum spanning tree
  - Prim's (undirected graphs)
  - Kruskal's (undirected graphs)
- Find all pairs shortest path
  - Johnsons's algorithm (negative and positive weight graphs)
  - Floyd-Warshall (negative and positive weight graphs)
- Cycle detection
  - Depth first search while keeping track of visited Verticies
  - Connected Components
- Topological sort: 拓扑排序
- A* path finding algorithm: 一种静态路网中求解最短路径最有效的直接搜索方法
- Maximum flow: 最大流问题
  - Push-Relabel
- Graph Traversal
  - Depth First Traversal
  - Breadth First Traversal
- Edmonds Karp: *Edmonds*-Karp算法是用于在O（V E2）时间内计算流网络中的最大流量的Ford-Fulkerson方法的实现
- Matching
  - Turbo Matching
- Lowest common ancestor in tree: 最小公共祖先

### Search

- Get index of value in array
  - Linear
  - Quickselect
  - Binary [sorted array input only]
  - Lower bound [sorted array input only]
  - Upper bound [sorted array input only\]
  - Optimized binary (binary until a threashold then linear) [sorted array input only]
  - Interpolation [sorted array input only\]

### Sequences

- Find longest common subsequence (dynamic programming)
- Find longest increasing subsequence (dynamic programming)
- Find number of times a subsequence occurs in a sequence (dynamic programming)
- Find i-th element in a Fibonacci sequence
  - using a loop
  - using recursion
  - using matrix multiplication
  - using Binet's formula
- Find total of all elements in a sequence(Arithmetic Progression)
  - using a loop
  - using Triangular numbers
- Largest sum of contiguous subarray (Kadane's algorithm)
- Longest palin­dromic sub­se­quence (dynamic programming)

### Sorts

- American Flag Sort
- Bubble Sort
- Counting Sort (Integers only)
- Heap Sort
- Insertion Sort
- Merge Sort
- Quick Sort
- Radix Sort (Integers only)
- Shell's Sort

### String Functions

- Reverse characters in a string
  - using additional storage (a String or StringBuilder)
  - using in-place swaps
  - using in-place XOR
- Reverse words in a string
  - using char swaps and additional storage (a StringBuilder)
  - using StringTokenizer and additional (a String)
  - using split() method and additional storage (a StringBuilder and String[])
  - using in-place swaps
- Is Palindrome
  - using additional storage (a StringBuilder)
  - using in-place symetric element compares
- Subsets of characters in a String
- Edit (Levenshtein) Distance of two Strings (Recursive, Iterative)

## Problem

### 1. add digit

Given a non-negative integer `num`, repeatedly add all its digits until the result has only one digit.

Example:

```
Input: 38
Output: 2 
Explanation: The process is like: 3 + 8 = 11, 1 + 1 = 2. 
             Since 2 has only one digit, return it.
```

Follow up:
Could you do it without any loop/recursion in O(1) runtime?

**Hint:**

1. A naive implementation of the above process is trivial. Could you come up with other methods?
2. What are all the possible results?
3. How do they occur, periodically or randomly?
4. You may find this [Wikipedia article](https://en.wikipedia.org/wiki/Digital_root) useful.

### 2. majority element

Given an array of size *n*, find the majority element. The majority element is the element that appears more than `⌊ n/2 ⌋` times.

You may assume that the array is non-empty and the majority element always exist in the array.

原理：如果majority元素存在（majority元素个数大于n/2,个数超过数组长度一半），那么无论它的各个元素位置是如何分布的，其count经过抵消和增加后，最后一定是大于等于1的。如果不能保证majority存在，需要检验。复杂度：O(N)