## 120. Triangle

# Given a triangle array, return the minimum path sum from top to bottom. For each step, you may move to an adjacent number of the row below. More formally, if you are on index i on the current row, you may move to either index i or index i + 1 on the next row.

# Example 1:

Input: triangle = [[2],[3,4],[6,5,7],[4,1,8,3]]
Output: 11
Explanation: The triangle looks like:
   2
  3 4
 6 5 7
4 1 8 3
The minimum path sum from top to bottom is 2 + 3 + 5 + 1 = 11 (underlined above).
Example 2:

Input: triangle = [[-10]]
Output: -10

# Constraints:

1 <= triangle.length <= 200
triangle[0].length == 1
triangle[i].length == triangle[i - 1].length + 1
-104 <= triangle[i][j] <= 104
 

Follow up: Could you do this using only O(n) extra space, where n is the total number of rows in the triangle?


``` java
class Solution {
    public int minimumTotal(List<List<Integer>> triangle) {
        int n=triangle.size()-1;
        int dp[][]=new int[n+1][n+1];
        for(int row[]:dp)
        {
            Arrays.fill(row,-1);
        }
        return f(0,0,n,triangle,dp);
    }

    public int f(int i, int j, int n, List<List<Integer>> triangle, int dp[][]) {
        if (i == n)  return triangle.get(i).get(j);
        if(i<0 || j<0 || i>n || j>n) return (int)1e8;
        if(dp[i][j]!=-1) return dp[i][j];
        int left=triangle.get(i).get(j)+f(i+1,j,n,triangle,dp);
        int right=triangle.get(i).get(j)+f(i+1,j+1,n,triangle,dp);
        return dp[i][j]=Math.min(left,right);
    }
}
```

![image](https://github.com/user-attachments/assets/7c040d99-0c08-4a35-89f4-747baab8bc01)

