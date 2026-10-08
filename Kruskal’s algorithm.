def kruskal(edges, vertices):
    # Sort edges by weight
    edges.sort(key=lambda x: x[2])

    parent = list(range(vertices))

    # Find the parent of a vertex
    def find(x):
        if parent[x] != x:
            parent[x] = find(parent[x])
        return parent[x]

    # Join two sets
    def union(x, y):
        root_x = find(x)
        root_y = find(y)

        if root_x != root_y:
            parent[root_y] = root_x
            return True

        return False

    mst = []
    total_weight = 0

    # Process edges in increasing order
    for u, v, weight in edges:
        if union(u, v):
            mst.append((u, v, weight))
            total_weight += weight

    print("Edge\tWeight")

    for u, v, weight in mst:
        print(u, "-", v, "\t", weight)

    print("Total weight:", total_weight)


# Example graph
edges = [
    (0, 1, 2),
    (0, 3, 6),
    (1, 2, 3),
    (1, 3, 8),
    (1, 4, 5),
    (2, 4, 7),
    (3, 4, 9)
]

vertices = 5

kruskal(edges, vertices)
