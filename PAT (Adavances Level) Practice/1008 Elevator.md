```c++
#include <iostream>
#include <bits/stdc++.h>
using namespace std;

int main() {
    int N,sum = 0,now = 0,temp;
    cin>>N;
    vector<int>a(N,0);
    for(int i = 0;i<N;i++)
    {
        cin>>a[i];
    }
    sum += N*5;
    
    for(int num : a)
    {
        temp = num - now;
        sum += temp > 0 ? temp*6 : -temp*4;
        now = num;
    }
    cout<<sum<<endl;

    return 0;
}
```