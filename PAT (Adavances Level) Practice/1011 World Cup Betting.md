```c++
#include "bits/stdc++.h"

using namespace std;

char s[] = {'W','T','L'};

int main()
{
    double num,ans = 0.65;
    for(int i = 0;i<3;i++)
    {
        double Max = 0;
        int t = 0;
        for(int j = 0;j<3;j++)
        {
            cin>>num;
            if(num > Max)
            {
                Max = num;
                t = j;
            }
        }
        cout<<s[t]<<" ";
        ans *= Max;
    }
    
    ans = (ans-1)*2;
    printf("%.2f",ans);
    return 0;
}
```