#include <iostream>
#include<bits/stdc++.h>

using namespace std;



int main() {

int n=0;
cin>>n;
int arr[n+1];

for(int i=0;i<n;i++){
    
    cin>>arr[i];
}

std::vector<int> sum;
int s = arr[n-1] ,l = arr[0],x=0;

for(int i=1;i<n-2;i++){
    x = max( arr[i] , arr[i+1] );
    sum.push_back(x);
}
 
 int ans=0;
 
 ans  = min(s,l);
 
if(!sum.empty()){
 sort(sum.begin(),sum.end());
 ans = min(ans,sum[0]);
}
 cout<<ans;
 
 
	return 0;
}
