
# EX 2D Pattern Matching using Naive Approach.
## DATE: 01/08/2026
## AIM:
To write a Java program to for given constraints.
Given text string with length n and a pattern with length m, the task is to prints all occurrences of pattern in text.
Note: You may assume that n > m.

Examples: 

Input:  text = "THIS IS A TEST TEXT", pattern = "TEST"
Output: Pattern found at index 10

Input:  text =  "AABAACAADAABAABA", pattern = "AABA"
Output: Pattern found at index 0, Pattern found at index 9, Pattern found at index 12

## Algorithm

1. **Start**
2. Read the `text` and `pattern` strings and determine their lengths `n` and `m`.
3. Traverse the text from index `0` to `n - m`.
4. For each position, compare the pattern characters with the corresponding text characters.
5. Stop the comparison when a mismatch is found.
6. If all `m` characters match, print the starting index of the pattern.
7. Continue the process for all possible starting positions in the text.
8. **End**

## Program:
```
/*
Program to implement Reverse a String
Developed by: Vishwaraj G
Register Number: 212223220125
*/
import java.util.Scanner;

public class NaivePatternSearch {
    //Type code here....
    public static void search(String text,String pattern)
    {
        int n=text.length();
        int m=pattern.length();
        for(int i=0;i<=n-m;i++)
        {
            int j;
            for(j=0;j<m;j++)
            {
                if(text.charAt(i+j)!=pattern.charAt(j))
                {
                    break;
                }
            }
            if(j==m) System.out.println("Pattern found at index "+i);
        }
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Taking input from the user
        //System.out.print("Enter the text: ");
        String text = scanner.nextLine();

        //System.out.print("Enter the pattern: ");
        String pattern = scanner.nextLine();

        // Search for pattern in the text
        search(text, pattern);

        scanner.close();
    }
}
```

## Output:
<img width="494" height="171" alt="image" src="https://github.com/user-attachments/assets/cb6c707a-074a-4e6c-a2a1-faa6a5be7d1e" />



## Result:
The program successfully implemented and the expected output is verified.
