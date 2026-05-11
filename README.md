# ExpNo 2 : Implement Depth First Search Traversal of a Graph

# Name: NITHISH S
# Register Number: 212224240105

## Aim:
To Implement Depth First Search Traversal of a Graph using Python 3.

## Theory:
Depth First Traversal (or DFS) for a graph is like Depth First Traversal of a tree. The only catch here is that, unlike trees, graphs may contain cycles (a node may be visited twice). Use a Boolean visited array to avoid processing a node more than once. A graph can have more than one DFS traversal. Depth-first search is an algorithm for traversing or searching trees or graph data structures. The algorithm starts at the root node (selecting some arbitrary node as the root node in the case of a graph) and explores as far as possible along each branch before backtracking. Step 1: Initially, stack and visited arrays are empty.

<img width="825" height="413" alt="277147664-640b3c6f-3ac1-49a2-a955-68da9a71f446" src="https://github.com/user-attachments/assets/071c8a4b-6cb9-4b19-934a-68d57e7772bc" />


Queue and visited arrays are empty initially. Stack and visited arrays are empty initially. Step 2: Visit 0 and put its adjacent nodes which are not visited yet into the stack. 

<img width="725" height="363" alt="277147583-86dcf7d9-1f9d-49b0-a821-5976a6e77606" src="https://github.com/user-attachments/assets/96609f8b-4955-4fc4-a15a-307977c86730" />


Visit node 0 and put its adjacent nodes (1, 2, 3) into the stack Visit node 0 and put its adjacent nodes (1, 2, 3) into the stack

Step 3: Now, Node 1 at the top of the stack, so visit node 1 and pop it from the stack and put all of its adjacent nodes which are not visited in the stack. 

<img width="690" height="345" alt="277147597-e6017942-08b1-4742-87ad-c97eb97bf985" src="https://github.com/user-attachments/assets/cb44b796-fc55-40af-b741-e2d07ca3b6dd" />


Visit node 1 Visit node 1

Step 4: Now, Node 2 at the top of the stack, so visit node 2 and pop it from the stack and put all of its adjacent nodes which are not visited (i.e, 3, 4) in the stack. 

<img width="831" height="416" alt="277147603-6e6d123c-60ae-4f9c-a27c-c4fc7e57d57c" src="https://github.com/user-attachments/assets/69b4b130-d1d3-43f4-bbff-8f8b381678e3" />


Visit node 2 and put its unvisited adjacent nodes (3, 4) into the stack Visit node 2 and put its unvisited adjacent nodes (3, 4) into the stack

Step 5: Now, Node 4 at the top of the stack, so visit node 4 and pop it from the stack and put all of its adjacent nodes which are not visited in the stack. 

<img width="841" height="421" alt="277147620-20b76a05-5668-4da5-8189-e10fb1bb7238" src="https://github.com/user-attachments/assets/8c39447e-53c4-4d38-8cb5-e41222a52088" />


Visit node 4 Visit node 4

Step 6: Now, Node 3 at the top of the stack, so visit node 3 and pop it from the stack and put all of its adjacent nodes which are not visited in the stack.

<img width="1031" height="516" alt="277147623-3b88f04a-7846-4f75-89b4-22bbd5b48e52" src="https://github.com/user-attachments/assets/8882f14b-c101-4b8e-9c7e-a81beb437f75" />


Visit node 3 Visit node 3

Now, the Stack becomes empty, which means we have visited all the nodes, and our DFS traversal ends.

## Algorithm:

1.Construct a Graph with Nodes and Edges

2.Depth First Search Uses Stack and Recursion

3.Insert a START node to the STACK

4.Find its Successors Or neighbors and Check whether the node is visited or not

5.If Not Visited, add it to the STACK. Else Call The Function Again Until No more nodes needs to be visited.


Program:
```
from collections import defaultdict
def dfs(graph,start,visited,path):
    path.append(start)
    visited[start]=True
    for neighbour in graph[start]:
       if visited[neighbour]==False:
            dfs(graph,neighbour,visited,path)
            visited[neighbour]=True
    return path
graph=defaultdict(list)
n,e=map(int,input().split())
for i in range(e):
    u,v=map(str,input().split(' '))
    graph[u].append(v)
    graph[v].append(u)
start='A'
visited=defaultdict(bool)
path=[]
traversedpath=dfs(graph,start,visited,path)
print(traversedpath)
```

## Sample Input

8 9

A B

A C

B E

C D

B D

C G

D F

G F

F H


## Sample Output

['A', 'B', 'E', 'D', 'C', 'G', 'F', 'H']

## Sample Input

5 5

0 1

0 2

0 3

2 3

2 4

## Sample Output

['0', '1', '2', '3', '4']


## Result:

Thus,a Graph was constructed and implementation of Depth First Search for the same graph was done successfully.
