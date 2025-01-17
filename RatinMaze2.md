## Rat in Maze 2

![image](https://github.com/user-attachments/assets/4d1f019a-465d-4bc5-a825-3ff2262997e4)


```java
import java.util.*;
public class Main{
    public static boolean f(int i,int j,int n,int arr[][],int solution[][])
    {
        if(i==n-1 && j==n-1)
        {
            if(arr[i][j]==0)
            {
                solution[i][j]=1;
                return true;
            }
            return false;
        }
        if(i>=0 && j>=0 && i<=n-1 && j<=n-1 && solution[i][j]==0 && arr[i][j]==0)
        {
            solution[i][j]=1;
            if(f(i+1,j,n,arr,solution))
            {
                return true;
            }
            if(f(i,j+1,n,arr,solution))
            {
                return true;
            }  
            if(f(i-1,j,n,arr,solution))
            {
                return true;
            }    
            if(f(i,j-1,n,arr,solution))
            {
                return true;
            }
            solution[i][j]=0;
            return false;
        }
        return false;
    }
    public static void main(String args[])
    {
        Scanner sc=new Scanner(System.in);
        int n=sc.nextInt();
        int arr[][]=new int[n][n];
        for(int i=0;i<n;i++)
        {
            for(int j=0;j<n;j++)
            {
                arr[i][j]=sc.nextInt();
            }
        }
        int solution[][]=new int[n][n];
        if(f(0,0,n,arr,solution))
        {
            for(int i=0;i<n;i++)
            {
                for(int j=0;j<n;j++)
                {
                    System.out.print(solution[i][j]+" ");
                }
                System.out.println();
            }
        }
        else
        {
            System.out.println("No solution exists");
        }
    }
}
![image](https://github.com/user-attachments/assets/1d2894eb-c25c-49d2-957a-fa4657b17a61)


