```c++
#include "bits/stdc++.h"

using namespace std;

struct Stu
{
    string id,name;
    int grade;
    Stu(string a,string b,int c):id(a),name(b),grade(c){}
};

int cmp1(const Stu & a,const Stu & b)
{
    return a.id<b.id;
}

int cmp2(const Stu & a,const Stu & b)
{
    if(a.name == b.name) return a.id < b.id;
    return a.name < b.name;
}

int cmp3(const Stu & a,const Stu & b)
{
    if(a.grade == b.grade) return a.id < b.id;
    return a.grade < b.grade;
}

int main()
{
    int N,C,grade;
    string id,name;
    while(cin>>N>>C)
    {
        vector<Stu>stus;
        for(int i = 0;i<N;i++)
        {
            cin>>id>>name>>grade;
            stus.push_back(Stu(id,name,grade));
        }
        if( C == 1) sort(stus.begin(),stus.end(),cmp1);
        else if(C == 2) sort(stus.begin(),stus.end(),cmp2);
        else sort(stus.begin(),stus.end(),cmp3);
        
        for(int i = 0;i<N;i++)
        {
            cout<<stus[i].id<<" "<<stus[i].name<<" "<<stus[i].grade<<endl;
        }
    }
    return 0;
}
```