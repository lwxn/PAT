```c++
#include "bits/stdc++.h"

using namespace std;

int main()
{
    long N1,N2;
    cin>>N1;
    
    vector<long>num1(N1);
    for(int i = 0;i<N1;i++)
    {
        cin>>num1[i];
    }
    
    cin>>N2;
    vector<long>num2(N2);
    for(int i = 0;i<N2;i++)
    {
        cin>>num2[i];
    }
    
    int i = 0,j = 0,t = 0;
    int mid = (N1 + N2 + 1)/2;
    long flag;
    while(t < mid)
    {
        if(i < N1 && j < N2)
        {
            if(num1[i] < num2[j])
            {
                flag = num1[i];
                i++;
            }
            else
            {
                flag = num2[j];
                j++;
            }
        }
        else if(i < N1)
        {
            flag = num1[i+mid-t-1];
            i++;
            
        }
        else
        {
            flag = num2[j+mid-t-1];
            j++;
        }
        t++;
    }
    cout<<flag<<endl;
    
    return 0;
}
```