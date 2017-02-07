# @ParametersAreNonnullByDefault Annotation

## 简介

`@ParametersAreNonnullByDefault`注解提供了一个便利，用于为给定的类或包里定义的所有元素（方法、参数、字段和变量）标注上`@NotNull`语义，除非它们使用了`@Nullable`注解进行显式标注。

`@javax.annotation.ParametersAreNonnullByDefault`可用于包、类或方法。

要使用`@javax.annotation.ParametersAreNonnullByDefault`注解，请确保将`jsr305 jars`添加到类库中。

## 示例

分析以下示例：

```java
public static <T extends Comparable<T>> List<T> sort(List<T> list) {
  if (list != null) {
    List<T> copy = new ArrayList<T>(list);
    sort(copy);
    return copy;
  } else {
    return null;
  }
}
```

IntelliJ IDEA不会出现警告。

让我们使用`@ParametersAreNonnullByDefault`注解来装饰`sort()`方法，这意味着此方法的所有符号都是`@NotNull`的。

IntelliJ IDEA会立即识别`if`语句是无关紧要的，因为这个条件永远为`true`：

![notnull default annotation](../assets/images/notnull_default_annotation1.png)

但是，如果将方法`sort()`的参数标注为`@Nullable`，则将看不到检查消息：

![notnull default annotation](../assets/images/notnull_default_annotation2.png)
