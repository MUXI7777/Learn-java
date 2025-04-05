# 将hex转换成字符数组，再遍历
- 附带抛出异常的操作
```java
for (char c : hex.toCharArray()) {
    if (validHexChars.indexOf(c) == -1) {
        throw new NumberFormatException();
    }
}
```
**hex.toCharArray()**
# 返回一个十进制整数转换成十六进制
```java
Integer.parseInt(hex, 16)
```
