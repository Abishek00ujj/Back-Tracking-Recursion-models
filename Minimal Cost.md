##
 Minimal Cost

 #
 Problem statement
There is an array of heights corresponding to 'n' stones. You have to reach from stone 1 to stone ‘n’.



From stone 'i', it is possible to reach stones 'i'+1, ‘i’+2… ‘i’+'k' , and the cost incurred will be | Height[i]-Height[j] |, where 'j' is the landing stone.



Return the minimum possible total cost incurred in reaching the stone ‘n’.



Example:
For 'n' = 3 , 'k' = 1, height = {2, 5, 2}.

Answer is 6.

Initially, we are present at stone 1 having height 2. We can only reach stone 2 as ‘k’ is 1. So, cost incurred is |2-5| = 3. Now, we are present at stone 2, we can only reach stone 3 as ‘k’ is 1. So, cost incurred is |5-2| = 3. So, the total cost is 6.
Detailed explanation ( Input/output format, Notes, Images )
Sample Input 1:
4 2
10 40 30 10
Sample Output 1:
40
Explanation of sample output 1:
For ‘n’ = 4, 'k' = 2, height = {10, 40, 30, 10}

Answer is 40.

Initially, we are present at stone 1 having height 10. We can reach stone 3 as ‘k’ is 2. So, cost incurred is |10-30| = 20. 

Now, we are present at stone 3, we can reach stone 4 as ‘k’ is 2. So, cost incurred is |30-10| = 20. So, the total cost is 40. We can show any other path will lead to greater cost.
Sample Input 2:
5 3
10 40 50 20 60
Sample Output 2:
50
Constraints:
1 <= n <= 10^4
1 <= k <= 100
1 <= height[i] <= 10^4
Time Limit: 1 sec

```java
import java.util.Arrays;

public class Solution {
    public static int f(int index,int k,int height[],int dp[])
    {
        if(index==0) return 0;

        if(dp[index]!=-1) return dp[index];
        int minSteps=Integer.MAX_VALUE;
        for(int i=1;i<=k;i++)
        {
            if(index-i>=0)
            {
                int jump=Math.abs(height[index-i]-height[index])+f(index-i,k,height,dp);
                minSteps=Math.min(minSteps,jump);
            }
        }
        return dp[index]=minSteps;
    }
    public static int minimizeCost(int n, int k, int []height){
        int dp[]=new int[n+1];
        Arrays.fill(dp,-1);
        return f(n-1,k,height,dp);
    }
}
```
![image](https://github.com/user-attachments/assets/47f46f5b-b7ef-4f29-a9ec-2aaaf2fb8d2a)


