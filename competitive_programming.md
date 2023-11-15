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

## Dynamic Programming / 動的計画法

### DP /  DP
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