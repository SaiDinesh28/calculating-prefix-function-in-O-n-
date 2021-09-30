#include<bits/stdc++.h>
using namespace std;
#define mod 1000000007
#define lli long long 
// vector<int> prefix_function(string s) {
//     int n = (int)s.length();
//     vector<int> pi(n);
//     for (int i = 0; i < n; i++)
//         for (int k = 0; k <= i; k++)
//             if (s.substr(0, k) == s.substr(i-k+1, k))
//                 pi[i] = k;
//     return pi;
// }
vector<int> prefix_function(string s){
        int n=(int)s.length();
        vector<int>pi(n);int j;
        for(int i=1;i<n;i++){
             j=pi[i-1];
             while(j>0 && s[i]!=s[j]) j=pi[j-1];
             if(s[i]==s[j]) j++;
             pi[i]=j;
        }
        return pi;
}
int main(){
        string s;
        cin>>s;
       // cout<<s.substr(5,2)<<endl;
        vector<int>v(s.size());
        v=prefix_function(s);
        for(auto i:v){
                cout<<i<<" ";
        }
}
