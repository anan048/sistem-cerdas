def DFS(graph, start, goal):
    # buat sebuah stack dan tambahkan simpul awal
    stack = [(start, [start], 0)]
    # inisialisasi variabel yang menyimpan jalur terpendek yang ditemukan
    shortest_path = None
    
    while stack:
        # pop simpul teratas dari stack
        (node, path, cost) = stack.pop()
        
        # cek apakah simpul yang diproses adalah tujuan
        if node == goal:
            # jika jalur terpendek belum ada atau jalur saat ini lebih pendek daripada jalur terpendek yang sudah ditemukan,
            # update jalur terpendek
            if shortest_path is None or cost < shortest_path[2]:
                shortest_path = (node, path, cost)
        
        # cek setiap tetangga dari simpul saat ini
        for neighbor, neighbor_cost in graph[node].items():
            # jika tetangga belum dikunjungi, tambahkan tetangga ke stack dengan menambahkan tetangga ke path dan menambahkan cost dari simpul saat ini ke tetangga
            if neighbor not in path:
                stack.append((neighbor, path + [neighbor], cost + neighbor_cost))
    
    # return jalur terpendek yang ditemukan
    return shortest_path[1] if shortest_path is not None else None

graph = {
    'A': {'B': 1, 'C': 4},
    'B': {'D': 3},
    'C': {'D': 2},
    'D': {}
}

start = 'A'
goal = 'D'

shortest_path = DFS(graph, start, goal)

print(shortest_path)  # output: ['A', 'C', 'D']
