```c++
#include <iostream>
#include <bits/stdc++.h>

using namespace std;

bool isMatch(char c)
{
    return c == 'P' || c == 'A' || c == 'T' || c == 'e' || c == 's' || c == 't';
}

char m[] = {'P','A','T','e','s','t'};

int main() {
    string s;
    int cnt = 0;
    while(cin>>s)
    {
        map<char,int>mp;
        for(int i = 0;i<s.size();i++)
        {
            if(isMatch(s[i]))
            {
                mp[s[i]]++;
                cnt++;
            }
        }
        while(cnt)
        {
            for(int i = 0;i<strlen(m);i++)
            {
                if(mp.count(m[i]) && mp[m[i]]>0)
                {
                    cout<<m[i];
                    cnt--;
                    mp[m[i]]--;
                }
            }
        }
    }
    return 0;
}
/*
 * redlesPayBestPATTopTeePHPereatitAPPT
 * PATest
 */
 ```