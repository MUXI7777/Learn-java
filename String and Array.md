# String的基本操作
## .substring(),存在两种重载方式
### substring(int beginIndex)：从指定的 beginIndex 位置开始，一直截取到字符串的末尾。
### substring(int beginIndex, int endIndex)：从 beginIndex 位置开始截取，到 endIndex - 1 位置结束。
# java怎么判断一个元素是否在列表中
## contains方法
```java
import java.util.ArrayList;
import java.util.List;

public class ListContainsExample {
    public static void main(String[] args) {
        List<String> list = new ArrayList<>();
        list.add("apple");
        list.add("banana");
        list.add("cherry");

        String element = "banana";
        boolean isPresent = list.contains(element);
        if (isPresent) {
            System.out.println(element + " 存在于列表中。");
        } else {
            System.out.println(element + " 不存在于列表中。");
        }
    }
}
```
## 手动遍历 
