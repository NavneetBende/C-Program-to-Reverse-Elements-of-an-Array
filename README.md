# C-Program-to-Reverse-Elements-of-an-Array

Reverse elements of an array in C
Here, in this page we will discuss the program to reverse elements of an array in C programming language. We are given with an array and need to reverse the elements. We will discuss various algorithms to reverse the array in efficient way.

C program to reverse an array
Here, in page we will discuss various method for reversing the array. Different methods are :

Method Discussed
Method 1: Just print the array in reverse order
Method 2: Actual in-place reversing of the original array
Method 3: Recursive in-place reversing of the original array
 
Example :
Input : arr[5] = [10, 20, 30, 40, 50]
Output : Array after reversing, arr[5] = [50, 40, 30, 20, 10]
We will discuss all of these methods one by one below –

C program to reverse an array
Method 1
For an array: arr

Run an iterative loop from the last index of the array
Print each item one by one arr[i]
Let’s see how it works below –

Method 1 Code in C
Run
#include <stdio.h>

void printReverse(int arr[], int len){
    
    for(int i = len - 1; i >= 0; i--)
        printf("%d ", arr[i]);
}

int main()
{
    int arr[] = {10, 20, 30, 40, 50, 60};
    
    int len = sizeof(arr)/sizeof(arr[0]);
    
    printf("Array in Reverse:\n");
    printReverse(arr, len);

    return 0;
}
Output
Array in Reverse:
60 50 40 30 20 10 
Related Pages
Find Second Smallest Element in an Array

Calculate the sum of elements in an array

Sort first half in ascending order and second half in descending 

Sort the elements of an array

Finding the frequency of elements in an array

Method 2
For an array: arr[] with length len.

Call a function void reverse(int arr[], int start, int end)
Intial calling as reverse(arr, 0, len-1);
Swap items at start & end indexes
Do start++ & end–
Stop when start & end indexes overlap one another
Print the array
Time and Space Complexity :
Time – Complexity : O(n)
Space-Complexity : O(1)
 

C Program to Reverse elements of an array
Method 2 Code in C
Run
#include <stdio.h>

void reverse(int arr[], int start, int end)
{
    while (start < end)
    {
        // swap arr[start] & arr[end]
        int temp = arr[start];
        arr[start] = arr[end];
        arr[end] = temp;
        
        start++;
        end--;
    }
}

void display(int arr[], int len){
    
    for(int i = 0; i < len; i++)
        printf("%d ", arr[i]);
}

int main()
{
    int arr[] = {10, 20, 30, 40, 50, 60};
    
    int len = sizeof(arr)/sizeof(arr[0]);
    
    reverse(arr, 0, len-1);
    
    printf("Array in Reverse:\n");
    display(arr, len);

    return 0;
}
Output
Array in Reverse:
60 50 40 30 20 10 
Method 3
In this method, we will use recursion. Call function reverseRecursive(int arr[], int start, int end)

Initially pass values of start = 0, end = len – 1

Function gets called as reverseRecursive(arr, 0, len-1);
In each recursive iteration swap arr[start] & arr[end]
Make further recursive calls as reverseRecursive(arr, start + 1, end – 1);
return when (start >= end)
Print the array
Time and Space Complexity :
Time – Complexity : O(n)
Space-Complexity : O(n), require stack to store the recursive calls.
Reverse elements of an array in C
Method 3 Code in C
Run
#include <stdio.h>

void reverseRecursive(int arr[], int start, int end)
{
    if (start >= end)
        return;
     
    int temp = arr[start];
    arr[start] = arr[end];
    arr[end] = temp;
     
    // recursive call to swap arr[start+1] & arr[end-1]
    reverseRecursive(arr, start + 1, end - 1);
}   

void display(int arr[], int len){
    
    for(int i = 0; i < len; i++)
        printf("%d ", arr[i]);
}

int main()

    reverseRecursive(arr, 0, len-1);
    
    printf("Array in Reverse:\n");
    display(arr, len);

    return 0;
}
Output
Array in Reverse:
60 50 40 30 20 10 
