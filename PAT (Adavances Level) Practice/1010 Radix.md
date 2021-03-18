```c++
#include <iostream>
#include "bits/stdc++.h"
#define ll long long

using namespace std;

ll change(string num,ll raddix)
{
    ll sum = 0;
    ll temp = 1;
    for(int i = num.size()-1;i>=0;i--)
    {
        if(isalpha(num[i]))
        {
            sum += (num[i] - 'a' + 10)*temp;
        }
        else
        {
            sum += (num[i] - '0')*temp;
        }
        temp *= raddix;
    }
    return sum;
}


int main() {
    string N1,N2;
    int flag,radix;

    cin>>N1>>N2>>flag>>radix;

    if(flag == 2) swap(N1,N2);

    ll sum1 = change(N1,radix);
    ll sum2;
    char maxc = '0';
    ll low,flag1 = 0,high;
    for(char c : N2)
    {
        maxc = max(maxc,c);
    }
    low = isdigit(maxc) ? maxc - '0' + 1 : maxc - 'a' + 11;
    high = max(low,sum1);

    while(low <= high)
    {
        ll mid = low + (high-low)/2;
        sum2 = change(N2,mid);
        if(sum2 == sum1)
        {
            cout<<mid;
            flag1 = 1;
            high = mid-1;
        }
        else if(sum2 >sum1 || sum2 < 0) high = mid - 1;
        else if(sum2 < sum1) low = mid + 1;
    }

    if(!flag1) cout<<"Impossible";
    return 0;
}

/**
0 000 1 10
 **/
 ```