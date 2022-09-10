# DAAassignment
class PossibleEqualMaxSum {
    
    public static int MaximumSum(int queue1[], int queue2[], int queue3[], int n1, int n2, int n3)
    {
    int sum1 = 0, sum2 = 0, sum3 = 0;
    
    // finding the initial sum of queue1
    for (int i=0; i < n1; i++)
        sum1 += queue1[i];
    
    // finding the initial sum of queue2
    for (int i=0; i < n2; i++)
        sum2 += queue2[i];
    
    // finding the initial sum of queue3
    for (int i=0; i < n3; i++)
        sum3 += queue3[i];
    
    // logic
    int front1 =0, front2 = 0, front3 = 0;
    int ans = 0;
    while (true)
    {
        // if any queue is empty
        if (front1 == n1 || front2 == n2 || front3 == n3)
            return 0;
    
        // if sum of all three queue are equal
        if (sum1 == sum2 && sum2 == sum3)
            return sum1;
        
        // finding the queue with maximum sum and removing its front element
        if (sum1 >= sum2 && sum1 >= sum3)
            sum1 -= queue1[front1++];
        else if (sum2 >= sum1 && sum2 >= sum3)
            sum2 -= queue2[front2++];
        else if (sum3 >= sum2 && sum3 >= sum1)
            sum3 -= queue3[front3++];
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
