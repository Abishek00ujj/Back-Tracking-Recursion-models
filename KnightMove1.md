## Knights moves

![image](https://github.com/user-attachments/assets/a40bde7f-7b64-4b17-b618-199d194931fc)



```java

import java.util.*;

public class Main {
    static int minSteps = Integer.MAX_VALUE;

    public static void main(String args[]) {
        Scanner sc = new Scanner(System.in);
        int si = sc.nextInt();
        int sj = sc.nextInt();
        int di = sc.nextInt();
        int dj = sc.nextInt();
        int n = 8;
        Set<String> visited = new HashSet<>();
        f(si - 1, sj - 1, di - 1, dj - 1, n, visited, 0);
        System.out.println((minSteps == Integer.MAX_VALUE ? -1 : minSteps));
    }

    public static void f(int i, int j, int di, int dj, int n, Set<String> visited, int steps) {
        if (i == di && j == dj) {
            minSteps = Math.min(minSteps, steps);
            return;
        }
        if (i >= 0 && j >= 0 && i < n && j < n && !visited.contains(i + "," + j)) {
            visited.add(i + "," + j);
            if (steps + 1 < minSteps) {
                f(i+2,j+1,di,dj,n,visited,steps+1);
                f(i+1,j+2,di,dj,n,visited,steps+1);
                f(i-2,j+1,di,dj,n,visited,steps+1);
                f(i+2,j-1,di,dj,n,visited,steps+1);
                f(i-1,j-2,di,dj,n,visited,steps+1);
                f(i-1,j+2,di,dj,n,visited,steps+1);
                f(i+1,j-2,di,dj,n,visited,steps+1);
                f(i-2,j-1,di,dj,n,visited,steps+1);
            }
            visited.remove(i+","+j);
        }
    }
}
```
![image](https://github.com/user-attachments/assets/9c1ce786-f6e1-4b00-b585-c8e864cf110d)


