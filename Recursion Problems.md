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
#### Given an integer n, count and return the number of zeros that are present in the given integer using recursion.

Solution:
```
#include <iostream>

using namespace std;

int countZeros(int n) {
    
    static int count=0;
    
    if (n > 0) {
        if(n%10 == 0){
            count++;
            countZeros(n/10);
        }else{
            countZeros(n/10);
        }   
    }
    
    return count;
    
}

int main()
{
    int n;
    cin>>n;
    
    cout<<countZeros(n)<<endl;

    return 0;
}
```
