# External Annotations

存在这样一种情景，当需要使用`@Nullable`、`@NotNull`或`@NonNls`标注时，但又要避免写死在源代码里。这可能是一个团队里使用了不同的IDE（例IntelliJ IDEA和Eclipse）；或要标注类库里的类时。

本章节简要描述了外部注解。要了解如何启用，配置和创建外部注解，查阅[Using External Annotation](./using-external-annotations.md)部分。

IntelliJ IDEA建议使用存储在源代码之外的外部注解。有关注解符号的信息存储在XML文件中，而不是源代码中。每个条目将方法参数或返回值映射到所需的注解类。

这个文件命名为`annotations.xml`，并放在依赖于特定注解的来源的路径中。如果注解属于项目配置中的SDK里，则路径将在SDK设置中定义。如果注解与模块相关，则应在模块设置中定义路径。
