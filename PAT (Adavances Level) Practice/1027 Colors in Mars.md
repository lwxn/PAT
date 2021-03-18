```c++
#include <bits/stdc++.h>

using namespace std;

int main()
{
    int color[3];
    while(cin>>color[0]>>color[1]>>color[2])
    {
        string s = "#";
        for(int temp : color)
        {
            string a = "";
            while(temp)
            {
                int t = temp%13;
                temp/=13;
                a.push_back(t > 9 ? (t - 10) + 'A' : t + '0');
            }
            reverse(a.begin(),a.end());
            if(a.size() == 0) a = "00";
            else if(a.size() == 1) a = '0' + a;
            s = s+a;
        }
        cout<<s<<endl;
    }
    return 0;
}
```