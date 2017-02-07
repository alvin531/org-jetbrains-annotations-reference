# Annotating Source Code 使用jetbrains annotations来注解您的代码

本教程主要讲解IntelliJ IDEA的annotations工具包的基本使用，分以下几个章节进行描述：

- Enabling Annotations：引入jetbrains annotations。

- @Nullable and @NotNull annotations：使用`@Nullable`和`@NotNull`注解，可以让IntelliJ IDEA检查某个元素是否可以为`Null`。

- @NonNls annotation：`@NonNls`注解，用于忽略硬编码的字符串文字，即说明不需要本地化字符串（No National Language Support）。

- @Contract annotations：`@Contract`注解，这是一个强大而灵活的工具，能让API更安全。

- Annotating Source Code Directly：直接注解源代码，描述如何向源代码添加注解。

- Inferring Nullity：Null推理，它描述了如何对源代码进行分析，进行自动的`@Nullable`和`@NotNull`注解源码。

除此之外，还提供了以下信息：

- External Annotations：使用外部注解，可以进行源码和注解的分离，解藕。

- Using External Annotations：如何使用外部注解。
