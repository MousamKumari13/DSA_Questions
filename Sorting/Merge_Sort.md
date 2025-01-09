# Merge Sort Algorithm

Problem:  Given an array of size n, sort the array using Merge Sort.

Examples:

Example 1:
## Input: 
```N=5, arr[]={4,2,1,6,7}```
## Output: 
```1,2,4,6,7```


Example 2:
## Input: 
```N=7,arr[]={3,2,8,5,1,4,23}```
## Output:
``` 1,2,3,4,5,8,23```

# Problem Link->
https://www.geeksforgeeks.org/problems/merge-sort/1?utm_source=youtube&utm_medium=collab_striver_ytdescription&utm_campaign=merge-sort

## Solution
```C++
#include <bits/stdc++.h>
using namespace std;
void mergeSort(vector<int>& arr , int low , int mid , int high){
    vector<int> temp;
    int left = low ;
    int right = mid+1;
    
    while(left <= mid && right <= high){
        if(arr[left] < arr[right]){
            temp.push_back(arr[left]);
            left++;
        }else{
            temp.push_back(arr[right]);
            right++;
        }
    }
    while(left <= mid){
        temp.push_back(arr[left]);
        left++;
    }
    while(right <= high){
        temp.push_back(arr[right]);
        right++;
    }
    for(int i = low ;i <= high;i++){
        arr[i]= temp[i-low];
    }
}
void ms(vector<int>& arr , int low , int high){
    if(low == high) return;
    int mid = (low + high) / 2;
    ms(arr , low , mid);
    ms(arr , mid+1 , high);
    mergeSort(arr, low , mid , high);
}
int main()
{
   int n;
   cin>>n;
   vector<int> arr(n);
   for(int i = 0 ;i< n ;i++){
       cin>>arr[i];
   }
   ms(arr , 0 , n-1);
   
   for(int i = 0 ;i <n ;i++){
       cout<<arr[i]<<" ";
   }
    return 0;
}
```
# Complexity
Time complexity: O(nlogn) 
Reason: At each step, we divide the whole array, for that logn and we assume n steps are taken to get sorted array, so overall time complexity will be nlogn

Space complexity: O(n)  
Reason: We are using a temporary array to store elements in sorted order.