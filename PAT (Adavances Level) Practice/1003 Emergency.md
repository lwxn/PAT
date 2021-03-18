```c++
#include <bits/stdc++.h>
#define ll long long
using namespace std;

int main() {
    ll n,m,c1,c2;
    cin>>n>>m>>c1>>c2;

    vector<ll>rescue(n,0);
    vector<vector<ll>>M(n,vector<ll>(n,INT_MAX));
    vector<ll>dis(n,INT_MAX);
    vector<bool>vis(n,false);
    vector<ll>road(n,0);
    vector<ll>weight(n,0);
    for(int i = 0;i<n;i++)
    {
        cin>>rescue[i];
    }

    ll a,b,c;
    for(int i = 0;i<m;i++)
    {
        cin>>a>>b>>c;
        M[a][b] = c;
        M[b][a] = c;
    }


    dis[c1] = 0;
    road[c1] = 1;
    weight[c1] = rescue[c1];
    for(int i = 0;i<n;i++)
    {
        int p = -1;
        int v = INT_MAX;
        for(int j = 0;j<n;j++)
        {
            if(!vis[j] && dis[j] < v)
            {
                v = dis[j];
                p = j;
            }
        }

        if(p != -1)
        {
            vis[p] = 1;
//            cout<<p<<endl;
            for(int k = 0;k<n;k++)
            {
                if(dis[k] > dis[p] + M[p][k])
                {
                    dis[k] = dis[p] + M[p][k];
                    road[k] = road[p];
                    weight[k] = rescue[k] + weight[p];
//                    cout<<k<<" "<<dis[k]<<" "<<road[k]<<endl;
                }
                else if(dis[k] == dis[p] + M[p][k])
                {
                    road[k] += road[p];
                    weight[k] = max(weight[k],rescue[k] + weight[p]) ;
//                    cout<<k<<" "<<dis[k]<<" "<<road[k]<<endl;
                }
            }
        }
    }

    cout<<road[c2]<<" "<<weight[c2]<<endl;
    return 0;
}

/**
5 6 0 2
1 2 1 5 3
0 1 1
0 2 2
0 3 1
1 2 1
2 4 1
3 4 1
 **/
 ```