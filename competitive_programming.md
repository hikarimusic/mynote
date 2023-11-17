# Competitive Programming

## Search / 探索

### Pruning / 枝刈り
```cpp
vector<vector<int>> sol;

bool dfs("<position>") {
    if ("<complete>")
        return true;
    for ("<next step>") {
        if ("<pruning condition>")
            continue;
        "<construct solution>";
        if (dfs("<next position>"))
            return true;
        "<recover solution>";
    }
    return false;
}
```

## Optimization / 最適化

### Dynamic Programming / 動的計画法
```cpp
vector<vector<int>> dp;

void solve() {
    "<initialize>";
    for (int i=1; i<=N; ++i) {
        for (int j=1; j<=M; ++j) {
            dp[i][j] = "<function of dp[i-1][j-1], dp[i-1][j], ...>";
        }
    }
}
```

### Greedy Algorithm / 貪欲法
```cpp
void solve() {
    "<sort>";
    for (int i=0; i<N; ++i) {
        "<construct solution>";
    }
}
```

## Data Structure / データ構造

### Disjoint Set Union / Union-Find 木
```cpp
vector<int> p, s;

void make_set(int v) {
    p[v] = v;
    s[v] = 1;
}

int find_set(int v) {
    if (p[v]==v)
        return v;
    return p[v] = find_set(p[v]);
}

void union_set(int a, int b) {
    a = find_set(a);
    b = find_set(b);
    if (a==b)
        return;
    if (a < b)
        swap(a, b);
    p[b] = a;
    s[a] += s[b];
}
```