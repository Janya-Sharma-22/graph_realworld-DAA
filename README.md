Design and Analysis of Algorithms Lab – Assignment 3
Student: Janya Sharma
Program: BCA (AI & DS), Semester V
Instructor: Dr. Aarti Sangwan
Course Code: ENCA351

**Overview**

*This project demonstrates how core graph algorithms (BFS, DFS, Bellman-Ford, Dijkstra, and MST algorithms) can be applied to real-world problems such as social networking, navigation, emergency routing, and infrastructure planning.
Each problem maps a real-world scenario into a graph data structure and uses an appropriate algorithm to solve it efficiently.*

**🧩 Problem 1 – Social Network Friend Suggestion (BFS / DFS)**

Goal:
Recommend new friends in a social network based on mutual connections (friends-of-friends).

Algorithm Used:
Breadth-First Search (BFS)

Approach:
Represent users as nodes and friendships as undirected edges.
Perform BFS from a given user up to depth 2 (to find friends-of-friends).
Exclude direct friends and the user themselves.

Time Complexity: O(V + E)
Space Complexity: O(V)

Real-World Applications:
Used by Facebook, LinkedIn, and Instagram to recommend mutual friends.

**🧩 Problem 2 – Route Finding (Bellman-Ford Algorithm)**

Goal:
Find the shortest path between locations even when some road segments have negative weights (e.g., discounts or reversed tolls).

Algorithm Used:
Bellman-Ford

Approach:
Model cities as nodes and roads as directed weighted edges.
Relax all edges V–1 times to compute shortest distances.
Detect and report negative weight cycles.

Time Complexity: O(V × E)
Space Complexity: O(V)

Why Bellman-Ford?
Handles negative edge weights.
Detects negative cycles.

Real-World Applications:
Used in routing protocols like RIP (Routing Information Protocol) and navigation systems handling variable travel costs.

**🧩 Problem 3 – Emergency Response (Dijkstra’s Algorithm)**

Goal:
Determine the fastest route for an emergency vehicle to reach any location, assuming all roads have positive travel times.

Algorithm Used:
Dijkstra’s Algorithm (with Min-Heap)

Approach:
Represent intersections as nodes and roads as weighted edges.
Use a priority queue to repeatedly expand the nearest node.
Calculate minimum travel times from the emergency base to all others.

Time Complexity: O(E log V)
Space Complexity: O(V + E)

Why Dijkstra?
Extremely efficient for large graphs with positive weights.
Works perfectly for real-time navigation and disaster response systems.

**🧩 Problem 4 – Network Cable Installation (MST – Prim’s / Kruskal’s)**

Goal:
Connect all office buildings with minimum total cable length, avoiding redundant connections.

Algorithm Used:
Prim’s Algorithm (Greedy)

Approach:
Represent offices as nodes and potential cable paths as weighted edges.
Start from any node and grow the MST by always selecting the minimum-weight edge that connects to an unvisited node.
Optionally, compare with Kruskal’s Algorithm.

Time Complexity: O(E log V)
Space Complexity: O(V + E)

Why MST?
Ensures all offices are connected with minimum total cost and no cycles — essential in telecom, electrical, and computer networks.

***Comparative Analysis of All Algorithms***

| Problem                          | Algorithm                | Handles Negative Weights? | Directed/Undirected   | Time Complexity | Space Complexity | Best Use Case                          | Drawback                                 |
| -------------------------------- | ------------------------ | ------------------------- | --------------------- | --------------- | ---------------- | -------------------------------------- | ---------------------------------------- |
| Social Network Friend Suggestion | **BFS / DFS**            | ❌ No                      | Undirected            | O(V + E)        | O(V)             | Mutual friend recommendations          | Not optimal for weighted graphs          |
| Route Finding (Navigation)       | **Bellman-Ford**         | ✅ Yes                     | Directed              | O(V × E)        | O(V)             | Maps with possible negative weights    | Slower for large networks                |
| Emergency Response               | **Dijkstra**             | ❌ No                      | Directed / Undirected | O(E log V)      | O(V + E)         | Fastest path in positive-weight graphs | Fails with negative edges                |
| Network Cable Installation       | **Prim / Kruskal (MST)** | ❌ No                      | Undirected            | O(E log V)      | O(V + E)         | Infrastructure cost optimization       | Only finds minimum connection, not paths |
