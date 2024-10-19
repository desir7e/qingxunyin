完美整数（基于js，其他都是cpp）

```
function solution(x, y) {
    let count = 0; // 记录完美整数的数量
  
    // 枚举从 1 到 9 的每一个基数
    for (let digit = 1; digit <= 9; digit++) {
      let num = digit; // 当前完美整数
      // 不断生成 1 位到 9 位的完美整数
      while (num <= y) {
        if (num >= x) {
          count++; // 如果完美整数在 [x, y] 范围内，计数
        }
        num = num * 10 + digit; // 扩展生成下一位完美整数
      }
    }
  
    return count;

}

function main() {
    // Add your test cases here
    console.log(solution(1, 10) === 9);
    console.log(solution(2, 22) === 10);
}

main();
```

