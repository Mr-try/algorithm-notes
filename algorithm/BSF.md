> 广度优先搜索(breadth-first search)(最短路径算法)

- 代码
```
    def person_is_seller(name):
        ###
        ###
        ###
    def search(name):
        # 创建一个队列
        search_queue = deque()
        # 将离我最近的点加入队列中
        search_queue += graph[name]
        # 用于记录检查过的人
        searched = []
        # 只要队列不为空
        while search_queue:
            # 就取出其中的第一个人
            person = search_queue.popleft()
            # 只有当这个人没有检查过时才检查
            if not person in searched:
                # 是芒果经销商
                if person_is_seller(person):
                    print person + "is a mango seller"
                    return true
                # 如果不是芒果经销商，将这个人的朋友加入搜索队列，并将此人加入已经搜索的数组中
                else:
                    search_queue += graph[person]
                    searched.append(person)
        return false
    search("myself")

```
- 运行时间
> 如果你在你的人际关系网中搜索芒果经销商，就意味着你将沿着每条边前行(记住，边是从一个人到另一个人的箭头或连接)，因此
  运行事件至少为O(边数)。
  同时又使用了一个队列，其中包含要检查的每个人。将一个人添加到队列需要的时间是固定的，为O(1)，因此对每个人都这样操作
  的需要的总时间为O(人数)，所以，广度优先搜索的运行时间为O(人数+边数)，记做O(V+E)，V为顶点数，E为边数

- 小结
    - 广度优先搜索指出是否有从A到B的路径
    - 如果有，则找出最短路径
    - 面临类似于寻找最短路径的问题时，可以尝试使用图来建立模型，再使用官渡优先搜索来解决问题