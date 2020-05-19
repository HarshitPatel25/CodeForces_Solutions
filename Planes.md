#include <iostream>
#include<bits/stdc++.h>

using namespace std;



int main() {

int n=0,m=0;
cin>>n>>m;
vector<int>plane;
vector<int>copy_plane;
int temp=0;
 for(int i=0;i<m;i++){
     cin>>temp;
     plane.push_back(temp);
     copy_plane.push_back(temp);
 }
 int n2 = n;
 int Min=0,Max=0;
 
 sort(plane.begin(),plane.end());
 
 while(n){
     
     
    if(plane[0] > 0){ 
     Min += plane[0];
     plane[0]--;
     n--;
    }
    
    if(plane[0]==0){
        plane.erase(plane.begin());
    }
    
 }
 
// cout<<Max<<"\n";
 
 
 sort(copy_plane.begin(),copy_plane.end(), greater<int>() );
 
 while(n2){
     if(copy_plane[0] > 0){
         Max +=copy_plane[0];
         copy_plane[0]--;
         n2--;
        sort(copy_plane.begin(),copy_plane.end(), greater<int>() );

     }
     
     if(copy_plane[0] == 0){
         copy_plane.erase(copy_plane.begin());
     }
 }
 
 
 cout<<Max<<" "<<Min;
 
	return 0;
}
