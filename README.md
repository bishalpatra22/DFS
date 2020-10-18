# DFS
I will try to make a  Java code for DFS algorithm
def dfs(G, v):
    visited = set() # keep visited information away from graph

    def _dfs(v):
        visited.add(v) # mark the node as visited
        if v.is_goal:
            return [':-)'] # return end point of path
        for edge in v.out_edges:
            neighbor = edge.to() # to avoid calling to() several times
            if neighbor not in visited:
                result = _dfs(neighbor)
                if result: # only when successful
                    # we only need 1 success: add current neighbor and exit
                    return [neighbor.label] + result 
                # otherwise, nothing should change to any path: continue

        # don't return anything in case of failure

    # call nested function: the visited and Graph variables are shared
    return _dfs(v) 
