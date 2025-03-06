---
title: Access Built-in Properties in PowerPoint
linktitle: Access Built-in Properties in PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to access built-in properties in PowerPoint using Aspose.Slides for Java. This tutorial guides you through retrieving author, creation date, and more.
weight: 10
url: /java/java-powerpoint-properties-management/access-built-in-properties-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introduction
In this tutorial, we'll explore how to access built-in properties in PowerPoint presentations using Aspose.Slides for Java. Aspose.Slides is a powerful library that allows Java developers to work with PowerPoint presentations programmatically, enabling tasks such as reading and modifying properties seamlessly.
## Prerequisites
Before we begin, make sure you have the following prerequisites:
1. Java Development Kit (JDK): Ensure that you have JDK installed on your system. You can download it from [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Slides for Java: Download and install Aspose.Slides for Java from [this link](https://releases.aspose.com/slides/java/).

## Import Packages
First, you need to import the necessary packages to your Java project. Add the following import statement at the beginning of your Java file:
```java
import com.aspose.slides.IDocumentProperties;
import com.aspose.slides.Presentation;

```
## Step 1: Set Up the Presentation Object
Start by setting up the Presentation object to represent the PowerPoint presentation you want to work with. Here's how you can do it:
```java
// The path to the directory containing the presentation file
String dataDir = "path_to_your_presentation_directory/";
// Instantiate the Presentation class
Presentation pres = new Presentation(dataDir + "your_presentation_file.pptx");
```
## Step 2: Access the Document Properties
After setting up the Presentation object, you can access the built-in properties of the presentation using the IDocumentProperties interface. Here's how you can retrieve various properties:
### Category
```java
System.out.println("Category : " + documentProperties.getCategory());
```
### Current Status
```java
System.out.println("Current Status : " + documentProperties.getContentStatus());
```
### Creation Date
```java
System.out.println("Creation Date : " + documentProperties.getCreatedTime());
```
### Author
```java
System.out.println("Author : " + documentProperties.getAuthor());
```
### Description
```java
System.out.println("Description : " + documentProperties.getComments());
```
### Keywords
```java
System.out.println("KeyWords : " + documentProperties.getKeywords());
```
### Last Modified By
```java
System.out.println("Last Modified By : " + documentProperties.getLastSavedBy());
```
### Supervisor
```java
System.out.println("Supervisor : " + documentProperties.getManager());
```
### Modified Date
```java
System.out.println("Modified Date : " + documentProperties.getLastSavedTime());
```
#### Presentation Format
```java
System.out.println("Presentation Format : " + documentProperties.getPresentationFormat());
```
### Last Print Date
```java
System.out.println("Last Print Date : " + documentProperties.getLastPrinted());
```
### Shared Between Producers
```java
System.out.println("Is Shared between producers : " + documentProperties.getSharedDoc());
```
### Subject
```java
System.out.println("Subject : " + documentProperties.getSubject());
```
### Title
```java
System.out.println("Title : " + documentProperties.getTitle());
```

## Conclusion
In this tutorial, we learned how to access built-in properties in PowerPoint presentations using Aspose.Slides for Java. By following the steps outlined above, you can easily retrieve various properties such as author, creation date, and title programmatically.
## FAQ's
### Can I modify these built-in properties using Aspose.Slides for Java?
Yes, you can modify these properties using Aspose.Slides. Simply use the appropriate setter methods provided by the IDocumentProperties interface.
### Is Aspose.Slides compatible with different versions of PowerPoint?
Aspose.Slides supports a wide range of PowerPoint versions, ensuring compatibility across various platforms.
### Can I retrieve custom properties as well?
Yes, besides built-in properties, you can also retrieve and modify custom properties using Aspose.Slides for Java.
### Does Aspose.Slides offer documentation and support?
Yes, you can find comprehensive documentation and access support forums on the [Aspose website](https://reference.aspose.com/slides/java/).
### Is there a trial version available for Aspose.Slides for Java?
Yes, you can download a free trial version from [here](https://releases.aspose.com/).

{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
