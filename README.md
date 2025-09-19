# 🧭 Guide Me — Route Planner & Booking (WinForms)

![C++](https://img.shields.io/badge/C%2B%2B-Algorithms-critical?logo=cplusplus)
![WinForms](https://img.shields.io/badge/Windows%20Forms-GUI-lightgrey)
![Algorithms](https://img.shields.io/badge/Algorithms-BFS%2FDFS%2FDijkstra-orange)
![Graph](https://img.shields.io/badge/Data%20Structure-Graph-darkgreen)
![Database](https://img.shields.io/badge/Database-SQLite%2FSQLServer-yellow)

> **Guide Me** is a desktop route planning and booking application built with **C# .NET (WinForms)**.  
> It supports two roles: **User** (search, view routes, book) and **Admin** (add/edit/delete routes, update fares).  
> The system models transport connections as a **graph** and provides algorithmic search (BFS/DFS/Dijkstra) and booking flows.  
> Core algorithms (Graph Traversal, Dijkstra) can also be implemented/tested in **C++** for performance.

---

## 🚀 Key Features

### For Users
- Search available routes between two cities (origin → destination).
- Choose search mode:
  - **All routes** / **Complete graph check**
  - **Path search (BFS / DFS)** — list of reachable nodes / paths
  - **Shortest-path (Dijkstra)** — cheapest/shortest path if weighted
- View route details: transport type, duration, fare, provider.
- Book a route (simple booking flow with local persistence).
- View booking history and cancel bookings.

### For Admins
- Add new routes (from city A to city B) with transport type, duration, price, seats.
- Edit existing route properties (price, time, availability).
- Delete routes (remove edges from the graph).
- Manage providers and route categories.
- Export/import route data

### Under the hood
- Routes represented as a **graph**: nodes = cities, edges = connections.
- Graph supports:
  - Unweighted traversal (**BFS / DFS**).
  - Weighted shortest path (**Dijkstra**).
  - Graph completeness check.
- Simple authentication for two roles (User / Admin).
- Windows Forms GUI: Login, Search, Routes, Booking, Admin dashboard.

---

## 🎯 User Flows (UX)

### User: Search & Book
1. Login as **User**.
2. Enter **Origin** and **Destination**.
3. Choose search mode:
   - **All Routes** — list all available direct and chained routes.
   - **BFS / DFS** — explore reachable nodes or list paths.
   - **Dijkstra** — find minimum-cost or shortest-time route.
4. View route options.  
5. Click **Book** → confirm details → record saved.  
6. Check booking history or cancel.

### Admin: Manage Network
1. Login as **Admin**.
2. Add a new route with details (origin, destination, type, price).
3. Edit or delete routes.
4. Import/export route data 

---

## 🔎 Algorithms

- **Graph Representation** → adjacency list (`Dictionary<int, List<Edge>>` in C++ or `unordered_map<int, vector<Edge>>` in C++).  
- **BFS/DFS** → unweighted traversal.  
- **Dijkstra** → priority queue (min-heap) for weighted shortest path.  
- **Completeness Check** → verify each node has edges to `n-1` nodes.  
- **Booking Logic** → decrement seats, prevent overbooking, log transaction.
