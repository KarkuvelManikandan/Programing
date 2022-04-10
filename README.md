# Programing


// 1. PRINT THE LARGEST POSSIBLE FOR THE GIVEN STRING.
// CODE:

#include <iostream>

#include <string>
#include <algorithm>

using namespace std;

int main(){
    string s = "hafd";
    sort(s.begin(), s.end(), greater<int>());
    cout<<s<<endl;
    return 0;
}


// 2. PRINT THE DISTINCT WORD IN THE GIVEN STRING.
// CODE:

#include <iostream>

#include <string>
#include <sstream>
#include <unordered_set>
using namespace std;


void removedupword(string str){
    istringstream ss(str);
    unordered_set<string> hsh;
    
    do{
        string word;
        ss>> word;
        while(hsh.find(word)== hsh.end()){
            cout << word << " ";
            hsh.insert(word);
        }
    }while(ss);
    
}

int main(){
    string str = "This is Zoho and Zoho is Good";
    removedupword(str);
    return 0;
    
}

//3.FIND ONE OF THE MAXIMUM POSSIBLE POLINDROME IN THE GIVEN STRING.
// CODE:

#include <iostream>

#include <string>
#include <sstream>
#include <unordered_set>
using namespace std;


public: string longestPolindrome(string s){
    if(s.length()<= 1)returns;
    int max_length = 1;
    int n = s.length();
    int st = 0, end = 0;
    
    for(int i =0; i < n-1; ++i){
        int l = i; r = i; 
        while(l>=0 && r<n){
            if(s[l]==s[r]){
                l--;r++;
            }
            else break;
        }
        int len = r-l-1;
        if(len> max_length){
            max_length = len;
            st = l+1;
            end = r-1;
        }
    };
    
    
    for(int i =0; i < n-1; ++i){
        int l = i; r = i+1; 
        while(l>=0 && r<n){
            if(s[l]==s[r]){
                l--;r++;
            }
            else break;
        }
        int len = r-l-1;
        if(len> max_length){
            max_length = len;
            st = l+1;
            end = r-1;
        }
    };
    
    return s.substr(st, max_length);
}

// 4. DISPLAY THE DIAGONAL PATTER FOR THE STRING OF ODD LENGTH.
//CODE:
#include <stdio.h>

int main()
{
char a[100];
int i, j, N,x=0;
int f=0;
scanf("%s",a);
for(N=0;a[N];N++);
for(i=1; i<=N; i++)
{
for(j=1; j<=N; j++)
{

if(j==i && (j==N - i + 1))
{
printf("%c",a[x]);f++;
}
else if(j==i)
{
printf("%c",a[x]);f++;
}
else if(j==N - i + 1)
{
printf("%c",a[x]);f++;
}
else
{
printf(" ");
}
if(f>=2){ x++;f=0;}
}
printf("\n");
}
return 0;
}

//5. PRINT THE FOLLOWING PATTERN FOR THE GIVEN N:
//CODE:

#include<iostream>

using namespace std;
int main(){
    int i, j;
    for(i=1; i<=3; i++){
        for(j=1;j<=i;j++){
            cout<<i;
        }
        cout<<"\n";
    }
    return 0;
}


// 6. CHECK WHETHER THE GIVEN STRING HAS CHARACTERS OF EQUAL DIFFERENCE OR UNEQUAL DIFFERENCE
// CODE:

#include<iostream>

using namespace std;
int main(){
    char str1[50], str2[50];
    cout<<"Enter string1: ";
    gets(str1);
    cout<<"Enter string 2: ";
    gets(str2);
    if(strcmp(str1,str2)==0)
    cout<<"Strings are equal!";
    else
    cout<<"Strings are not equal."
    return 0;
}
