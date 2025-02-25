``` java
import java.util.ArrayList;
import java.util.Scanner;

public class Main
{
    public static void main(String[] args)
    {
        Scanner sc=new Scanner(System.in);
        int n=2;
        int arr[]={2,2};
        int k=0;

        ArrayList<String> subset=new ArrayList<>();
        subset.add(String.valueOf(arr[0]));

        ArrayList<ArrayList<String>> ans=new ArrayList<>();
        f(1,n,arr,subset,ans,arr[0],k);
        System.out.println(ans);
    }

    public static void f(int index,int n,int arr[],ArrayList<String> subset,ArrayList<ArrayList<String>> ans,int sum,int target)
    {
        if(index==n)
        {
            System.out.println(sum);

                 if(target==sum)
                 {
                     ans.add(new ArrayList<>(subset));
                 }

            return;
        }
        if(subset.size()>(n+(n-1))) return;
        if(target>=sum-arr[index])
        {
            subset.add("+");
            subset.add(String.valueOf(arr[index]));
            f(index+1,n,arr,subset,ans,sum+arr[index],target);
            subset.remove(subset.size()-2);
            subset.remove(subset.size()-1);
        }

        if(target>=sum-arr[index])
        {
            subset.add("-");
            subset.add(String.valueOf(arr[index]));
            f(index+1,n,arr,subset,ans,sum-arr[index],target);
            subset.remove(subset.size()-2);
            subset.remove(subset.size()-1);
        }
        if(target>=sum-arr[index])
        {
            subset.add("/");
            subset.add(String.valueOf(arr[index]));
            f(index+1,n,arr,subset,ans,sum/arr[index],target);
            subset.remove(subset.size()-2);
            subset.remove(subset.size()-1);
        }
        if(target>=sum-arr[index])
        {
            subset.add("*");
            subset.add(String.valueOf(arr[index]));
            f(index+1,n,arr,subset,ans,sum*arr[index],target);
            subset.remove(subset.size()-2);
            subset.remove(subset.size()-1);
        }
    }

}
