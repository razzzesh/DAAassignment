


Problem Statement : Possible Maximum Sum of Three Stacks: Queue Implementation
Finding the Maximum sum of three Stacks using queue data stucture .

Code:
```
class PossibleEqualMaxSum {
    public static int MaximumSum(int q1[], int q2[], int q3[], int n1, int n2, int n3)
    {  int s1 = 0, s2 = 0, s3 = 0;
    
    // finding the initial sum of queue1
    for (int i=0; i < n1; i++)
        s1 += q1[i];
    
    // finding the initial sum of queue2
    for (int i=0; i < n2; i++)
        s2 += q2[i];
    
    // finding the initial sum of queue3
    for (int i=0; i < n3; i++)
        s3 += q3[i];
    
    // logic
    int f1 =0, f2 = 0, f3 = 0;
    int ans = 0;
    while (true)
    {
        // if any queue is empty
        if (f1 == n1 || f2 == n2 || f3 == n3)
            return 0;
    
        // if sum of all three queue are equal
        if (s1 == s2 && s2 == s3)
            return s1;
        
        // finding the queue with maximum sum and removing its front element
        if (s1 >= s2 && s1 >= s3)
            s1 -= q1[f1++];
        else if (s2 >= s1 && s2 >= s3)
            s2 -= q2[f2++];
        else if (s3 >= s2 && s3 >= s1)
            s3 -= q3[f3++];
    }
    }
    
    // Driver code 
    public static void main(String[] args)
    {
        int queue1[] = {7, 4, 2};
        int queue2[] = {5, 8, 3, 2, 2};
        int queue3[] = {3, 2, 1, 2};
        
        int n1 = queue1.length;
        int n2 = queue2.length;
        int n3 = queue3.length;
        
        System.out.println("Possible Equal Maximum Sum: "+MaximumSum(queue1, queue2, queue3, n1, n2, n3));
    }
}

Output of the Code  :
Possible Equal Maximum Sum: 2


TEST CASES
INPUT 1 :
Stack 1 : 6 1 0 1
Stack 2 : 6 1 1 
Stack 3 : 5 2 8
OUTPUT 1  :
Possible Equal Maximum Sum : 8

INPUT 2 :
Stack 1 : 8 5 3
Stack 2 : 6 9 4 2 2
Stack 3 : 3 2 1 2
OUTPUT 2  :
Possible Equal Maximum Sum : 8

INPUT 3 :
Stack 1 : 9 1 4 2
Stack 2 : 3 6 1
Stack 3 : 1 2 5
OUTPUT 3 :
Possible Equal Maximum Sum : 7
```


Explanation :</br>
Data structure used:
Three queues q1,q2,q3 to store the elements.
s1,s2,s3 to store respective sums of q1,q2 and q3 respectively.

The approach to the problem is as follows:
Step1:We store the sums of q1,q2,q3 in s1,s2,s3
Step2:we add conditionals to satisfy the max possible equal  sum-condition.if the queue is empty simply return 0.If the sum of all three queues are equal return anyone sum.
For other conditions,finding the queue with maximum sum and removing its front element








