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

void solve() {
    if (dfs("<start position>"))
        "<print solution>";
}
```
