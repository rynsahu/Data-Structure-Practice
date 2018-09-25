## What is shorting?
Arranging of elements in a particular manner it may be in `ascending` or `descending` order that is called shorting.

## 1. Selection Short
In this shorting technique, the list is divided into two parts one is shorted and another one is unsorted. Shorted part will be in the left end and unsorted part will be in the right end.
In the set of N elements, we need to find out the location of the minimum element and swap it with the location of the first element and repeat this step for n-1 elements until the list is not shorted.
#### Program:
```
#include <iostream>
using namespace std;

void SelectionShort(int input[], int size) {
    int temp,minIndex;
    
    for(int i=0; i<size-1; i++) 
    {
        minIndex = i;
        for(int j=i+1; j<size; j++) 
        {
            if(input[minIndex] > input[j])
            {
                minIndex = j;
            }
        }
        temp = input[i];
        input[i] = input[minIndex];
        input[minIndex] = temp;
    }
}

int main()
{
    int size=7;
    int arr[size];
    
    for(int i = 0; i < size; i++) {
        cin>>arr[i];
    }
    
    SelectionShort(arr, size);
    
    for(int i = 0; i < size; i++) {
        cout<<arr[i]<<" ";
    }
}
```

## 2. Bubble Short
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

## 3. Insertion Short
## Program:
```
#include <iostream>

using namespace std;

void InsertionShort(int input[], int size) {
    for(int i = 0; i<size-1; i++) {
        int value = input[i];
        int hole = i;
        
        while(hole > 0 && input[hole-1] > value) {
            input[hole] = input[hole-1];
            --hole;
        }
        
        input[hole] = value;
    }
}

int main()
{
    int size=7;
    int arr[size];
    
    for(int i = 0; i < size; i++) {
        cin>>arr[i];
    }
    
    InsertionShort(arr, size);
    
    for(int i = 0; i < size; i++) {
        cout<<arr[i]<<" ";
    }
}
```
