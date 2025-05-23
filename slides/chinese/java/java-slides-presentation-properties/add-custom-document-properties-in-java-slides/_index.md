---
"description": "了解如何使用 Java Slides 中的自定义文档属性增强 PowerPoint 演示文稿。本指南包含使用 Aspose.Slides for Java 的代码示例，并提供了分步指南。"
"linktitle": "在 Java Slides 中添加自定义文档属性"
"second_title": "Aspose.Slides Java PowerPoint 处理 API"
"title": "在 Java Slides 中添加自定义文档属性"
"url": "/zh/java/presentation-properties/add-custom-document-properties-in-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java Slides 中添加自定义文档属性


## Java Slides 中添加自定义文档属性的简介

在本教程中，我们将引导您使用 Aspose.Slides for Java 向 PowerPoint 演示文稿添加自定义文档属性。自定义文档属性允许您存储有关演示文稿的其他信息，以供参考或分类。

## 先决条件

在开始之前，请确保您已在 Java 项目中安装并设置了 Aspose.Slides for Java 库。

## 步骤1：导入所需的包

```java
import com.aspose.slides.*;
```

## 第 2 步：创建新演示文稿

首先，你需要创建一个新的展示对象。具体操作如下：

```java
// 文档目录的路径。
String dataDir = "Your Document Directory";

// 实例化 Presentation 类
Presentation presentation = new Presentation();
```

## 步骤3：获取文档属性

接下来，您将检索演示文稿的文档属性。这些属性包括标题、作者等内置属性，以及您可以添加的自定义属性。

```java
// 获取文档属性
IDocumentProperties documentProperties = presentation.getDocumentProperties();
```

## 步骤 4：添加自定义属性

现在，让我们向演示文稿添加自定义属性。自定义属性由名称和值组成。您可以使用它们来存储所需的任何信息。

```java
documentProperties.set_Item("New Custom", 12);
documentProperties.set_Item("My Name", "Mudassir");
documentProperties.set_Item("Custom", 124);
```

## 步骤 5：获取特定索引处的属性名称

您还可以检索特定索引处的自定义属性的名称。如果您需要处理特定属性，这将非常有用。

```java
// 获取特定索引处的属性名称
String getPropertyName = documentProperties.getCustomPropertyName(2);
```

## 步骤 6：删除选定的属性

如果要删除自定义属性，可以通过指定其名称来实现。这里，我们删除的是在步骤 5 中获得的属性。

```java
// 删除选定的属性
documentProperties.removeCustomProperty(getPropertyName);
```

## 步骤 7：保存演示文稿

最后，将添加和删除的自定义属性的演示文稿保存到文件中。

```java
// 保存演示文稿
presentation.save(dataDir + "CustomDocumentProperties_out.pptx", SaveFormat.Pptx);
```

## 在 Java 幻灯片中添加自定义文档属性的完整源代码

```java
// 文档目录的路径。
String dataDir = "Your Document Directory";
// 实例化 Presentation 类
Presentation presentation = new Presentation();
// 获取文档属性
IDocumentProperties documentProperties = presentation.getDocumentProperties();
// 添加自定义属性
documentProperties.set_Item("New Custom", 12);
documentProperties.set_Item("My Name", "Mudassir");
documentProperties.set_Item("Custom", 124);
// 获取特定索引处的属性名称
String getPropertyName = documentProperties.getCustomPropertyName(2);
// 删除选定的属性
documentProperties.removeCustomProperty(getPropertyName);
// 保存演示文稿
presentation.save(dataDir + "CustomDocumentProperties_out.pptx", SaveFormat.Pptx);
```

## 结论

您已经学习了如何使用 Aspose.Slides 在 Java 中向 PowerPoint 演示文稿添加自定义文档属性。自定义属性对于存储与演示文稿相关的其他信息非常有用。您可以根据具体用例的需要扩展此知识，添加更多自定义属性。

## 常见问题解答

### 如何检索自定义属性的值？

要检索自定义属性的值，您可以使用 `get_Item` 方法 `documentProperties` 对象。例如：

```java
Object customPropertyValue = documentProperties.get_Item("New Custom");
```

### 我可以添加不同数据类型的自定义属性吗？

是的，您可以添加各种数据类型的自定义属性，包括数字、字符串、日期等，如示例所示。Aspose.Slides for Java 可以无缝处理各种数据类型。

### 我可以添加的自定义属性数量有限制吗？

您可以添加的自定义属性数量没有严格限制。但是，请注意，添加过多的属性可能会影响演示文稿文件的性能和大小。

### 如何列出演示文稿中的所有自定义属性？

您可以循环遍历所有自定义属性来列出它们。以下是操作示例：

```java
for (int i = 0; i < documentProperties.getCustomCount(); i++) {
    String propertyName = documentProperties.getCustomPropertyName(i);
    Object propertyValue = documentProperties.get_Item(propertyName);
    System.out.println("Property Name: " + propertyName);
    System.out.println("Property Value: " + propertyValue);
}
```

此代码将显示演示文稿中所有自定义属性的名称和值。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}