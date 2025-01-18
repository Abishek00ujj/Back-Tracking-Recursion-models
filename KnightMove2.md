## KnightMove2

![image](https://github.com/user-attachments/assets/19ad489d-fb21-4746-9480-347c5f49f854)



```java

import java.util.*;
public class Main{
    public static void main(String args[])
    {
        Scanner sc=new Scanner(System.in);
        int n=8;
        char arr[][]=new char[n][n];
        for(int i=0;i<n;i++)
        {
            String x=sc.nextLine();
            x=x.substring(3);
            String m[]=x.split(",");
            for(int j=0;j<n;j++)
            {
                arr[i][j]=m[j].charAt(0);
            }
        }
        int si=0;
        int sj=0,di=0,dj=0;
        for(int i=0;i<n;i++)
        {
            for(int j=0;j<n;j++)
            {
                if(arr[i][j]=='S')
                {
                    si=i;
                    sj=j;
                }
                if(arr[i][j]=='X')
                {
                    di=i;
                    dj=j;
                }
            }
        }
        Set<String> visited=new HashSet<>();
        if(f(si,sj,di,dj,n,arr,visited))
        {
            System.out.println("YES");
        }
        else
        {
            System.out.println("NO");
        }
    }
    public static boolean f(int i,int j,int di,int dj,int n,char arr[][],Set<String> visited)
    {
        if(i==di && j==dj)
        {
            return true;
        }
        if (i >= 0 && j >= 0 && i < n && j < n && !visited.contains(i + "," + j) && arr[i][j]!='1') {
            visited.add(i + "," + j);
          boolean found=f(i+2,j+1,di,dj,n,arr,visited)||
                f(i+1,j+2,di,dj,n,arr,visited)||
                f(i-2,j+1,di,dj,n,arr,visited)||
                f(i+2,j-1,di,dj,n,arr,visited)||
                f(i-1,j-2,di,dj,n,arr,visited)||
                f(i-1,j+2,di,dj,n,arr,visited)||
                f(i+1,j-2,di,dj,n,arr,visited)||
                f(i-2,j-1,di,dj,n,arr,visited);
            visited.remove(i+","+j);
            return found;
        }
        return false;
    }
}
