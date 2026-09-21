
# EX 2B Jump Game using Greedy Algorithm.
## DATE: 28/07/2026
## AIM:
To write a Java program to for given constraints.
You are given an array of integers. Each number represents the maximum number of steps you can jump forward from that position.

You start from the first element (index 0). 
Write a program to find the minimum number of jumps required to reach the last index of the array.

If it is not possible to reach the end, return -1.

## Algorithm

1. **Start**
2. Read the array `nums`; if its length is `1` or less, return `0`.
3. If the first element is `0`, return `-1` because the end cannot be reached.
4. Initialize `jump = 0`, `current = 0`, and `pos = 0`.
5. Traverse the array and update `pos` with the farthest index reachable from the current positions.
6. When the current boundary `i` is reached, increment `jump` and update `current` to `pos`.
7. If `current` reaches or exceeds the last index, stop; if no further position is reachable, return `-1`.
8. Display the minimum number of jumps, or `-1` if the last index cannot be reached.
9. **End**

## Program:
```
/*
Program to implement Reverse a String
Developed by: Vishwaraj G
Register Number: 212223220125
*/
import java.util.Scanner;

public class MinJumpToEnd {

    // Function to return minimum jumps to reach end
    public static int minimumJumps(int[] nums) {
        // Type Your Code Here.
        if(nums.length<=1) return 0;
        if(nums[0]==0) return -1;
        int jump=0;
        int current=0;
        int pos=0;
        for(int i=0;i<nums.length-1;i++)
        {
            pos=Math.max(pos,i+nums[i]);
            if(i==current)
            {
                jump++;
                current=pos;
                if(current>=nums.length-1) break;
                if(current==i) return -1;
            }
        }
        return current>=nums.length-1 ? jump: -1;
    }

    // Main method to handle input and output
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt(); // Number of elements
        int[] nums = new int[n];

        for (int i = 0; i < n; i++) {
            nums[i] = sc.nextInt();
        }

        System.out.println("Minimum jumps to reach last index: " + minimumJumps(nums));
    }
}
```

## Output:
<img width="653" height="181" alt="image" src="https://github.com/user-attachments/assets/b8243fe7-db61-4f90-ab54-b9a63b4e0e61" />



## Result:
The program successfully implemented and the expected output is verified.
