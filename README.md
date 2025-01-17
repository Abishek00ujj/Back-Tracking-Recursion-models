# Recursion-models
#question
![image](https://github.com/user-attachments/assets/e9fd59ae-464a-4b4b-ace3-bdfe10173884)


#code
```
import java.util.*;
public class Main{
    static int count=0;
    public static void f(String s,ArrayList<Character> ds,ArrayList<List<Character>> ans,boolean freq[])
    {
        if(ds.size()==s.length())
        {
            count++;
            ans.add(new ArrayList<>(ds));
            return;
        }
        for(int i=0;i<s.length();i++)
        {
            if(!freq[i])
            {
                freq[i]=true;
                ds.add(s.charAt(i));
                f(s,ds,ans,freq);
                ds.remove(ds.size()-1);
                f(s,ds,ans,freq);
                freq[i]=false;
            }
        }
   }
    public static void main(String args[])
    {
        Scanner sc=new Scanner(System.in);
        String s=sc.nextLine();
        ArrayList<List<Character>> ans=new ArrayList<>();
        ArrayList<Character> ds=new ArrayList<>();
        boolean freq[]=new boolean[s.length()];
        f(s,ds,ans,freq);
        // Collections.sort(ans);
         Collections.sort(ans, (list1, list2) -> {
            for (int i = 0; i < list1.size(); i++) {
                if (list1.get(i) != list2.get(i)) {
                    return list1.get(i) - list2.get(i);
                }
            }
            return 0;
        });
        System.out.println(count);
        for(List<Character> x:ans)
        {
            for(char c:x)
            {
                System.out.print(c);
            }
            System.out.println();
        }
    }
}
