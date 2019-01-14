给定一个正整数，返回它在 Excel 表中相对应的列名称。

例如，
```
    1 -> A
    2 -> B
    3 -> C
    ...
    26 -> Z
    27 -> AA
    28 -> AB 
    ...
```
示例 1:
```
输入: 1
输出: "A"
示例 2:

输入: 28
输出: "AB"
示例 3:

输入: 701
输出: "ZY"
```

mycode
```
class Solution {
    public String convertToTitle(int n) {
         StringBuilder sb=new StringBuilder();
        while(n>26){
            int num=n%26;
            n=n/26;
            if(num==0){
                num=26;
                n=n-1;
            }
            char letter=(char)(num+64);
            sb.insert(0,letter);
        }
        char letter=(char)(n+64);
        sb.insert(0,letter);
        return sb.toString();
    }
}
```
