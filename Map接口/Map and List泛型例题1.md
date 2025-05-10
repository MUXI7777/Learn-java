# 原题
 Java泛型与收集API3_3姓名年龄性别
【问题描述】

用Map存储学生的姓名、年龄和性别等信息，自拟数据将若干学生的信息存储到List<Map<String, Object>>类型的列表中。

按横列对齐的表格样式输出列表中数据。

编写一个方法convert()，将上述列表存储的信息转换为List<Student>类型的数据，其中，Student类中包含学生姓名、年龄和性别等属性，输出列表内容。

【样例】

请输入学生人数：

3

请输入每位同学信息，每个同学一行

每行上的内容依次为：姓名、年龄、性别。用空格分隔：

张三 46 男

李四 42 女

王麻子 13 女

张三    46      男

李四    42      女

王麻子  13      女

张三    46      男

李四    42      女

王麻子  13      女


【样例说明】

斜体部分为用户输入，输出时各列用制表符(TAB)分隔

```java
import java.util.ArrayList;
import java.util.HashMap;
import java.util.List;
import java.util.Map;
import java.util.Scanner;

class Student {
    private String name;
    private int age;
    private String gender;

    public Student(String name, int age, String gender) {
        this.name = name;
        this.age = age;
        this.gender = gender;
    }

    @Override
    public String toString() {
        return name + "\t" + age + "\t" + gender;
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.println("请输入学生人数：");
        int numStudents = scanner.nextInt();
        scanner.nextLine();

        List<Map<String, Object>> studentListMap = new ArrayList<>();
        System.out.println("请输入每位同学信息，每个同学一行");
        System.out.println("每行上的内容依次为：姓名、年龄、性别。用空格分隔：");
        for (int i = 0; i < numStudents; i++) {
            String[] input = scanner.nextLine().split(" ");
            String name = input[0];
            int age = Integer.parseInt(input[1]);
            String gender = input[2];

            Map<String, Object> studentMap = new HashMap<>();
            studentMap.put("name", name);
            studentMap.put("age", age);
            studentMap.put("gender", gender);
            studentListMap.add(studentMap);
        }

        // 输出列表中数据
        for (Map<String, Object> studentMap : studentListMap) {
            System.out.println(studentMap.get("name") + "\t" + studentMap.get("age") + "\t" + studentMap.get("gender"));
        }

        // 转换为 List<Student> 类型的数据
        List<Student> studentList = convert(studentListMap);

        // 输出转换后的列表内容
        for (Student student : studentList) {
            System.out.println(student);
        }
    }

    public static List<Student> convert(List<Map<String, Object>> studentListMap) {
        List<Student> studentList = new ArrayList<>();
        for (Map<String, Object> studentMap : studentListMap) {
            String name = (String) studentMap.get("name");
            int age = (int) studentMap.get("age");
            String gender = (String) studentMap.get("gender");
            studentList.add(new Student(name, age, gender));
        }
        return studentList;
    }
} 
```
