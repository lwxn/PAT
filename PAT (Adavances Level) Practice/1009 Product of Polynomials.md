```c++
#include<bits/stdc++.h>

using namespace std;

int main()
{
    int N1,N2;
    double e,c;
    map<double,double,greater<double>>mp;

    cin>>N1;
    vector<double>e1(N1,0),c1(N1,0);
    for(int i = 0;i<N1;i++)
    {
        cin>>e1[i]>>c1[i];
    }

    cin>>N2;
    vector<double>e2(N2,0),c2(N2,0);
    for(int i = 0;i<N2;i++)
    {
        cin>>e2[i]>>c2[i];
    }


    for(int i = 0;i<N1;i++)
    {
        for(int j = 0;j<N2;j++)
        {
            mp[e1[i] + e2[j]] += c1[i] * c2[j];
        }
    }

    int cnt = 0;
    for(map<double,double>::iterator it = mp.begin();it != mp.end();it++)
    {
        if(it->second)
        {
            cnt++;
        }
    }
    
    cout<<cnt;
    for(map<double,double>::iterator it = mp.begin();it != mp.end();it++)
    {
        if(it->second)
        {
            printf(" %.0f %.1f",it->first,it->second);
        }
            
    }
    return 0;
}
/**
2 1 2.4 0 3.2
2 2 1.5 1 0.5
 **/
 ```