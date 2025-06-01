# Ex 6(D) Travelling Salesman Problem
## DATE:  10.05.2025
## AIM:
To write a C Program to implement Travelling Salesman Problem for finding shortest path.
## Algorithm

1.Read the number of cities and their cost matrix; initialize all cities as unvisited.

2.Start from city 0, mark it visited, and print it.

3.Find the nearest unvisited city from the current city using the least-cost criteria.

4.Add the travel cost to the total cost.

5.Move to the next city and repeat until all cities are visited.

6.Return to the starting city and add the return cost.

7.Print the total minimum cost of the completed route.

## Program:
```
/*
Program to implement Travelling Salesman Problem for finding shortest path
Developed by: Shree Lekha.S
RegisterNumber: 212223110052
*/

#include<stdio.h>
int a[10][10],visited[10],n,cost=0;

void get()
{
	int i,j;
		scanf("%d",&n);
	for(i=0;i < n;i++)
	{
			for( j=0;j < n;j++)
			scanf("%d",&a[i][j]);
		visited[i]=0;
	}
	}

void mincost(int city)
{
	int ncity;
	int least(int);
	visited[city]=1;	
	printf("%d -->",city+1);
	ncity=least(city);
	if(ncity==999)
	{
		ncity=0;
		printf("%d",ncity+1);
		cost+=a[city][ncity];
		return;
	}
	mincost(ncity);
}

int least(int c)
{
	int i,nc=999;
	int min=999,kmin;
	for(i=0;i < n;i++)
	{
		if((a[c][i]!=0)&&(visited[i]==0))
			if(a[c][i] < min)
			{
				min=a[i][0]+a[c][i];
				kmin=a[c][i];
				nc=i;
			}
	}
	if(min!=999)
		cost+=kmin;
	return nc;
}

void put()
{
	printf("\n\nMinimum cost:%d",cost);
}

int main()
{
	get();
	mincost(0);
	put();
	return 0;
	}
```

## Output:
![image](https://github.com/user-attachments/assets/a5e17185-c045-446d-8b86-a9dcbbd82532)



## Result:
Thus, the C program to implement Travelling Salesman Problem for finding shortest path is implemented successfully.
