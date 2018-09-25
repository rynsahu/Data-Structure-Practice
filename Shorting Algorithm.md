## What is shorting?
Arranging of elements in a particular manner it may be in `ascending` or `descending` order that is called shorting.

## Bubble Short
In bubble short technique, each pair of adjacent elements is compared and elements are swapped if they are not in order.
#### Complexity 
```
Best Case: o(n)
Average Case: o(n^2)
Worst Case: o(n^2)
```
#### Program:
```
#include <iostream>

using namespace std;

void bubblehShort(int input[], int size) {
    int temp, flag;
    
    for(int i = 0; i < size - 1; i++) {
        flag = 0;
        
        for(int j = 0; j < size-i; j++) {
            
            if(input[j] > input[j+1]) {
                temp = input[j];
                
                input[j] = input[j+1];
                input[j+1] = temp;
                
                flag = 1;
            }
        }
        if(flag == 0) {break;}
    }
}

int main()
{
    int size=7;
    int arr[size];
    
    for(int i = 0; i < 6; i++) {
        cin>>arr[i];
    }
    
    bubblehShort(arr, size);
    
    for(int i = 0; i < size; i++) {
        cout<<arr[i]<<" ";
    }
}
```
