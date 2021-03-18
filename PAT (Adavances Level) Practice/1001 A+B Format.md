```c++
#include<stdio.h>
#include<iostream>
#include <math.h>

using namespace std;

int main()
{
    int a,b;
    cin>>a>>b;

    int c = a+b;
    int flag = c < 0 ? 1 : 0;
    c = abs(c);

    string s = to_string(c);

    int i = s.size()-1;
    string ans = "";
    while(i>2)
    {
        ans = "," + s.substr(i-2,3) + ans;
        i-=3;
    }
    ans = s.substr(0,i+1) + ans;
    if(flag) cout<<"-";
    cout<<ans<<endl;
    return 0;
}
```