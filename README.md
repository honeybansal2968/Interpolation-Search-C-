# Interpolation-Search-C-
Interpolation Search C++


// Intepolation Search

#include <bits/stdc++.h>
using namespace std;

int interpolationSearch(int arr[],int key, int size,int start, int end){
    int pos = start + (key - arr[start]) *(end - start)/(arr[end] - arr[start]);
    if(pos <size){
        if (arr[pos]==key){
            return pos;
        }else if (arr[pos]<key){
            return pos+1;
        }
        return pos-1;
    }
    return -1;
}

int main(){
    int size,key;
    cout<<"Enter Size of array: ";
    cin>>size;
    
    int arr[size];
    cout<<"Enter array elements(Arithematic progression & sorted): ";
    for(int i=0;i<size;++i){
        cin>>arr[i];
    }
    cout<<"Enter key: ";
    cin>>key;
    
    cout<<interpolationSearch(arr,key,size,0, size-1);
    return 0;
}
