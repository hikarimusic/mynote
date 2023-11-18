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

## Graph / グラフ

### Dijkstra Algorithm / ダイクストラ法
```cpp
vector<int> d;
vector<bool> u;

void dijkstra() {
    d.assign(n, INF);
    u.assign(n, 0);
    d[0] = 0;
    for (int i=0; i<N; ++i) {
        int v = -1;
        for (int j=0; j<N; ++j) {
            if (u[j])
                continue;
            if (v==-1 || d[j]<d[v])
                v = j;
        }
        if (d[v]==INF)
            break;
        u[v] = 1;
        for (int j=0; j<N; ++j) {
            d[j] = min(d[j], d[v]+g[v][j]);
        }
    }
}
```