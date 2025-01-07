# Insertion Sort Algorithm

Problem Statement: Given an array of N integers, write a program to implement the Insertion sorting algorithm.

Examples:

Example 1:
## Input: 
```N = 6, array[] = {13,46,24,52,20,9}```
## Output: 
```9,13,20,24,46,52```
Explanation: 
After sorting the array is: 9,13,20,24,46,52

Example 2:
## Input: 
```N=5, array[] = {5,4,3,2,1}```
## Output: 
```1,2,3,4,5```

Explanation: After sorting the array is: 1,2,3,4,5

# problem link->
https://www.geeksforgeeks.org/problems/insertion-sort/0?category%5B%5D=Algorithms&page=1&query=category%5B%5DAlgorithmspage1&utm_source=youtube&utm_medium=collab_striver_ytdescription&utm_campaign=insertion-sort
## 2nd Link-> 
https://www.naukri.com/code360/problems/insertion-sort_3155179?interviewProblemRedirection=true&search=insertion&leftPanelTabValue=PROBLEM

# Solution
```C++

#include <bits/stdc++.h>
using namespace std;
void insertionsort(int n , vector<int>& arr){
    for(int i =0 ;i< n ;i++){
        int j = i;
        while(j >0 && arr[j-1] > arr[j]){
           int temp = arr[j-1];
           arr[j-1] = arr[j];
           arr[j] = temp;
            j--;
        }
    }
    
    for(int i =0 ;i< n ;i++){
        cout<<arr[i]<<" ";
    }
}
int main()
{
   int n ;
   cin>>n;
   
  vector<int> arr(n);
  for(int i =0 ;i<n ;i++){
      cin>>arr[i];
  }
  insertionsort(n , arr);
    return 0;
}
```
# Complexity

Time complexity: O(N2), (where N = size of the array), for the worst, and average cases.

Reason: If we carefully observe, we can notice that the outer loop, say i, is running from 0 to n-1 i.e. n times, and for each i, the inner loop j runs from i to 1 i.e. i times. For, i = 1, the inner loop runs 1 time, for i = 2, the inner loop runs 2 times, and so on. So, the total steps will be approximately the following: 1 + 2 + 3 +......+ (n-2) + (n-1). The summation is approximately the sum of the first n natural numbers i.e. (n*(n+1))/2. The precise time complexity will be O(n2/2 + n/2). Previously, we have learned that we can ignore the lower values as well as the constant coefficients. So, the time complexity is O(n2). Here the value of n is N i.e. the size of the array.

Space Complexity: O(1)