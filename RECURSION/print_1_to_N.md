# Print 1 To N Without Loop
Print numbers from 1 to n without the help of loops. You only need to complete the function printNos() that takes n as a parameter and prints the number from 1 to n recursively.

Note: Don't print any newline, it will be added by the driver code.

Examples:

# Input: 
```n = 10```
# Output: 
```1 2 3 4 5 6 7 8 9 10```
# Input: 
```n = 5```
# Output: 
```1 2 3 4 5```
# Input: 
```n = 1```
# Output: ```1```

Constraints:
1 <= n <= 1000

# Problem Link -> 
https://www.geeksforgeeks.org/problems/print-1-to-n-without-using-loops-1587115620/1?utm_source=youtube&utm_medium=collab_striver_ytdescription&utm_campaign=print-1-to-n-without-using-loops

# Solution 
```C++
#include <bits/stdc++.h>
using namespace std;
void printn(int n){
    if(n ==0 ) return ;
    
    printn(n-1);
    cout<<n<<" ";
}
int main() {
    int n ;
    cin>>n;
    
    printn(n);
    
}
```
# Final Complexity:
Time Complexity: O(n)
Space Complexity: O(n) 

