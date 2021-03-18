```c++
#include "bits/stdc++.h"

using namespace std;

struct Stu
{
    string name,id;
    int grade;
    Stu(string a,string b,int c):name(a),id(b),grade(c){}
};

int cmp(const Stu & a,const Stu & b)
{
    return a.grade > b.grade;
}

int main()
{
    int N,grade,grade1,grade2;
    string id,name;
    
    cin>> N;
    vector<Stu>stus;
    vector<Stu>stut;
    for(int i = 0;i<N;i++)
    {
        cin>>name>>id>>grade;
        stus.push_back(Stu(name,id,grade));
    }
    cin>>grade1>>grade2;
    
    
    for(Stu a : stus)
    {
        if(a.grade >= grade1 && a.grade <= grade2)
        {
            stut.push_back(a);
        }
    }
    
    if(stut.size() == 0) cout<<"NONE"<<endl;
    else{
        sort(stut.begin(),stut.end(),cmp);
        for(Stu a : stut)
        {
            cout<<a.name<<" "<<a.id<<endl;
        }
    }
    
    

    return 0;
}
```