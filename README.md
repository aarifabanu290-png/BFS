# BFS
Data Structure Practicle program
22.Python Program for BFS and

from collections import deque

graph = {
    'A': ['B', 'C'],
    'B': ['D', 'E'],
    'C': ['F'],
    'D': [],
    'E': [],
    'F': []
}

visited = set()

def bfs(graph, start):
    visited = []
    queue = deque([start])

    while queue:
        vertex = queue.popleft()
        if vertex not in visited:
            print(vertex),
            visited.append(vertex)
            queue.extend(graph[vertex])

def dfs(graph, start, visited=None):
    if visited is None:
        visited = set()

    visited.add(start)
    print(start),

    for next in graph[start]:
        if next not in visited:
            dfs(graph, next, visited)

print("BFS Traversal:")
bfs(graph, 'A')

print("\nDFS Traversal:")
dfs(graph, 'A')

Output :
BFS Traversal:
A B C D E F

DFS Traversal:
A B D E C F
