> 广度优先搜索(breadth-first search)(最短路径算法)
bsf.py
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
