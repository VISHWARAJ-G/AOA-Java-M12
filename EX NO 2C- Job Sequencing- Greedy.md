
# EX 1C Job Sequencing using Greedy Approach
## DATE: 30/07/2026
## AIM:
To write a Java program to for given constraints.
Given an integer array nums and an integer k, return the number of pairs (i, j) where i < j such that |nums[i] - nums[j]| == k.

The value of |x| is defined as:

x if x >= 0.
-x if x < 0.You're given N jobs, each with:

A unique jobId

A deadline (by which it must be completed)

A profit (earned only if completed on or before the deadline)

Each job:

Takes exactly 1 unit of time

Only one job can be done at a time

Your goal is to maximize total profit while completing the maximum number of jobs possible within their deadlines.

## Algorithm

1. **Start**
2. Read the number of jobs and their `id`, `deadline`, and `profit`.
3. Sort all jobs in descending order of profit.
4. Find the maximum deadline among all jobs and create a slot array to track occupied time slots.
5. For each job, search backward from its deadline for the latest available slot.
6. If an available slot is found, schedule the job, mark the slot as occupied, and update the job count and total profit.
7. Repeat until all jobs are considered.
8. Display the total number of scheduled jobs and the maximum profit obtained.
9. **End**

## Program:
```
/*
Program to implement Reverse a String
Developed by: Vishwaraj G
Register Number: 212223220125
*/
import java.util.*;

public class JobScheduling {

    static class Job {
        int id, deadline, profit;

        Job(int id, int deadline, int profit) {
            this.id = id;
            this.deadline = deadline;
            this.profit = profit;
        }
    }

    public static int[] jobScheduling(Job[] jobs, int n) {

        // Sort by profit in descending order
        Arrays.sort(jobs, (a, b) -> b.profit - a.profit);

        int maxDeadline = 0;

        for (Job job : jobs)
            maxDeadline = Math.max(maxDeadline, job.deadline);

        boolean[] slot = new boolean[maxDeadline + 1];

        int count = 0;
        int profit = 0;

        for (Job job : jobs) {

            // Find latest available slot
            for (int j = Math.min(job.deadline, maxDeadline); j > 0; j--) {

                if (!slot[j]) {
                    slot[j] = true;
                    count++;
                    profit += job.profit;
                    break;
                }
            }
        }

        return new int[]{count, profit};
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int n = sc.nextInt();
        Job[] jobs = new Job[n];

        for (int i = 0; i < n; i++) {
            int id = sc.nextInt();
            int deadline = sc.nextInt();
            int profit = sc.nextInt();

            jobs[i] = new Job(id, deadline, profit);
        }

        int[] result = jobScheduling(jobs, n);

        System.out.println(result[0] + " " + result[1]);
    }
}
```

## Output:

<img width="349" height="243" alt="image" src="https://github.com/user-attachments/assets/6dc86cab-c02f-44d0-a19b-320f44a7558f" />


## Result:
The program successfully implemented and the expected output is verified.
