
# EX 2A Assign Cookies using Greedy Algorithm. 
## DATE: 25/07/2026
## AIM:
To Write a Java program for the following Constraints.
Assume you are an awesome parent and want to give your children some cookies. But, you should give each child at most one cookie.

Each child i has a greed factor g[i], which is the minimum size of a cookie that the child will be content with; and each cookie j has a size s[j]. If s[j] >= g[i], we can assign the cookie j to the child i, and the child i will be content. Your goal is to maximise the number of your content children and output the maximum number.

## Algorithm

1. **Start**
2. Read the greed factors of the children and the sizes of the available cookies.
3. Sort both arrays in ascending order.
4. Initialize pointers `i = 0` for children and `j = 0` for cookies.
5. Compare `g[i]` with `s[j]`; if the cookie satisfies the child's greed, increment `i` to count the child as content.
6. Increment `j` after considering each cookie.
7. Continue until all children or cookies are processed.
8. Return and display the number of content children.
9. **End**

## Program:
```
/*
Program to implement Reverse a String
Developed by: Vishwaraj G
Register Number: 212223220125
*/
import java.util.*;

public class AssignCookies {
    
    public static int findContentChildren(int[] g, int[] s) {
        // Type Your Logic Here.
        Arrays.sort(g);
        Arrays.sort(s);
        int i=0,j=0;
        while(i<g.length && j<s.length)
        {
            if(g[i]<=s[j])
            {
                i++;
            }
            j++;
        }
        return i;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] g = new int[n];
        for (int i = 0; i < n; i++) g[i] = sc.nextInt();
        int m = sc.nextInt();
        int[] s = new int[m];
        for (int i = 0; i < m; i++) s[i] = sc.nextInt();
        System.out.println(findContentChildren(g, s));
    }
}
```

## Output:

<img width="308" height="200" alt="image" src="https://github.com/user-attachments/assets/8467b0b3-8d41-458d-b724-500d72dee852" />


## Result:
The program successfully print all the numbers from 1 to N. 
