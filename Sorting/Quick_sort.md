# Quick Sort Algorithm

## Problem Statement:  Given an array of n integers, sort the array using the Quicksort method.

Examples:

Example 1:
## Input:  
```N = 5  , Arr[] = {4,1,7,9,3}```
## Output: 
```1 3 4 7 9 ```

Explanation: After sorting the array becomes 1, 3, 4, 7, 9

Example 2:
## Input: 
```N = 8 , Arr[] = {4,6,2,5,7,9,1,3}```
## Output: 
```1 2 3 4 5 6 7 9```
Explanation: After sorting the array becomes 1, 3, 4, 7, 9

## Problem Link ->
https://www.geeksforgeeks.org/problems/quick-sort/1?utm_source=youtube&utm_medium=collab_striver_ytdescription&utm_campaign=quick-sort

# Solution
```C++

#include <bits/stdc++.h>
using namespace std;
int partition(vector<int>& arr , int low , int high){
    int pivot = arr[low];
    int i = low;
    int j = high;
    while(i < j){
        while(arr[i] <= pivot && i <= high - 1){
            i++;
        }
        while(arr[j] > pivot && j >= low + 1){
            j--;
        }
        if(i < j){
            swap(arr[i] , arr[j]);
        }
    }
    swap(arr[low] , arr[j]);
    return j;
}
void qs(vector<int>& arr , int low , int high){
    if(low < high){
        int Pidx = partition(arr , low , high);
        qs(arr, low , Pidx - 1);
        qs(arr , Pidx + 1 , high);
    }
}

vector<int> quicksort(vector<int>& arr ){
    qs(arr , 0 , arr.size()-1);
    return arr;
}
int main()
{
   int n ;
   cin>>n;
   
  vector<int> arr(n);
  for(int i =0 ;i<n ;i++){
      cin>>arr[i];
  }
 
   arr = quicksort(arr);
  for(int i =0 ;i<n ;i++){
      cout<<arr[i]<<" ";
  }
    return 0;
}
```
# Complexity
Time Complexity: O(N*logN), where N = size of the array.

Space Complexity: O(1) + O(N) auxiliary stack space.