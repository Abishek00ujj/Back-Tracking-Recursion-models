#Claiming stairs

![image](https://github.com/user-attachments/assets/29a1bcdb-255a-4ec8-90ba-b42a2e7cc568)


```
import java.util.*;
public class Main{
    public static void main(String args[])
    {
        Scanner sc=new Scanner(System.in);
        int n=sc.nextInt();
        System.out.println(f(n));
    }
    public static int f(int x)
    {
        int f1=0;
        int f2=1;
        int sum=0;
        for(int i=1;i<=x;i++)
        {
            sum=f1+f2;
            f1=f2;
            f2=sum;
        }
        return sum;
    }
}
