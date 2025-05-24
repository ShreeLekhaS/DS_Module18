# Ex 6(C) Dijkstra’s Algorithm
## DATE:
## AIM:
To write a C Program to implement Dijkstra's Algorithm to find the shortest path

## Algorithm

1.Start the program and include necessary libraries (stdio.h).

2.Define constants for infinity and maximum graph size.

3.Read the number of vertices n and the adjacency matrix G.

4.Read the starting node startnode.

5.Initialize the cost matrix by replacing zero edges with infinity.

6.Initialize distance, predecessor, and visited arrays; set distance to startnode as 0.

7.Mark the startnode as visited and set count of processed nodes to 1.

8.While not all nodes are processed, select the unvisited node with the smallest distance.

9.Update distances and predecessors for adjacent unvisited nodes if a shorter path is found.

10.After processing, print the shortest distances and paths from the startnode to all other nodes, then end the program.

## Program:
```
/*
Program to implement Dijkstra's Algorithm 
Developed by: Shree Lekha.S
RegisterNumber: 212223110052 
*/

#include<stdio.h>
#define INFINITY 9999
#define MAX 10
 
void dijkstra(int G[MAX][MAX],int n,int startnode);
 
int main()
{
int G[MAX][MAX],i,j,n,u;
scanf("%d",&n);
for(i=0;i<n;i++)
for(j=0;j<n;j++)
scanf("%d",&G[i][j]);
scanf("%d",&u);
dijkstra(G,n,u);
return 0;
}
 
void dijkstra(int G[MAX][MAX],int n,int startnode)
{
 
int cost[MAX][MAX],distance[MAX],pred[MAX];
int visited[MAX],count,mindistance,nextnode,i,j;
//pred[] stores the predecessor of each node
//count gives the number of nodes seen so far
//create the cost matrix
for(i=0;i<n;i++)
for(j=0;j<n;j++)
if(G[i][j]==0)
cost[i][j]=INFINITY;
else
cost[i][j]=G[i][j];
//initialize pred[],distance[] and visited[]
for(i=0;i<n;i++)
{
distance[i]=cost[startnode][i];
pred[i]=startnode;
visited[i]=0;
}
distance[startnode]=0;
visited[startnode]=1;
count=1;
while(count<n-1)
{
mindistance=INFINITY;
//nextnode gives the node at minimum distance
for(i=0;i<n;i++)
if(distance[i]<mindistance&&!visited[i])
{
mindistance=distance[i];
nextnode=i;
}
//check if a better path exists through nextnode
visited[nextnode]=1;
for(i=0;i<n;i++)
if(!visited[i])
if(mindistance+cost[nextnode][i]<distance[i])
{
distance[i]=mindistance+cost[nextnode][i];
pred[i]=nextnode;
}
count++;
}
 
//print the path and distance of each node
for(i=0;i<n;i++)
if(i!=startnode)
{
printf("Distance of node%d=%d\n",i,distance[i]);
printf("Path=%d",i);
j=i;
do
{
j=pred[j];
printf("<-%d",j);
}while(j!=startnode);
}
}

```

## Output:

![image](https://github.com/user-attachments/assets/f8ec82ff-d006-4f67-825b-7519cdeb7ef5)


## Result:
Thus, the Program to implement Dijkstra's Algorithm to find the shortest path is implemented successfully.
