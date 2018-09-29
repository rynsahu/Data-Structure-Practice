## What is sorting?
Arranging of elements in a particular manner it may be in `ascending` or `descending` order that is called sorting.

## 1. Selection Sort
In this sorting technique, the list is divided into two parts one is sorted and another one is unsorted. Sorted part will be in the left end and unsorted part will be in the right end.
In the set of N elements, we need to find out the location of the minimum element and swap it with the location of the first element and repeat this step for n-1 elements until the list is not sorted.
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

## 2. Bubble Sort
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

## 3. Insertion Sort
#### Program:
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
## 4. Merge Sort
#### Program:
```
#include <iostream>

using namespace std;

void merge(int arrL[], int arrR[],int nL, int nR, int arr[]) {
    int L = 0, R = 0, k = 0;
    while(L < nL && R < nR) {
        if(arrL[L] < arrR[R]) {
            arr[k++] = arrL[L++];
        } else {
            arr[k++] = arrR[R++];
        }
    }
    
    for(; L < nL; L++) {
        arr[k++] = arrL[L];
    }
    
    for(; R < nR; R++) {
        arr[k++] = arrR[R];
    }
    
}

void MergeSort(int arr[], int size) {
    int mid = size/2, 
        sizeL = mid,
        sizeR = size-mid,
        arrL[sizeL], 
        arrR[sizeR];
        
    if(size < 2) {
        return;
    }
    
    for(int i = 0; i<sizeL; i++) {
        arrL[i] = arr[i]; 
    }
    
    for(int i = mid; i<size; i++) {
        arrR[i - mid] = arr[i]; 
    }
    
    MergeSort(arrL, sizeL);
    MergeSort(arrR, sizeR);
    
    merge(arrL, arrR, sizeL, sizeR, arr);
    
}

int main()
{
    int size = 8;
    int arr[size];
    
    for(int i = 0; i<size; i++) {
        cin>>arr[i];
    }
    
    MergeSort(arr, size);
    
    for(int i = 0; i<size; i++) {
        cout<<arr[i];
    }
    
}
```
## 5. Quick Sort
#### Program:
```
#include <iostream>
using namespace std;

int partition(int arr[], int startIndex, int endIndex) {
    int pivot = arr[endIndex];
    int partitionIndex = startIndex;
    int temp;
    
    for(int i=startIndex; i < endIndex; i++) {
        if(arr[i] <= pivot) {
            temp = arr[i];
            arr[i] = arr[partitionIndex];
            arr[partitionIndex] = temp;
            
            partitionIndex++;
        }
    }
    
    temp = arr[partitionIndex];
    arr[partitionIndex] = arr[endIndex];
    arr[endIndex] = temp;
    
    return partitionIndex;
}

void quickSort(int arr[], int startIndex, int endIndex) {
    if(startIndex < endIndex) {
        int partitionIndex = partition(arr, startIndex, endIndex);
    
        quickSort(arr, startIndex, partitionIndex - 1);
        quickSort(arr, partitionIndex + 1, endIndex);
    } 
    
    
}

int main()
{
    int size = 9;
    int arr[size];
    
    for(int i=0; i<size; i++) {
        cin>>arr[i];
    }
    
    quickSort(arr, 0, 8);

    for(int i=0; i<size; i++) {
        cout<<arr[i];
    }    
}
```
