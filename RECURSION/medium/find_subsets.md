# Subsets

Given an integer array nums of unique elements, return all possible 
subsets (the power set).

The solution set must not contain duplicate subsets. Return the solution in any order.

Example 1:

### Input: 
```plaintext
nums = [1,2,3]
```
### Output: 
```plaintext
[[],[1],[2],[1,2],[3],[1,3],[2,3],[1,2,3]]
```

Example 2:

### Input: 
```plaintext
nums = [0]
```
### Output: 
```plaintext
[[],[0]]
```

***Constraints:***
```plaintext
1 <= nums.length <= 10
-10 <= nums[i] <= 10
All the numbers of nums are unique.
```

## Problem link->
https://leetcode.com/problems/subsets/description/
https://www.geeksforgeeks.org/problems/subsets-1613027340/1

### For Understanding this concept watch this video ->
https://youtu.be/p4bP_FIXGWw?si=QizHRcKwLDPObQSB

# Solution( Using Recursion)
```C++
#include <bits/stdc++.h> 
using namespace std;

void solve(int i ,vector<int>& arr , vector<int>& temp ,vector<vector<int>>& result){

    if(i >= arr.size()){
        result.push_back(temp);
        return;
    }
    
    temp.push_back(arr[i]); // take ith element
    solve(i+1 , arr , temp , result);//recursion call for next ith iteration
    
    temp.pop_back(); // not take ith element (backtracking);
    solve(i+1 , arr , temp , result);
    
}
vector<vector<int>> subset(vector<int>& arr){
    vector<int> temp;
    vector<vector<int>> result;
    
    solve(0 , arr , temp , result);
    
    return result;
   
}
int main()
{
   int n;
   cin>>n;
   vector<int> arr(n);
   for(int i =0 ;i<n ;i++){
       cin>>arr[i];
   }
   
    vector<vector<int>> result = subset(arr);
    
    for(auto& subsets : result){
        cout << "[";
        for(auto& num : subsets){
            cout<<num<<" ";
        }
        cout<<"]"<<endl;
    }
    return 0;
}
```

# Complexity

**Time Complexity:** ```O(n⋅2^n)```

**Space Complexity:** ```O(n⋅2^n)```