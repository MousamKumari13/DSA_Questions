# Factorial Number

For a given number N, find whether it is a factorial number or not. A Factorial number is a number which is equal to the factorial value of other numbers.
 

Example 1:

## Input:
```plaintext
N = 6
```
## Output:
```plaintext
1
```

Explanation:
6 is factorial of 3 
Example 2:

## Input:
```plaintext
N = 5
```
## Output:
```plaintext
0
```
Explanation:
no number's factorial is 5.

Your Task:
You don't need to read input or print anything. Your task is to complete the function isFactorial() which takes an integer N as input parameters and returns 1 if N is a factorial number, or 0 otherwise.
 
Expected Time Complexity: O(log N)
Expected Space Complexity: O(1)

***Constraints:***
```1 <= N <= 100000```

## Problem Link->
https://www.geeksforgeeks.org/problems/factorial-number2446/1

## Solution
```C++
#include <iostream>
using namespace std;

int isFactorial(int n, int i = 1) {
    if (n == 1) return 1;  
    if (n % i != 0) return 0;  // If `n` is not divisible by `i`, it's not factorial
    return isFactorial(n / i, i + 1);  // Recursive call with updated values
}

int main() {
    int t;  
    cin >> t;

    while (t--) {
        int n;
        cout << "Enter a number: ";
        cin >> n;

        if (isFactorial(n)) {
            cout << n << " is a factorial number." << endl;
        } else {
            cout << n << " is NOT a factorial number." << endl;
        }
    }

    return 0;
}
```
# Complexity
**Time Complexity:** O(√n)

**Space Complexity:** O(√n)(for recursive stack)

## Solution2
```C++
#include <iostream>
using namespace std;

class Solution {
public:
    int isFactorial(int N) {
        long long factorial = 1;  
        int k = 1;

        // Iterate until factorial exceeds N
        while (factorial <= N) {
            if (factorial == N) {
                return 1;  // N is a factorial number
            }
            k++;  // Increment k to calculate the next factorial
            factorial *= k;  // Update factorial to k!
        }

        return 0;  // N is not a factorial number
    }
};

int main() {
    Solution sol;
    int N;
    cin >> N;

    if (sol.isFactorial(N)) {
        cout << N << " is a factorial number." << endl;
    } else {
        cout << N << " is NOT a factorial number." << endl;
    }

    return 0;
}
```
### Complexity
**Time Complexity:** O(log N)

**Space Complexity:** O(1)

