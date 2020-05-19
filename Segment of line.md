#include <iostream>
#include<bits/stdc++.h>


using namespace std;

int main() {

int n=0;
cin>>n;

vector<pair<int,int>>p;
int x=0,y=0;
for(int i=0;i<n;i++){
    cin>>x>>y;
    p.push_back(make_pair(x,y));
}

int MaxIndex=0, MinIndex=0;


for(int i = 1; i < n; i++)
{
    if(p[MaxIndex].second < p[i].second)
    {
        MaxIndex = i;
    }
    else if(p[MaxIndex].second == p[i].second){
        
        MaxIndex =p[MaxIndex].first <p[i].first ?MaxIndex :i;
    }
}

for(int i = 1; i < n; i++)
{
    if(p[MinIndex].first > p[i].first)
    {
        MinIndex = i;
    }
    
     else if(p[MinIndex].first == p[i].first){
        
        MinIndex =p[MinIndex].second > p[i].second ?MinIndex : i;
    }
}
 
if(MaxIndex == MinIndex){
  cout<<MinIndex+1;
}
else{
    cout<<-1;
}


	return 0;
}
