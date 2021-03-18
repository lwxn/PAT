```c++
#include <iostream>
#include <bits/stdc++.h>

using namespace std;

int main() {
    int N;
    cin>>N;
    vector<int>num(N),sum(N,0);
    int ans = INT_MIN,first = 0,second = 0,flag = 0;
    for(int i = 0;i<N;i++)
    {
        cin>>num[i];
        if(num[i]>=0) flag = 1;
    }

    int tmp = 0;
    int t_i = 0;
    for(int i = 0;i<N;i++)
    {
        tmp += num[i];
        if(tmp > ans)
        {
            ans = tmp;
            second = i;
            first = t_i;
        }
        if(tmp < 0 && i+1 < N)
        {
            t_i = i+1;
            tmp = 0;
        }



    }

    if(!flag)
    {
        ans = 0;
        first = 0;
        second = N-1;
    }
    cout<<ans<<" "<<num[first]<<" "<<num[second];
    return 0;
}
/**
10
-10 1 2 3 4 -5 -23 3 7 -21

 2
 -1 0
 **/
 ```