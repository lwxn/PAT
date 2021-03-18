```c++
#include "bits/stdc++.h"

using namespace std;

int main()
{
    string s1,s2,ans = "";
    cin>>s1>>s2;
    
    
    int i = 0,j = 0;
    set<char>ss;
    while(i < s1.size() && j < s2.size())
    {
        if(s1[i] == s2[j])
        {
            while(j < s2.size() && s1[i] == s2[j])
            {
                i++;
                j++;
            }
        }
        else
        {
            if(isalpha(s1[i])) s1[i] = toupper(s1[i]);
            if(!ss.count(s1[i]))
            {
                ss.insert(s1[i]);
                ans.push_back(s1[i]);
            }
            i++;
        }
        
    }
    while(i < s1.size())
    {
        if(isalpha(s1[i])) s1[i] = toupper(s1[i]);
        if(!ss.count(s1[i]))
        {
            ss.insert(s1[i]);
            ans.push_back(s1[i]);
        }
        i++;
    }
    cout<<ans<<endl;
    return 0;
}
```