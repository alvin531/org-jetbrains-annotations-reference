# Inferring Nullity

## 自动标注元素为nullable和non-null

IntelliJ IDEA可以分析源代码中哪些元素是可以为null的，并标注它们，前提是annotations在项目中可用。

1. 确保将`annotations.jar`添加到项目中。如果还没有，IntelliJ IDEA会建议配置好项目库。 这可以手动（**File | Settings | Project Settings - Inspections - Probable bugs - Constant conditions and exceptions**）或自动完成。

2. 在主菜单上，选择 **Analyze | Infer Nullity**。

3. 在 **Specify Infer Nullity Scope** 界面里，执行以下操作：

  - 选择要推断空值的范围：整个项目，还是当前文件等等。
  - 如果要对test source以及对局部变量（Annotate local variables）执行空值分析，请选中相应的复选框。

  单击“确定”。 IntelliJ IDEA添加注解的import语句（如果需要），并注解参数和变量。

## 示例

分析以下示例：

```java
public Color myMethod() {
  Color color = null;
  return color;
}
```

对此代码进行空值推断，选中 **Annotate local variables** 的复选框。IntelliJ IDEA使用`@Nullable`注解标注方法和局部变量：

```java
@Nullable
public Color myMethod() {
  @Nullable Color color = null;
  return color;
}
```

但是，如果在初始代码中，变量使用某个具体的值而不是null进行初始化，则方法和局部变量将使用`@NotNull`注解进行标注：

```java
@NotNull
public Color myMethod() {
  @NotNull Color color = new Color(255);
  return color;
}
```
