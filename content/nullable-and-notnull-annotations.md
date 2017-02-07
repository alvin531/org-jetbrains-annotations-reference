# @Nullable and @NotNull Annotations

## 简介

本章节讲述了IntelliJ IDEA引入的`@Nullable`和`@NotNull`注解，这两个注解通过 **Constant Conditions & Exceptions（常量条件＆异常）** 和@Nullable问题检查机制来发现NullPointerException（NPE）。

这些注解旨在协助您在方法层次结构中声明契约（Contracts），避免NPE的出现。此外，IntelliJ IDEA还有一个功能：代码审查（Code Inspection）机制会反馈给您，那些声明了契约的方法在定义和调用之间是否存在差异，而且在某些情景下提供了自动处理方案。

这两个注解--@Nullable和@NotNull--审查方法的调用和字段的引用。

## @Nullable

@Nullable注解提示您在以下情况里要进行NPE的检查（即null的判断）：

- 调用的方法可能会返回null。
- 引用的变量（字段，局部变量，参数）可能是null。

## @NotNull

@NotNull注解实际上就是一个显式的契约声明：

- 方法不会返回null。
- 变量（如字段，局部变量，参数）不能是null。

IntelliJ IDEA会警告您是否违反了这些契约。

## 语义说明

一个使用了`@Nullable`注解的元素，表明了null值作为返回值（对于方法）、传递值（对于参数）和引用（对于局部变量和字段）都是合法的。

一个使用了`@NotNull`注解的元素，表明了null值作为返回值（对于方法）、传递值（对于参数）和引用（对于局部变量和字段）是不允许的。

当重写或实现使用了带注解声明或带注解参数的方法时，@Nullable和@NotNull之间是协变-逆变关系。

- 重写或实现使用了带注解声明的方法：

  - 父类方法使有了`@NotNull`注解声明，那么子类方法必须使用`@NotNull`注解声明。
  - 父类方法使用了`@Nullable`注解声明，那么子类方法可以使用`@Nullable`和`@NotNull`注解声明。

- 重写或实现使用了注解参数的方法：

  - 父类方法中的参数使用了`@Nullable`注解，那么子类方法必须使用`@Nullable`注解。
  - 父类方法中的参数使用了`@NotNull`注解，那么子类方法的参数可以使用`@Nullable`或`@NotNull`注解（或不包含任何注解）。
