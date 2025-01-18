## Word Puzzle

![image](https://github.com/user-attachments/assets/5023af13-8403-4008-83f6-51d2d200eb0e)


```java

import java.util.*;
public class Main{
    public static void main(String args[])
    {
        Scanner sc=new Scanner(System.in);
        char board[][]={{'A','B','C','I'},{'B','I','C','S'},{'C','D','E','E'}};
        int n=board.length;
        int m=board[0].length;
        int t=sc.nextInt();
        sc.nextLine();
        for(int k=0;k<t;k++)
        {
        boolean path[][]=new boolean[n][m];
          String word=sc.nextLine();
          int f=0;
        for(int i=0;i<n;i++)
        {
            for(int j=0;j<m;j++)
            {
                if(word.charAt(0)==board[i][j])
                {
                    boolean result=f(board,i,j,word,n,m,0,path);
                    if(result)
                    {
                        f=1;
                        System.out.println("True");
                        break;
                    }
                }
            }
        }
        if(f==0)
        {
            System.out.println("False");
        }
       // System.out.println();
        }
    }
       public static boolean f(char board[][],int i,int j,String word,int row,int col,int index,boolean path[][])
    {
        if(index==word.length())
        {
            return true;
        }
        if(i<row && j<col && i>=0 && j>=0 && board[i][j]==word.charAt(index)&& !path[i][j])
        {
        path[i][j]=true;
        if(f(board,i+1,j,word,row,col,index+1,path)||
        f(board,i-1,j,word,row,col,index+1,path)||
        f(board,i,j+1,word,row,col,index+1,path)||
        f(board,i,j-1,word,row,col,index+1,path))
        {
        return true;
        }
        path[i][j]=false;
        return false;
    }
    return false;
  }
}


```
![image](https://github.com/user-attachments/assets/8584fdf4-5020-4de4-b010-0ff50595731b)

