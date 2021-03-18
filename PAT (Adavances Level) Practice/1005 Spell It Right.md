```c++
#include<bits/stdc++.h>
#include<algorithm>

using namespace std;

string num[10] = {"zero","one","two","three","four","five","six","seven","eight","nine"};
vector<int>ans;

int main()
{
    int a,sum = 0;
    string N;
    cin>>N;

    for(int i = 0;i<N.size();i++)
    {
        sum += N[i]-'0';
    }
    
    if(!sum)
    {
        ans.push_back(sum);
    }
    while(sum)
    {
        a = sum%10;
        sum/=10;
        ans.push_back(a);
    }

    int len = ans.size();
    cout<<num[ans[len-1]];
    for(int i = ans.size()-2;i>=0;i--)
    {
        cout<<" "<<num[ans[i]];
    }
    return 0;
}
```