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
#### Q3: Write a recursive function that returns the sum of the digits of a given integer.

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
#### Q4: Find the length of string using recursion.

Solution:
```
#include <iostream>

using namespace std;

int stringLength(char str[]) {
    if(str[0] == 0){
        return 0;
    }
    
    int lengthOfString = stringLength(str + 1);
    return ++lengthOfString;
}

int main()
{
    char str[100];
    cin>>str;
    
    cout<<stringLength(str);
}
```

#### Q5: Remove the 'x' from string using recursion.

Solution:
```
#include <iostream>

using namespace std;

void removeX(char str[]) {
    if(str[0] == '\0') {
        return;
    }
    
    if(str[0] != 'x') {
        removeX(str+1);
    } else {
        int i;
        for(i = 1; str[i] != '\0'; i++) {
            str[i-1] = str[i];
        }
        str[i-1] = str[i];
        removeX(str);
    }
    return;
}

int stringLength(char str[]) {
    if(str[0] == 0){
        return 0;
    }
    
    int lengthOfString = stringLength(str + 1);
    return ++lengthOfString;
}

int main()
{
    char str[100];
    cout<<"Enter the string: ";
    cin>>str;
    
    int length = stringLength(str);
    
    removeX(str);
    
    cout<<"1st length: "<<length<<endl;
    cout<<"String after removel: "<<str<<endl;
    
    length = stringLength(str);
    cout<<"2nd lenght: "<<length;
}
```
Output:
```
Enter the string: axbxzx                                                                                                                 
1st length: 6         
String after removel: abz        
2nd lenght: 3 
```
#### Q6: Given an input string S and two characters c1 and c2, you need to replace every occurrence of character c1 with character c2 in          the given string.
Solution:
```
#include <iostream>
#include <bits/stdc++.h>

using namespace std;

void replaceCharacter (char input[], char c1, char c2) {
    
    if(input[0] == '\0') {
        return;
    }
    
    
    if(input[0] == c1) {
        input[0] = c2;
        replaceCharacter(input+1, c1, c2);
    } else {
        replaceCharacter(input+1, c1, c2);   
    }
}

int main()
{
    string str;
    getline(cin, str);
    
    char s[str.length()], c1, c2;
    
    cin>>c1;
    cin>>c2;
    
    for(int i=0; i <= str.length(); i++) {
        s[i] = str[i];
    }
    
    replaceCharacter(s,c1,c2);
    
    cout<<s<<endl;
    cout<<str;
}
```
Output:
```
xryxn sxhu                                                                                                                               
x a                                                                                                                                     
aryan sahu                                                                                                                               
xryxn sxhu 
```
#### Q7: Given a string S, remove consecutive duplicates from it recursively.
Solution:
```
#include <iostream>
#include <bits/stdc++.h>

using namespace std;

void removeConsecutiveDuplicates(char *input) {
    if(input[0] == '\0') {
        return;
    } 
    
    char c = input[0];
    
    if(input[1] == c) {
        int i;
        for(i=1; input[i] != '\0'; i++) {
            input[i] = input[i+1];
        }
        input[i] = input[i+1];
        removeConsecutiveDuplicates(input + 1);
    } else {
        removeConsecutiveDuplicates(input + 1);
    }
}

int main()
{
    string str;
    getline(cin, str);
    
    char s[str.length()];
    
    for(int i=0; i <= str.length(); i++) {
        s[i] = str[i];
    }
    
    removeConsecutiveDuplicates(s);
    
    cout<<s<<endl;
    cout<<str;
}
```
Output:
```
aabccba                                                                                                                                 
abcba      
aabccba
```
