# Ex 6(B) Kruskal’s Algorithm
## DATE:
## AIM:
To write a C program to implement Kruskal's Algorithm for finding minimum cost

## Algorithm

1.Start the program.

2.Include necessary libraries like #include <stdio.h>.

3.Define a function to return the priority of an operator (e.g., priority(char op)).

4.Use if-else statements to assign higher values to operators like ^, *, /, +, and -.

5.Return a priority value based on the operator (e.g., ^ = 3, *// = 2, +/- = 1).

6.Call the function from main by taking an operator input from the user.

7.Print the priority of the entered operator and end the program.

## Program:
```
/*
Program to implement Kruskal's Algorithm
Developed by: Shree Lekha.S
RegisterNumber: 212223110052
*/

    #include <stdio.h>
    #include <stdlib.h>
    int i,j,k,a,b,u,v,n,ne=1;
    int min,mincost=0,cost[9][9],parent[9];
    int find(int);
    int uni(int,int);
    int main()
    {
          scanf("%d",&n);
          for(i=1;i<=n;i++)
     {
     for(j=1;j<=n;j++)
     {
     scanf("%d",&cost[i][j]);
     if(cost[i][j]==0)
     cost[i][j]=999;
     }
     }
         while(ne < n)
     {
     for(i=1,min=999;i<=n;i++)
     {
     for(j=1;j <= n;j++)
     {
     if(cost[i][j] < min)
     {
     min=cost[i][j];
     a=u=i;
     b=v=j;
     }
     }
     }
     u=find(u);
     v=find(v);
     if(uni(u,v))
     {
     printf("%d edge (%d,%d) =%d\n",ne++,a,b,min);
     mincost +=min;
     }
     cost[a][b]=cost[b][a]=999;
     }
     printf("Minimum cost = %d\n",mincost);
     return 0;
       }
    int find(int i)
    {
     while(parent[i])
     i=parent[i];
     return i;
    }
    int uni(int i,int j)
    {
     if(i!=j)
     {
     parent[j]=i;
     return 1;
     }
     return 0;
    }

```

## Output:

![image](https://github.com/user-attachments/assets/72a0dc13-e6ae-4b9c-9ff1-5423aecef1c9)


## Result:
Thus, the C program to implement Kruskal's Algorithm for finding minimum cost is implemented successfully.
