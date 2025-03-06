---
title: 访问 PowerPoint 中的内置属性
linktitle: 访问 PowerPoint 中的内置属性
second_title: Aspose.Slides Java PowerPoint 处理 API
description: 了解如何使用 Aspose.Slides for Java 访问 PowerPoint 中的内置属性。本教程将指导您检索作者、创建日期等。
type: docs
weight: 10
url: /zh/java/java-powerpoint-properties-management/access-built-in-properties-powerpoint/
---
## 介绍
在本教程中，我们将探索如何使用 Aspose.Slides for Java 访问 PowerPoint 演示文稿中的内置属性。Aspose.Slides 是一个功能强大的库，允许 Java 开发人员以编程方式处理 PowerPoint 演示文稿，从而无缝地执行读取和修改属性等任务。
## 先决条件
在开始之前，请确保您满足以下先决条件：
1.  Java 开发工具包 (JDK)：确保你的系统上安装了 JDK。你可以从以下网址下载[这里](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides for Java：从以下网站下载并安装 Aspose.Slides for Java[此链接](https://releases.aspose.com/slides/java/).

## 导入包
首先，您需要将必要的包导入到 Java 项目中。在 Java 文件的开头添加以下导入语句：
```java
import com.aspose.slides.IDocumentProperties;
import com.aspose.slides.Presentation;

```
## 步骤 1：设置演示对象
首先设置 Presentation 对象来表示您要处理的 PowerPoint 演示文稿。操作方法如下：
```java
//包含演示文件的目录路径
String dataDir = "path_to_your_presentation_directory/";
//实例化 Presentation 类
Presentation pres = new Presentation(dataDir + "your_presentation_file.pptx");
```
## 步骤 2：访问文档属性
设置 Presentation 对象后，您可以使用 IDocumentProperties 接口访问演示文稿的内置属性。以下是检索各种属性的方法：
### 类别
```java
System.out.println("Category : " + documentProperties.getCategory());
```
### 当前状态
```java
System.out.println("Current Status : " + documentProperties.getContentStatus());
```
### 创建日期
```java
System.out.println("Creation Date : " + documentProperties.getCreatedTime());
```
### 作者
```java
System.out.println("Author : " + documentProperties.getAuthor());
```
### 描述
```java
System.out.println("Description : " + documentProperties.getComments());
```
### 关键词
```java
System.out.println("KeyWords : " + documentProperties.getKeywords());
```
### 最后修改者
```java
System.out.println("Last Modified By : " + documentProperties.getLastSavedBy());
```
### 导师
```java
System.out.println("Supervisor : " + documentProperties.getManager());
```
### 修改日期
```java
System.out.println("Modified Date : " + documentProperties.getLastSavedTime());
```
#### 演示格式
```java
System.out.println("Presentation Format : " + documentProperties.getPresentationFormat());
```
### 最后打印日期
```java
System.out.println("Last Print Date : " + documentProperties.getLastPrinted());
```
### 生产者之间共享
```java
System.out.println("Is Shared between producers : " + documentProperties.getSharedDoc());
```
### 主题
```java
System.out.println("Subject : " + documentProperties.getSubject());
```
### 标题
```java
System.out.println("Title : " + documentProperties.getTitle());
```

## 结论
在本教程中，我们学习了如何使用 Aspose.Slides for Java 访问 PowerPoint 演示文稿中的内置属性。通过遵循上面概述的步骤，您可以轻松地以编程方式检索各种属性，例如作者、创建日期和标题。
## 常见问题解答
### 我可以使用 Aspose.Slides for Java 修改这些内置属性吗？
是的，您可以使用 Aspose.Slides 修改这些属性。只需使用 IDocumentProperties 接口提供的适当 setter 方法即可。
### Aspose.Slides 是否与不同版本的 PowerPoint 兼容？
Aspose.Slides 支持广泛的 PowerPoint 版本，确保跨各种平台的兼容性。
### 我也可以检索自定义属性吗？
是的，除了内置属性之外，您还可以使用 Aspose.Slides for Java 检索和修改自定义属性。
### Aspose.Slides 提供文档和支持吗？
是的，您可以在以下位置找到全面的文档并访问支持论坛：[Aspose 网站](https://reference.aspose.com/slides/java/).
### Aspose.Slides for Java 有试用版吗？
是的，你可以从以下网站下载免费试用版[这里](https://releases.aspose.com/).