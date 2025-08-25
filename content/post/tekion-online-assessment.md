+++
title = 'Tekion Online Assessment'
date = 2025-08-24T18:25:20+05:30
draft = false
tags = ['tech', 'college', 'hiring']
+++
Compensation: 20 LPA (if converted)

Stipend: 65k per month

## Online assessment
2 DSA problems 

Easy + Hard was mentioned.
"Easy" was actually "medium".

20 MCQ on core subjects

## DSA 1:
arr = [2, 4, 6, 8, 10], k = 4

Find number of pairs (i,j) such that:

a = arr[i], b = arr[j]

set_bits(a & b) + set_bits(a | b) >= k

```
4 -> 100 (set bits are 1)

6 -> 110 (set bits are 2)

10 -> 1010 (set bits are 2)

```

### Solution:
dp[bits] = number of elements which have `bits` set bits

Given that:
0 <= k <= 100

n <= 3000

arr[i] <= 3000

```
[0 1 2 3 4 5] <- bits

[0 3 2 3 0 0] <- dp
```

This solution works in O(100 * 100) == O(1e4) == O(1)

if (2 * bits >= k) res += nC2

for i:=max(bits+1, req); i<=100; i++

    res += dp[i] * dp[j]

### Result
First I made a brute-force solution which passed 7/15 test-cases.
Then solved MCQs and glanced at the 2nd DSA problem.
Then came back to this problem and passed all test-cases.

## DSA 2:
You are given an array arr, say

arr = [2, 3, 2]

Breaking an array means you create array a and b such that:

a and b are of size n = arr.size()

a is non-decreasing

b is non-increasing

a[i] + b[i] == arr[i]

for arr = [2, 3, 2],
a possible break may be like the following

```
a = [0, 1, 2]

b = [2, 2, 0]
```

Find number of ways to break array arr int array a and array b.
As the answer may be very large use MOD = 1e9 + 7

### Solution:
```cpp
#include <bits/stdc++.h>
using namespace std;

typedef long long ll;

const ll MOD = 1e9+7;

ll rec(ll idx, vector<ll>& b, vector<ll>& c, vector<int>& arr) {
    if (idx >= arr.size()) return 1LL;

    ll prev_b = b.back();
    ll prev_c = c.back();
    ll req = arr[idx];

    ll ways_to_break = 0;

    for (int i=prev_b; i<=req; i++) {
        ll new_b = i;
        ll new_c = req - new_b;

        if (new_c > prev_c) continue;

        b.push_back(new_b);
        c.push_back(new_c);

        ll ways = rec(idx+1, b, c, arr) % MOD;

        ways_to_break = (ways_to_break%MOD + ways%MOD) % MOD;

        /*
            This was probably what was needed to be written
            b.pop_back();
            c.pop_back();
        */
    }

    return ways_to_break % MOD;
}

int solve() {
    ll n; cin >> n;

    vector<int> arr(n);
    for (auto &ele : arr) cin >> ele;

    vector<ll> b;
    b.push_back(0);
    vector<ll> c;
    c.push_back(3001);

    int ans = rec(0, b, c, arr) % MOD;

    return ans;
    

}

int main() {
ios_base::sync_with_stdio(false); cin.tie(NULL);
    cout << solve() << "\n";
}
```

### Result
When I first glanced at this problem. I just returned n, which passed 0/15 test-cases.
Then I returned n+1, which passed 1 test-case.

> I did this because in case I'm unable to solve this problem and some other person also solves the same number of test-cases as me. 
> Then time would be the deciding factor. Thus I make a brute-force or random solution as quickly as possible.

Then I tried solving it and came up with an approach to prune branches.

It only passed 5/15 test-cases, I think the problem was with the MOD.
