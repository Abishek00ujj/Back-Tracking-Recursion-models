## Subset Sums



# Given a array arr of integers, return the sums of all subsets in the list.  Return the sums in any order.

Examples:

Input: arr[] = [2, 3]
Output: [0, 2, 3, 5]
Explanation: When no elements are taken then Sum = 0. When only 2 is taken then Sum = 2. When only 3 is taken then Sum = 3. When elements 2 and 3 are taken then Sum = 2+3 = 5.
Input: arr[] = [1, 2, 1]
Output: [0, 1, 1, 2, 2, 3, 3, 4]
Explanation: The possible subset sums are 0 (no elements), 1 (either of the 1's), 2 (the element 2), and their combinations.
Input: arr[] = [5, 6, 7]
Output: [0, 5, 6, 7, 11, 12, 13, 18]


``` java
class Solution {
    public ArrayList<Integer> subsetSums(int[] arr)
    {
        ArrayList<Integer> ans=new ArrayList<>();
        f(0,ans,arr,new ArrayList<>());
        return ans;
    }
    public int Sum(ArrayList<Integer> arr)
    {
        int sum=0;
        for(int x:arr)
        {
            sum+=x;
        }
        return sum;
    }
    public void f(int index,ArrayList<Integer> ans,int arr[],ArrayList<Integer> subset)
    {
        if(index==arr.length)
        {
            ans.add(Sum(subset));
            return;
        }
        subset.add(arr[index]);
        f(index+1,ans,arr,subset);
        subset.remove(subset.size()-1);
        f(index+1,ans,arr,subset);
    }
}


```
