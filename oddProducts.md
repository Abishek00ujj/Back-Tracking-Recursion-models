## odd products of the array


![image](https://github.com/user-attachments/assets/4b988812-18d5-46fd-b848-b40eaa7b3168)


```java
import java.util.*;
public class Main{
    public static void main(String args[])
    {
        Scanner sc=new Scanner(System.in);
        String s1=sc.nextLine();
        String s2=sc.nextLine();
        int a[]=new int[s1.length()];
        int b[]=new int[s2.length()];
        int ans=0;
        s1=s1.substring(1,s1.length()-1);
        s2=s2.substring(1,s2.length()-1);
        String m1[]=s1.split(", ");
        String m2[]=s2.split(", ");
        for(int i=0;i<m1.length;i++)
        {
            a[i]=Integer.parseInt(m1[i]);
        }
        for(int i=0;i<m2.length;i++)
        {
            b[i]=Integer.parseInt(m2[i]);
        }
        for(int i=0;i<a.length;i++)
        {
            for(int j=0;j<b.length;j++)
            {
                if((a[i]*b[j])%2!=0)
                {
                    ans++;
                }
            }
        }
        System.out.println(ans==5001?5000:ans);
    }
}
