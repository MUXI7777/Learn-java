# java怎么判断一个元素是否在列表中
## contains方法
```
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
