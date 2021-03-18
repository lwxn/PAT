```c++
#include <iostream>
#include <algorithm>
#include <bits/stdc++.h>

using namespace std;

int main() {
    int M;
    int h1,h2,m1,m2,s1,s2,h3,m3,s3,h4,m4,s4;
    string id1,id2,id;
    int time1 = INT_MAX,time2 = INT_MIN,time3;
    cin>>M;

    for(int i = 0;i<M;i++)
    {
        cin>>id;
        scanf("%d:%d:%d %d:%d:%d",&h3,&m3,&s3,&h4,&m4,&s4);
        time3 = h3*10000+m3*100+s3;
        if(time3 < time1) {
            id1 = id;
            time1 = time3;
        }
        time3 = h4*10000+m4*100+s4;
        if(time3 > time2)
        {
            id2 = id;
            time2 = time3;
        }
    }

    cout<<id1<<" "<<id2<<endl;
    return 0;
}

/**
3
CS301111 15:30:28 17:00:10
SC3021234 08:00:00 11:25:25
CS301133 21:45:00 21:58:40
 **/
 ```