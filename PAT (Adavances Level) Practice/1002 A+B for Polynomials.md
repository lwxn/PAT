```c++
#include<stdio.h>
#include<iostream>
#include <bits/stdc++.h>

using namespace std;

int main()
{
    int n1,n2;
    int a;
    double b;
    map<int,double,greater<int>>mp;
    cin>>n1;
    for(int i = 0;i<n1;i++)
    {
        cin>>a>>b;
        mp[a] += b;
    }


    cin>>n2;
    for(int i = 0;i<n2;i++)
    {
        cin>>a>>b;
        mp[a] += b;
    }

    int len = 0;
    for(map<int,double,greater<int>>::iterator it = mp.begin();it != mp.end();it++)
    {
        if(it->second!=0)
        {
           len++;
        }
    }

    cout<<len;
    if(len)
    {
        for(map<int,double,greater<int>>::iterator it = mp.begin();it != mp.end();it++)
        {
            if(it->second!=0)
            {
                printf(" %d %.1f",it->first,it->second);
            }
        }
    }


    return 0;
}
/**
2 1 2.4 0 3.2
2 2 1.5 1 0.5
 **/
 ```