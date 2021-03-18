```c++
#include <iostream>
#include <bits/stdc++.h>
#include <algorithm>
using namespace std;
vector<int>tree[100];

void bfs(int node)
{
    bool first = 0;
    queue<int>q;
    q.push(node);
    while(!q.empty())
    {
        int len = q.size();
        int leaf = 0;
        for(int i = 0;i<len;i++)
        {
            int top = q.front();
            q.pop();
            if(tree[top].size() == 0) leaf++;
            else
            {
                for(int j = 0;j<tree[top].size();j++)
                {
                    q.push(tree[top][j]);
                }
            }
        }
        if(!first)
        {
            cout<<leaf;
            first = 1;
        }
        else
        {
            cout<<" "<<leaf;
        }

    }
}

int main() {
    int N,M,node,n,c;
    cin>>N>>M;
    for(int i = 0;i<M;i++)
    {
        cin>>node>>n;
        for(int j = 0;j<n;j++)
        {
            cin>>c;
            tree[node].push_back(c);
        }
    }
    bfs(1);
}
```