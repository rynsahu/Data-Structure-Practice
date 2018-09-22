## Q1: Given two integers m & n, calculate and return their multiplication using recursion. You can only use subtraction and addition for your calculation. No other operators are allowed.
    
Solution: 
```
#include <iostream>

using namespace std;

int multiplyNumbers(int m, int n) {
    if(n == 0) {
        return 0;
    }
    return m + multiplyNumbers(m, --n);
}

int main()
{
    int m, n;
    
    cin>>m;
    cin>>n;
    
    cout<<multiplyNumbers(m,n);

    return 0;
}
```
