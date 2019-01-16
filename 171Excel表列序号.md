给定一个Excel表格中的列名称，返回其相应的列序号。

例如，
```
    A -> 1
    B -> 2
    C -> 3
    ...
    Z -> 26
    AA -> 27
    AB -> 28 
    ...
```

示例 1:

```
输入: "A"
输出: 1
```

示例 2:

```
输入: "AB"
输出: 28
```
示例 3:

```
输入: "ZY"
输出: 701
```
mycode
```
class Solution {
    public int titleToNumber(String s) {
		char[] arr = s.toCharArray();
		int sum = 0;
		int len = arr.length;
		if(len>1){
			for(int i = 0;i<len;i++){
				int temp =(int)arr[i]-64;
				sum+=Math.pow(26,len-i-1)*temp;
			}
           
		}else{
            int tem =(int)arr[0]-64;
			sum+=tem;
		}
		
		return sum;
    }
}
```
