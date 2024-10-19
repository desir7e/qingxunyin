DNA序列还原

```
#include <bits/stdc++.h>
using namespace std;

int solution(std::string dna1, std::string dna2) {
    // Please write your code here
    int n = (int)dna1.size(),m = (int)dna2.size();
    vector<vector<int>>dp(n+1,vector<int>(m+1,0));
    dp[0][0] = 0;//dp[x][y]代表将a字符串前x个字符修改成b字符串前y个字符
    for (int i=1; i<=m; ++i) dp[0][i] = i;
    for (int i=1; i<=n; ++i) dp[i][0] = i;
    for (int i=1; i<=n; ++i) {
        for (int j=1; j<=m; ++j) {
             int one = dp[i-1][j] +1,two = dp[i][j-1]+1,three = dp[i-1][j-1];
             if(dna1[i-1]!=dna2[j-1]) three+=1;
             dp[i][j] = min(min(one,two),three);
         }
    }
    return dp[n][m];
}

int main() {
    //  You can add more test cases here
    std::cout << (solution("AGCTTAGC", "AGCTAGCT") == 2) << std::endl;
    std::cout << (solution("AGCCGAGC", "GCTAGCT") == 4) << std::endl;
    return 0;
}
```

