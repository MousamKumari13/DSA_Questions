# Sum of first N Natural Numbers.
Problem statement: Given a number ‘N’, find out the sum of the first N natural numbers.

Examples:

Example 1:
# Input:
```N=5```
# Output: 
```15```

Explanation: 1+2+3+4+5=15

Example 2:
# Input:
```N=6```
# Output: 
```21```

Explanation: 1+2+3+4+5+6=15

# Solution
```C++
#include <bits/stdc++.h>
using namespace std;
void fun(int i, int sum) {
	if(i < 1) {
		cout<<sum<<endl;
		return;
	}

	fun(i-1, sum + i);
}
int main() {
	int n ;
	cin>>n;

	fun(n, 0);

}```
Final Complexity:
Time Complexity: O(n)
Space Complexity: O(n)