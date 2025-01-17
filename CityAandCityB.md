## City A and City B

![Screenshot 2025-01-17 205921](https://github.com/user-attachments/assets/95528258-888c-4b4c-88b3-38202934f71b)


```java

import java.util.*;
public class Main{
    public static void main(String args[])
    {
        Scanner sc=new Scanner(System.in);
        int day=0;
        int S=sc.nextInt();
        int X=sc.nextInt();
        int N=sc.nextInt();
        LinkedHashMap<Integer,Integer> exceptions=new LinkedHashMap<>();
        for(int i=0;i<N;i++)
        {
            int T=sc.nextInt();
            int M=sc.nextInt();
            exceptions.put(T,M);
        }
        int dummy=S;
        int ans=0;
        while(S>=0)
        {
            if(exceptions.containsKey(day))
            {
                ans++;
                S-=exceptions.get(day);
            }
            else
            {
                ans++;
                S-=X;
            }
            day++;
        }
        System.out.println(ans-1);
    }
}

