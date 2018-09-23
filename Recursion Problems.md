#### Q1: Given two integers m & n, calculate and return their multiplication using recursion. You can only use subtraction and addition for your calculation. No other operators are allowed.
    
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
#### Q2: Given an integer n, count and return the number of zeros that are present in the given integer using recursion.

Solution:
```
#include <iostream>

using namespace std;

int counts(int n, int & count) {
    int r = n%10;
    
    if(n>0) {
        if(r == 0) {
            counts(n/10, ++count);
        }else {
            counts(n/10, count);
        }
    }

    return count;
}

int countZeros(int n) {
    
    int count = 0;
    return counts(n, count);
    
}

int main()
{
    int n;
    cin>>n;
    
    cout<<countZeros(n)<<endl;

    return 0;
}
```
#### Write a recursive function that returns the sum of the digits of a given integer.

Solution: 
```
#include <iostream>

using namespace std;

int sumOfDigits(int n) {
    int r = n%10;
    
    if(n != 0) {
        r = r + sumOfDigits(n/10);
    }
    
    return r;
}

int main()
{
    int n;
    cin>>n;
    
    cout<<sumOfDigits(n);
}
```
