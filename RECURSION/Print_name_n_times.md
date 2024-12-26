# Print GFG n times
Print GFG n times without the loop.

Example:

# Input:
```5```
# Output:
```GFG GFG GFG GFG GFG```
Your Task:
This is a function problem. You only need to complete the function printGfg() that takes N as parameter and prints N times GFG recursively. Don't print newline, it will be added by the driver code.


Expected Time Complexity: O(N).
Expected Auxiliary Space: O(N) (Recursive).

Constraint:
1<=N<=1000

# Problem Link->

https://www.geeksforgeeks.org/problems/print-gfg-n-times/1?utm_source=youtube&utm_medium=collab_striver_ytdescription&utm_campaign=print-gfg-n-times

# SOlution
```C++
#include<bits/stdc++.h>
using namespace std;

void printName(int n){
    if(n ==0) return ;
    printName(n- 1);
    cout<<"GFG"<<" ";
}
int main() {
    int n ;
    cin>>n;
    
    printName(n);
    
    return 0;
}
```
# Final Complexity:
Time Complexity: O(n)
Space Complexity: O(n) 