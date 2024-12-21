# Bubble Sort 
Problem Statement: Given an array of N integers, write a program to implement the Bubble Sorting algorithm.

Examples:

Example 1:
# Input: 
```N = 6, array[] = {13,46,24,52,20,9}```

# Output: 
```9,13,20,24,46,52```

Explanation: After sorting we get 9,13,20,24,46,52


# Input:
```N = 5, array[] = {5,4,3,2,1}```

# Output: 
```1,2,3,4,5```

Explanation: After sorting we get 1,2,3,4,5

# problem link ->
https://www.geeksforgeeks.org/problems/bubble-sort/1?utm_source=youtube&utm_medium=collab_striver_ytdescription&utm_campaign=bubble-sort


# Solution
```C++
#include <bits/stdc++.h>
using namespace std;
void bubbleSort(vector<int>& arr , int n){
    for(int i = n-1 ; i >=0 ;i--){
        for(int j = 0 ; j <= i-1 ;j++){
            if(arr[j] > arr[j+1]){
                swap(arr[j],arr[j+1] );
            }
        }
    }
}
int main() {
   int n;
   cin>>n;
   
   vector<int> arr(n);
   for(int i =0 ;i<n ;i++){
       cin>>arr[i];
   }
   bubbleSort(arr, n);
   
   for(int i = 0 ;i<n ;i++){
       cout<<arr[i]<<" ";
   }
   cout<<endl;
    return 0;
}
```
# Complexity
Time complexity: O(N2)
Space Complexity: O(1)


