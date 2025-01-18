## Denominations

![image](https://github.com/user-attachments/assets/f9de8f38-0f3d-43b1-87a5-583b9f9aa9f7)


```java

import java.util.*;
public class Main{
    public static void main(String args[])
    {
        Scanner sc=new Scanner(System.in);
        int t=sc.nextInt();
        int denominations[]={1000,500,200,100,50,20,10,5,2,1};
        for(int i=0;i<t;i++)
        {
            int amount=sc.nextInt();
            int index=0;
            while(amount>0)
            {
                if(denominations[index]<=amount)
                {
                    amount-=denominations[index];
                    System.out.print(denominations[index]+" ");
                }
                else
                {
                    index++;
                }
            }
            System.out.println();
        }
    }
}


```
![image](https://github.com/user-attachments/assets/4d6fc294-f294-4c3e-b9ba-0d94e455c110)

