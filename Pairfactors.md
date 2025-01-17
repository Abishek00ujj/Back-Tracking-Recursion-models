
## Pair Factors

![image](https://github.com/user-attachments/assets/5f103edb-081d-4cdf-947d-02624f2d8900)

```java
import java.util.*;
public class Main{
    public static void main(String args[])
    {
        Scanner sc=new Scanner(System.in);
        long n=sc.nextLong();
        long ans=Long.MAX_VALUE;
        long sum=0;
        long dummy=n;
        for(long i=1;i*i<=n;i++)
        {
            if(n%i==0)
            {
                long A=i;
                long B=n/i;
                sum=(A+B);
                ans=Math.min(sum,ans);
            }
        }
        System.out.println(ans);
    }
}

