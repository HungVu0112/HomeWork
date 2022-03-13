# HomeWork

bt2/C

#include <iostream>
#include <string>

const int Max = 100;

using namespace std;

int n,k,a[Max];
char b[Max];
int Check[Max] = {0};

void display2() {
    for(int i=1; i<=k; i++) {
        cout << b[i];
    }
    cout << endl;
}

void display(int f) {
    for (int i = 1; i <= k; i++) {
        if (Check[i]==0) {
            b[f] = a[i] + 96; 
            Check[i] = 1;
            if (f == k)
                display2();
            else display(f + 1);
            Check[i] = 0;
        }
    }
}

void Try(int i) {
    for(int j=a[i-1]+1; j<=n-k+i; j++) {
        a[i] = j;
        if(i==k) display(1);
        else Try(i+1);
    }
}

int main() {
    cin >> n >> k;
    Try(1);
    return 0;
}

  
bt3/C
  
#include <iostream>
#include <string>

const int Max = 100;

using namespace std;

int n,k,a[Max];
char b[Max];

void display() {
    for(int i=1; i<=k; i++) {
        b[i] = a[i] + 96;
    }
    for(int i=1; i<=k; i++) {
        cout << b[i] << " ";
    }
    cout << endl;
}

void Try(int i) {
    for(int j=a[i-1]+1; j<=n-k+i; j++) {
        a[i] = j;
        if(i==k) display();
        else Try(i+1);
    }
}

int main() {
    cin >> n >> k;
    Try(1);
    return 0;
}

  
bt6/C
  

#include<iostream>
#define MAX 20
using namespace std;
 
int n;
int B[MAX] = { 0 };
int A[MAX];
 
void xuat() {
    for (int i = 1; i <= n; i++)
        cout << A[i];
    cout << endl;
}
 
void Try(int k) {
    for (int i = 1; i <= n; i++) {
        if (B[i]==0) {
            A[k] = i; 
            B[i] = 1;
            if (k == n)
                xuat();
            else Try(k + 1);
            B[i] = 0;
        }
    }
}
 
int main() {
    cin >> n;
    Try(1);
}
