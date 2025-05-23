---
"description": "了解如何使用 Aspose.Slides for Java 在 Java PowerPoint 演示文稿中启用“推荐只读”属性。遵循我们包含源代码示例的分步指南，增强演示文稿的安全性。"
"linktitle": "Java 幻灯片中的只读推荐属性"
"second_title": "Aspose.Slides Java PowerPoint 处理 API"
"title": "Java 幻灯片中的只读推荐属性"
"url": "/zh/java/presentation-properties/read-only-recommended-properties-in-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java 幻灯片中的只读推荐属性


## Java 幻灯片中启用只读推荐属性的介绍

在本教程中，我们将探索如何使用 Aspose.Slides for Java 为 PowerPoint 演示文稿启用“只读推荐”属性。当您希望鼓励用户在不进行任何更改的情况下查看演示文稿时，“只读推荐”属性非常有用。这些属性建议以只读模式打开演示文稿。我们将为您提供分步指南以及 Java 源代码来实现此目的。

## 先决条件

在开始之前，请确保您的项目中已安装 Aspose.Slides for Java 库。您可以从 [Aspose.Slides for Java 网站](https://products。aspose.com/slides/java/).

## 步骤 1：创建新的 PowerPoint 演示文稿

我们将首先使用 Aspose.Slides for Java 创建一个新的 PowerPoint 演示文稿。如果您已经有演示文稿，可以跳过此步骤。

```java
String outPptxPath = "Your Output Directory" + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
```

在上面的代码中，我们定义了输出 PowerPoint 文件的路径并创建了一个新的演示文稿对象。

## 步骤 2：启用只读推荐属性

现在，让我们为演示文稿启用“只读推荐”属性。

```java
try
{
    pres.getProtectionManager().setReadOnlyRecommended(true);
    pres.save(outPptxPath, SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

在此代码片段中，我们使用 `getProtectionManager().setReadOnlyRecommended(true)` 方法将“只读推荐”属性设置为 `true`。这可确保当有人打开演示文稿时，系统会提示他们以只读模式打开它。

## 步骤 3：保存演示文稿

最后，我们在启用“建议只读”属性的情况下保存演示文稿。

## Java 幻灯片中只读推荐属性的完整源代码

```java
String outPptxPath = "Your Output Directory" + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
try
{
	pres.getProtectionManager().setReadOnlyRecommended(true);
	pres.save(outPptxPath, SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## 结论

在本教程中，您学习了如何使用 Aspose.Slides for Java 为 PowerPoint 演示文稿启用“建议只读”属性。当您希望限制编辑权限并鼓励观众以只读模式使用演示文稿时，此功能非常有用。您还可以通过为演示文稿设置密码来进一步增强安全性。

## 常见问题解答

### 如何禁用“推荐只读”属性？

要禁用“只读推荐”属性，只需使用以下代码：

```java
pres.getProtectionManager().setReadOnlyRecommended(false);
```

### 我可以为“建议只读”演示文稿设置密码吗？

是的，您可以使用 Aspose.Slides for Java 为只读推荐演示文稿设置密码。您可以使用 `setPassword` 方法为演示文稿设置密码。如果设置了密码，即使在只读模式下，用户也需要输入密码才能打开演示文稿。

```java
pres.getProtectionManager().setPassword("YourPassword");
```

记得更换 `"YourPassword"` 使用您想要的密码。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}