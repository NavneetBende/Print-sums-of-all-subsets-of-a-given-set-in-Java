# Print-sums-of-all-subsets-of-a-given-set-in-Java

Sums of all Subsets of a given set in Java
Here, in this page we will discuss the program to print the sums of all subsets of a given set in Java programming Language. We will discuss various methods to solve the given problem.

Sums of all Subsets of a given set in Java
Method Discussed :
Method 1 : Using Recursion
Method 2 : Using Iteration.
Let’s discuss them one by one in brief,

Method 1:
The total number of subset will be 2n, where n is the size of the array.
Run a loop from  0 to 2n -1.
Now, Pick all array elements which correspond to 1s in binary representation of ith number.
Method 1 : Code in Java
Run
import java.io.*;
 
class Main {
 
    static void subsetSums(int[] arr, int l, int r, int sum)
    {
 
        if (l > r) {
            System.out.print(sum + " ");
            return;
        }
 
        subsetSums(arr, l + 1, r, sum + arr[l]);
 
        subsetSums(arr, l + 1, r, sum);
    }
 
    // Driver code
    public static void main(String[] args)
    {
        int[] arr = { 5, 4, 3 };
        int n = arr.length;
 
        subsetSums(arr, 0, n - 1, 0);
    }
}
 
Output :
12 9 8 5 7 4 3 0
Related Pages
Decimal to Binary conversion

Decimal to Octal Conversion

Decimal to Hexadecimal Conversion

Permutations in which n people can occupy r seats in a classroom 

Octal to Binary conversion

Quadrants in which a given coordinate lies

Method 2:
In this method we will discuss the recursive way to find the subsets sum, in this either we will take the elements value in the sum or not. Based on this approach we will find the subsets sum.

Method 2 : Code in Java
Run
import java.io.*;
 
class Main {
 
    static void subsetSums(int arr[], int n)
    {
 
        int total = 1 << n;
 
        for (int i = 0; i < total; i++) {
            int sum = 0;
 
            for (int j = 0; j < n; j++)
                if ((i & (1 << j)) != 0)
                    sum += arr[j];
 
            System.out.print(sum + " ");
        }
    }
 
    // Driver code
    public static void main(String args[])
    {
        int arr[] = new int[] { 5, 4, 3 };
        int n = arr.length;
 
        subsetSums(arr, n);
    }
}   
Output :
0 5 4 9 3 8 7 12
