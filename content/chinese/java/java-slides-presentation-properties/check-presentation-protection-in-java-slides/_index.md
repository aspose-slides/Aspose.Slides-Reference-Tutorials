---
title: 检查 Java 幻灯片中的演示保护
linktitle: 检查 Java 幻灯片中的演示保护
second_title: Aspose.Slides Java PowerPoint 处理 API
description: 了解如何使用 Aspose.Slides for Java 检查 Java 幻灯片中的演示文稿保护。本分步指南提供了写和开放保护检查的代码示例。
type: docs
weight: 15
url: /zh/java/presentation-properties/check-presentation-protection-in-java-slides/
---

## 在 Java 幻灯片中检查演示保护简介

在本教程中，我们将探讨如何使用 Aspose.Slides for Java 检查演示保护。我们将介绍两种情况：检查演示文稿的写保护和检查打开保护。我们将为每个场景提供分步代码示例。

## 先决条件

在开始之前，请确保您已在 Java 项目中设置了 Aspose.Slides for Java 库。您可以从 Aspose 网站下载它并将其添加到项目的依赖项中。

### Maven依赖

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>your_version_here</version>
</dependency>
```

代替`your_version_here`与您正在使用的 Aspose.Slides for Java 版本。

## 第 1 步：检查写保护

要检查演示文稿是否受密码写保护，您可以使用`IPresentationInfo`界面。这是执行此操作的代码：

```java
//源演示文稿的路径
String pptxFile = "path_to_presentation.pptx";

//通过IPresentationInfo接口检查写保护密码
IPresentationInfo presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptxFile);
boolean isWriteProtectedByPassword = presentationInfo.isWriteProtected() == NullableBool.True
        && presentationInfo.checkWriteProtection("password_here");

System.out.println("Is presentation write protected by password = " + isWriteProtectedByPassword);
```

代替`"path_to_presentation.pptx"`与演示文稿文件的实际路径和`"password_here"`与写保护密码。

## 步骤 2：检查开放保护

要检查演示文稿是否受打开密码保护，您可以使用`IPresentationInfo`界面。这是执行此操作的代码：

```java
//源演示文稿的路径
String pptFile = "path_to_presentation.ppt";

//通过 IPresentationInfo 接口检查演示开放保护
presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptFile);
if (presentationInfo.isPasswordProtected()) {
    System.out.println("The presentation is protected by password to open.");
}
```

代替`"path_to_presentation.ppt"`与演示文稿文件的实际路径。

## Java 幻灯片中检查演示保护的完整源代码

```java
//源演示的路径
String pptxFile = RunExamples.getDataDir_PresentationProperties() + "modify_pass2.pptx";
String pptFile = RunExamples.getDataDir_PresentationProperties() + "open_pass1.ppt";
//通过IPresentationInfo接口检查写保护密码
IPresentationInfo presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptxFile);
boolean isWriteProtectedByPassword = presentationInfo.isWriteProtected() == NullableBool.True && presentationInfo.checkWriteProtection("pass2");
System.out.println("Is presentation write protected by password = " + isWriteProtectedByPassword);
//通过IProtectionManager接口检查写保护密码
Presentation presentation = new Presentation();
try
{
	boolean isWriteProtected = presentation.getProtectionManager().checkWriteProtection("pass2");
	System.out.println("Is presentation write protected = " + isWriteProtected);
}
finally
{
	if (presentation != null) presentation.dispose();
}
//通过 IPresentationInfo 接口检查演示开放保护
presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptFile);
if (presentationInfo.isPasswordProtected())
{
	System.out.println("The presentation '" + pptxFile + "' is protected by password to open.");
}
```

## 结论

在本教程中，我们学习了如何使用 Aspose.Slides for Java 检查 Java 幻灯片中的演示保护。我们讨论了两种场景：检查写保护和检查开放保护。您现在可以将这些检查集成到您的 Java 应用程序中，以有效地处理受保护的演示文稿。

## 常见问题解答

### 如何获取 Java 版 Aspose.Slides？

您可以从 Aspose 网站下载 Aspose.Slides for Java 或将其添加为项目中的 Maven 依赖项，如先决条件部分所示。

### 我可以同时检查演示文稿的写保护和打开保护吗？

是的，您可以使用提供的代码示例检查演示文稿的写保护和打开保护。

### 忘记保护密码怎么办？

如果您忘记了演示文稿的保护密码，则没有内置方法可以恢复它。请务必记录您的密码以避免此类情况的发生。

### Aspose.Slides for Java 是否与最新的 PowerPoint 文件格式兼容？

是的，Aspose.Slides for Java 支持最新的 PowerPoint 文件格式，包括 .pptx 文件。