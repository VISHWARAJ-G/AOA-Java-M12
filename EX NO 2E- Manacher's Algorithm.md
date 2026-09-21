
# EX 2E Pattern Matching using KMP Algorithm.
## DATE: 04/08/2026
## AIM:
To write a Java program for the following constraints.
Longest Palindromic Substring
Given a string s, return the longest palindromic substring in s.
using Manacher's Algorithm

## Algorithm

1. **Start**
2. Read the string `s` and initialize `longest` as an empty string.
3. Generate every possible substring using starting index `i` and ending index `j`.
4. Set two pointers, `left = i` and `right = j`, and assume the substring is a palindrome.
5. Compare characters from both ends while `left < right`; mark it non-palindromic if a mismatch occurs.
6. If the substring is a palindrome and its length is greater than `longest`, update `longest` with that substring.
7. After checking all substrings, return and display `longest`.
8. **End**

## Program:
```
/*
Program to implement Reverse a String
Developed by: Vishwaraj G
Register Number: 212223220125
*/
import java.util.Scanner;

public class Solution {
    public String longestPalindrome(String s) {
        //Type code here...
        String longest="";
        for(int i=0;i<s.length();i++)
        {
            for(int j=i;j<s.length();j++)
            {
                int left=i;
                int right=j;
                boolean ispalindrome=true;
                while(left<right)
                {
                    if(s.charAt(left)!=s.charAt(right))
                    {
                        ispalindrome=false;
                        break;
                    }
                    left++;
                    right--;
                }
                if(ispalindrome && (j-i+1)>longest.length())
                {
                    longest=s.substring(i,j+1);
                }
            }
        }
        return longest;
    }

    // Main method for user input
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        //System.out.println("Enter a string:");
        String input = scanner.nextLine();

        Solution sol = new Solution();
        String result = sol.longestPalindrome(input);

        System.out.println("Longest Palindromic Substring: " + result);
        scanner.close();
    }
}
```

## Output:

<img width="592" height="115" alt="image" src="https://github.com/user-attachments/assets/accf0cca-7d38-4e33-9d0f-305bebbf69f1" />


## Result:
The program successfully implemented and the expected output is verified.
