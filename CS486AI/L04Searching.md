## L04, 1/13, States and Searching

- A graph consists of a set N of nodes and a set A of ordered
pairs of nodes, called arcs .

Maintain a **frontier** of paths that have been explored

Search strategy determines how the frontier expands

Types of search
1. Uninformed (Blind)
2. Heuristic
3. More sophisticated "hacks"

DFS - not guaranteed to end for infinite graph and cycles
- add extra cycle check
- linear in space complexity

BFS - queue format
- needs to be aware of **branching factor**
  - if guaranteed to be finite, then will for sure find solution
- time complexity is exponential on BF -> $bf^n$, n being length
- space complexity as well 

Lowest Cost first search
- cost of path is the sum of all costs for each arc
- greedy: choose lowest cost first at each stage
  - keep in priority queue, when tied, BFS


### Heuristic Search
- don't ignore goals when searching
  - use extra knowledge - **heuristic**
- takes into account of h(n) -> estimated cost
  - make sure always underestimate
- eg. Manhattan distance, speed, straight line

Greedy best first search, only care about h, not optimal

Heuristic DFS - add to stack according to `h`
- locally does a best first search, same problems as DFS

A* search
- use both path cost and `h`
- `f(p) = h(p) + c(p)`
- mix of both lowest cost first and best first
- always choose the lowest by `f(p)` in priority queue
- A* usually finds the best solution
  - when BF is finite, all arcs are none-0, `h` underestimate the costs
- **Admissible H(n) never overestimate the costs**

### Constructing a Heuristic
- Relax the game, make it easier
- find which heuristic works best in each simplification

Strategy | Frontier  Selection|  Halts? | Space | Time
-- | -- | -- | -- | -- 
Depth-first | Last node added | No  |Linear | Exp
Breadth-first | First node added|  Yes | Exp | Exp
Heuristic depth-first | Local1 min h(n)| No | Linear | Exp
Best-first | Global2  min h(n)| No  |Exp | Exp
Lowest-cost-first | Minimal  cost(n)| Yes | Exp|  Exp
A ∗| Minimal f(n) |Yes |Exp | Exp

Path Pruning
- for DFS -> constant time as you can add flags
- other cases, linear time in length of the path

Multiple Path Pruning
- prune a path to `n` that a path to has already been found for
- store all node already discovered path to

Problem: what if we end up discovering a path that is shorter for n?
- go back and fix every path's prefix
- remove the old paths
- ensure this does not happen: shortest path first (lowest-cost-first search)

Monotonic Restriction
- $h(m) − h(n) ≤ cost(m, n)$ for every arch
- make sure heuristic estimate is always less than actual cost
- If h satisfies the monotone restriction, A ∗ with multiple path pruning always finds the shortest path to a goal.
- basically, *admissible* between any 2 nodes!

Iterative Deepening
- all halting algo requires exp space
- what if recompute the frontier instead of saving them
- depth-bounded DFS


Note: searching is symmetrical, if forward does not work, then check backwards (BF for forward vs backward: in vs out)

Bidirectional: use both sides
- use BFS to try to get to the middle, and see if the other side can meet the frontier
- save exponentially in time and space

Island driven search
- find all the path in between and make it into `m` subproblems
  - hard to say which path are correct and which are good island

- DP: work backwards find the cost and store it for each node
- 