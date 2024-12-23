# Selection Sort
Problem Statement: Given an array of N integers, write a program to implement the Selection sorting algorithm.

Examples:

Example 1:
# Input: 
```N = 6, array[] = {13,46,24,52,20,9}```
# Output: 
```9,13,20,24,46,52```

Explanation: After sorting the array is: 9, 13, 20, 24, 46, 52

Example 2:
# Input: 
```N=5, array[] = {5,4,3,2,1}```
# Output: 
```1,2,3,4,5```

Explanation: After sorting the array is: 1, 2, 3, 4, 5

# Problem Link -> 
https://www.geeksforgeeks.org/problems/selection-sort/1?utm_source=youtube&utm_medium=collab_striver_ytdescription&utm_campaign=selection-sort

# Solution 
```C++
#include<bits/stdc++.h>

using namespace std;
void selection_sort(vector<int>& arr, int n) {
  
  for (int i = 0; i < n - 1; i++) {
    int mini = i;
    for (int j = i + 1; j < n; j++) {
      if (arr[j] < arr[mini]) {
        mini = j;
      }
    }
    int temp = arr[mini];
    arr[mini] = arr[i];
    arr[i] = temp;
  }

  for (int i = 0; i < n; i++) {
    cout << arr[i] << " ";
  }

}
int main() {
 int n;
 cin>>n;

 vector<int> arr(n);
   for (int i = 0; i < n; i++) {
    cin>>arr[i];
  }
  selection_sort(arr, n);
  return 0;
}
```
# Complexity

Time complexity: O(N2), (where N = size of the array), for the best, worst, and average cases.
Reason: If we carefully observe, we can notice that the outer loop, say i, is running from 0 to n-2 i.e. n-1 times, and for each i, the inner loop j runs from i to n-1. For, i = 0, the inner loop runs n-1 times, for i = 1, the inner loop runs n-2 times, and so on. So, the total steps will be approximately the following: (n-1) + (n-2) + (n-3) + ……..+ 3 + 2 + 1. The summation is approximately the sum of the first n natural numbers i.e. (n*(n+1))/2. The precise time complexity will be O(n2/2 + n/2). Previously, we have learned that we can ignore the lower values as well as the constant coefficients. So, the time complexity is O(n2). Here the value of n is N i.e. the size of the array.

Space Complexity: O(1)