## Subset Sum Problem

# Given an array of positive integers arr[] and a value target, determine if there is a subset of the given array with sum equal to given target. 

# Examples:

Input: arr[] = [3, 34, 4, 12, 5, 2], target = 9
Output: true 
Explanation: Here there exists a subset with target sum = 9, 4+3+2 = 9.
Input: arr[] = [3, 34, 4, 12, 5, 2], target = 30
Output: false
Explanation: There is no subset with target sum 30.
Input: arr[] = [1, 2, 3], sum = 6
Output: true
Explanation: The entire array can be taken as a subset, giving 1 + 2 + 3 = 6.
Constraints:
1 <= arr.size() <= 200
1<= arr[i] <= 200
1<= sum <= 4 x 104

``` java

class Solution {

    static Boolean isSubsetSum(int arr[], int target) {
        int dp[][]=new int[arr.length+1][target+1];
        for(int row[]:dp)
        {
            Arrays.fill(row,-1);
        }
        return f(0,arr.length-1,target,dp,arr);
    }
    static boolean f(int index,int n,int target,int dp[][],int arr[])
    {
        if(target==0)  return true;
        if(index==n)
        {
            if(arr[index]-target==0)
            {
                return true;
            }
            return false;
        }
        if(dp[index][target]!=-1)  return dp[index][target]==1?true:false;
        boolean pick=false;
        boolean notpick=false;
        if(arr[index]<=target)
        {
            pick=f(index+1,n,target-arr[index],dp,arr);
        }
        notpick=f(index+1,n,target,dp,arr);
        dp[index][target]=(pick||notpick)?1:0;
        return dp[index][target]==1;
    }
}

```
![image](https://github.com/user-attachments/assets/ff6d7924-2ec2-4629-95b9-7caf8b8d8ea8)
