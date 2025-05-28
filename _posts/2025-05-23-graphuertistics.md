---
layout: post
comments: True
title: graph hueristics hw 
description: graph hueristics hw 
categories: ['AP CSA']
courses: {'csa': {'week': 5}}
type: ccc
menu: nav/CSA_Units/csa_unit3_p1.html
author: Anika Bhatnagar
---

## popcorn hack
A robotic mouse on a maze goes the same distance each time, whats the nodes? Is it weighted? 
- its not weighted becasue teh ouse moves teh same distance each time
- the nodes where the mouse is positioned and the edges are where the mouses teaching.

## popcorn hack 2 
Would you use greedy or A star search for teh mouse situation?
- Use a A star graph 

# Multiple Choice
What is the primary difference between Dijkstra’s algorithm and heuristic search methods?
- b) Dijkstra’s guarantees optimal solutions but doesn’t use estimation

Which heuristic function is most appropriate for 4-directional grid movement?
- b) Manhattan distance

# Short Answer
Q: Explain why A is often preferred over Greedy Best-First Search for pathfinding applications.*
A: A* considers both the cost to reach a node (g) and the estimated cost to the goal (h), while Greedy Best-First Search uses only h. This makes A* more balanced and reliable for finding optimal paths.

Q: Calculate the Manhattan distance heuristic for moving from point (2,3) to point (7,1).
A: |7 − 2| + |1 − 3| = 5 + 2 = 7

# Programming Problems

## Problem 1: Compare Dijkstra vs A* on a Grid

This problem compares two pathfinding algorithms, Dijkstra’s and A*, on a grid. The grid is a 2D array where:

- `0` represents walkable space  
- `1` represents an obstacle  
- Movement is allowed in four directions: up, down, left, right  
- Each movement has a cost of 1  

### Java Code

```java
import java.util.*;

class Node implements Comparable<Node> {
    int x, y, cost, priority;

    Node(int x, int y, int cost, int priority) {
        this.x = x;
        this.y = y;
        this.cost = cost;
        this.priority = priority;
    }

    public int compareTo(Node other) {
        return this.priority - other.priority;
    }
}

public class GridPathfinding {

    static int[][] directions = {{1,0}, {-1,0}, {0,1}, {0,-1}};

    public static int dijkstra(int[][] grid, int[] start, int[] goal) {
        int rows = grid.length, cols = grid[0].length;
        boolean[][] visited = new boolean[rows][cols];
        PriorityQueue<Node> pq = new PriorityQueue<>();
        pq.add(new Node(start[0], start[1], 0, 0));

        while (!pq.isEmpty()) {
            Node current = pq.poll();
            if (current.x == goal[0] && current.y == goal[1]) return current.cost;
            if (visited[current.x][current.y]) continue;
            visited[current.x][current.y] = true;

            for (int[] dir : directions) {
                int nx = current.x + dir[0], ny = current.y + dir[1];
                if (nx >= 0 && ny >= 0 && nx < rows && ny < cols && grid[nx][ny] == 0) {
                    pq.add(new Node(nx, ny, current.cost + 1, current.cost + 1));
                }
            }
        }
        return -1;
    }

    public static int astar(int[][] grid, int[] start, int[] goal) {
        int rows = grid.length, cols = grid[0].length;
        boolean[][] visited = new boolean[rows][cols];
        PriorityQueue<Node> pq = new PriorityQueue<>();
        pq.add(new Node(start[0], start[1], 0, heuristic(start, goal)));

        while (!pq.isEmpty()) {
            Node current = pq.poll();
            if (current.x == goal[0] && current.y == goal[1]) return current.cost;
            if (visited[current.x][current.y]) continue;
            visited[current.x][current.y] = true;

            for (int[] dir : directions) {
                int nx = current.x + dir[0], ny = current.y + dir[1];
                if (nx >= 0 && ny >= 0 && nx < rows && ny < cols && grid[nx][ny] == 0) {
                    int newCost = current.cost + 1;
                    int priority = newCost + heuristic(new int[]{nx, ny}, goal);
                    pq.add(new Node(nx, ny, newCost, priority));
                }
            }
        }
        return -1;
    }

    public static int heuristic(int[] a, int[] b) {
        return Math.abs(a[0] - b[0]) + Math.abs(a[1] - b[1]); // Manhattan Distance
    }

    public static void main(String[] args) {
        int[][] grid = {
            {0, 0, 0, 0, 0},
            {0, 1, 1, 0, 0},
            {0, 1, 0, 0, 0},
            {0, 0, 0, 1, 0},
            {0, 0, 0, 0, 0}
        };
        int[] start = {0, 0};
        int[] goal = {4, 4};

        System.out.println("Dijkstra cost: " + dijkstra(grid, start, goal));
        System.out.println("A* cost: " + astar(grid, start, goal));
    }
}

## Problem 2 

public static int terrainAwareHeuristic(int[] current, int[] goal, int[][] terrainGrid) {
    int dx = Math.abs(current[0] - goal[0]);
    int dy = Math.abs(current[1] - goal[1]);

    // Estimate average cost from terrain grid
    int total = 0, count = 0;
    for (int[] row : terrainGrid)
        for (int val : row)
            if (val > 0) { total += val; count++; }

    int avgCost = count == 0 ? 1 : total / count;
    return (dx + dy) * avgCost;
}
