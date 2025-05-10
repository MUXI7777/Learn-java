# 在 Java 里，Map 属于一个接口，它代表了**键值对的映射集合**,类似与字典
# 基本概念
Map 接口存储的是键值对，每个键都是唯一的，一个键对应着一个值。它不直接继承自 Collection 接口，不过它和 Collection 框架一同构成了 Java 集合框架。
# 常用实现类
- HashMap：这是最为常用的实现类，它基于哈希表来实现，不保证键值对的顺序。HashMap 允许键和值为 null，并且它的操作（如 put、get）时间复杂度为 O (1)，效率较高。
- TreeMap：基于红黑树实现，能按照键的自然顺序或者自定义的比较器顺序对键值对进行排序。TreeMap 不允许键为 null。
- LinkedHashMap：继承自 HashMap，它维护了一个双向链表，能按照插入顺序或者访问顺序来遍历键值对。
# 常用方法
put(K key, V value)：将指定的键值对存入 Map 中。若键已存在，会更新其对应的值。
get(Object key)：返回指定键所映射的值，若键不存在，则返回 null。
containsKey(Object key)：判断 Map 中是否包含指定的键。
containsValue(Object value)：判断 Map 中是否包含指定的值。
remove(Object key)：移除指定键对应的键值对。
size()：返回 Map 中键值对的数量。
clear()：清空 Map 中的所有键值对。
## 示例代码
```java
import java.util.HashMap;
import java.util.Map;

public class MapExample {
    public static void main(String[] args) {
        // 创建一个 HashMap 对象
        Map<String, Integer> map = new HashMap<>();

        // 添加键值对
        map.put("apple", 1);
        map.put("banana", 2);
        map.put("cherry", 3);

        // 获取指定键的值
        int value = map.get("banana");
        System.out.println("Value of banana: " + value);

        // 判断是否包含指定的键
        boolean containsKey = map.containsKey("apple");
        System.out.println("Contains key 'apple': " + containsKey);

        // 判断是否包含指定的值
        boolean containsValue = map.containsValue(3);
        System.out.println("Contains value 3: " + containsValue);

        // 移除指定键的键值对
        map.remove("cherry");
        System.out.println("Map size after removing 'cherry': " + map.size());

        // 清空 Map
        map.clear();
        System.out.println("Map size after clearing: " + map.size());
    }
}
```
## 代码解释
首先创建了一个 HashMap 对象，它的键是 String 类型，值是 Integer 类型。
运用 put 方法添加键值对。
利用 get 方法获取指定键的值。
通过 containsKey 和 containsValue 方法判断 Map 中是否包含指定的键或值。
使用 remove 方法移除指定键的键值对。
借助 clear 方法清空 Map。
# 遍历 Map
可以使用多种方式遍历 Map，以下是几种常见的方法：
```java
import java.util.HashMap;
import java.util.Map;

public class MapTraversal {
    public static void main(String[] args) {
        Map<String, Integer> map = new HashMap<>();
        map.put("apple", 1);
        map.put("banana", 2);
        map.put("cherry", 3);

        // 方式一：使用 keySet() 遍历键，再通过键获取值
        for (String key : map.keySet()) {
            int value = map.get(key);
            System.out.println(key + ": " + value);
        }

        // 方式二：使用 entrySet() 遍历键值对
        for (Map.Entry<String, Integer> entry : map.entrySet()) {
            String key = entry.getKey();
            int value = entry.getValue();
            System.out.println(key + ": " + value);
        }

        // 方式三：使用 forEach() 方法
        map.forEach((key, value) -> System.out.println(key + ": " + value));
    }
}
```
## 代码解释
方式一：先调用 keySet() 方法获取 Map 中所有键的集合，再对键进行遍历，通过 get 方法获取对应的值。
方式二：调用 entrySet() 方法获取 Map 中所有键值对的集合，接着对键值对进行遍历，通过 getKey() 和 getValue() 方法分别获取键和值。
方式三：使用 forEach() 方法结合 Lambda 表达式来遍历 Map。
