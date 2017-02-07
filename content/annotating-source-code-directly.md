# Annotating Source Code Directly

您的源代码可以包含各种注解。例如，当IntelliJ IDEA假定某个元素可以为`Null`时，使用`@Nullable`和`@NotNull`注解。`@NonNls`注解用于忽略硬编码的字符串。

**使用注解**：

1. 确保可以在IntelliJ IDEA安装下的`lib`文件夹中找到的`annotations.jar`，并添加到模块依赖库里。

  对于`@javax.annotation.ParametersAreNonnullByDefault`注解，应将`javax`添加到模块库。

2. 在package/class/field/variable/method/method parameter声明之前引入所需的注解。
