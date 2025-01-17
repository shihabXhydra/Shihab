#include <bits/stdc++.h>
using namespace std;
#define ll long long int
string st(int num, map<string, int> v)
{
    for (auto p : v)
    {
        if (p.second == num)
            return p.first;
    }

    return "";
}

void solve()
{
    int n, trace = 0;
    cin >> n;
    int a[n];
    string s = {"abcdefghijklmnopqrstuvwxyz"};
    for (int &x : a)
        cin >> x;
    map<string, int> m;
    string k, q;

    for (int i = 0; i < n; i++)
    {
        if (a[i] == 0)
        {
            k += s[trace];
            trace++;
        }
        else
        {
            k += st(a[i], m);
        }
        q = k[i];
        m[q]++;
    }
    cout << k << endl;
}
int main()
{
    int t;
    cin >> t;

    while (t--)
        solve();

    return 0;
}
