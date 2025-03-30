#include <iostream>
using namespace std;

void simpleSort(int arr[], int n) {
    for (int i = 0; i < n; i++) {
        for (int j = i + 1; j < n; j++) {
            if (arr[j] < arr[i]) {
                swap(arr[i], arr[j]);
            }
        }
    }
}


void bubbleSort(int arr[], int n) {
    for (int i = 0; i < n - 1; i++) {
        for (int j = 0; j < n - i - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                swap(arr[j], arr[j + 1]);
            }
        }
    }
}

void insertionSort(int arr[], int n) {
    for (int i = 1; i < n; i++) {
        int key = arr[i], j = i - 1;
        while (j >= 0 && arr[j] > key) {
            arr[j + 1] = arr[j];
            j--;
        }
        arr[j + 1] = key;
    }
}

void selectionSort(int arr[], int n) {
    for (int i = 0; i < n - 1; i++) {
        int minIndex = i;
        for (int j = i + 1; j < n; j++) {
            if (arr[j] < arr[minIndex]) {
                minIndex = j;
            }
        }
        swap(arr[i], arr[minIndex]);
    }
}

void printArray(int arr[], int n) {
    for (int i = 0; i < n; i++) {
        cout << arr[i] << " ";
    }
    cout << endl;
}

int main() {
    int n;
    cout << "Enter the number of elements: ";
    cin >> n;

    int arr[100];  
    cout << "Enter the elements: ";
    for (int i = 0; i < n; i++) {
        cin >> arr[i];
    }
    cout << "\nOriginal Array: ";
    printArray(arr, n);

    simpleSort(arr, n);
    cout << "Sorted using Simple Sort: ";
    printArray(arr, n);

    bubbleSort(arr, n);
    cout << "Sorted using Bubble Sort: ";
    printArray(arr, n);

    insertionSort(arr, n);
    cout << "Sorted using Insertion Sort: ";
    printArray(arr, n);

    
    selectionSort(arr, n);
    cout << "Sorted using Selection Sort: ";
    printArray(arr, n);

    return 0;
}

