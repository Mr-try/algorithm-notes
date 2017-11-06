>  广度优先搜索找出的是段数最少的路径，而狄克斯特拉算法(Dijkstra's algorithm)则是找出最快的路径
- 代码
```
    def find_lowest_cost_node(costs):
        lowest_cost = float('inf')
        lowest_cost_node = None
        for node in costs:
            cost = cists[node]
            if cost < lowest_cost and node not in processed:
                lowest_cost = cost
                lowest_cost_node = node
            return lowest_cost_node
    # 在未处理的节点中找出开销最小的点
    node = find_lowest_cost_node(costs)
    while node is not Node:
        cost = costs[node]
        neighbors = graph[node]
        # 遍历当前节点的所有邻居
        for n in neighbors.keys():
            new_cost = cost + neighbors[n]
            # 如果经当前节点前往该邻居更近
            if costs[n] > new_cost:
                # 就更新该邻居的开心
                costs[n] = new_cost
                # 同时将该邻居的父节点设置为当前节点
                parents[n] = node
        # 将当前节点标记为处理过
        processed.append(node)
        # 找出接下来要处理的节点，并循环
        node = find_lowest_cost_node(costs)
```