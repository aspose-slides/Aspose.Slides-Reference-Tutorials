---
title: Save PowerPoint with Default Regular Font using Java
linktitle: Save PowerPoint with Default Regular Font using Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to manipulate PowerPoint presentations programmatically using Aspose.Slides for Java. Master Java PowerPoint handling with step-by-step tutorials.
weight: 12
url: /java/java-powerpoint-text-font-customization/save-powerpoint-default-regular-font-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introduction
In the realm of Java development, creating and manipulating PowerPoint presentations programmatically can greatly enhance productivity and customization options. Aspose.Slides for Java is a robust library that empowers developers to efficiently handle PowerPoint files, offering a comprehensive set of features from simple modifications to complex presentations.
## Prerequisites
Before diving into using Aspose.Slides for Java, ensure you have the following prerequisites set up:
1. Java Development Kit (JDK): Aspose.Slides for Java requires JDK 1.8 or above to function correctly.
2. Aspose.Slides for Java JAR: Download the latest version of Aspose.Slides for Java from [here](https://releases.aspose.com/slides/java/).
3. Integrated Development Environment (IDE): Use IntelliJ IDEA, Eclipse, or another Java IDE of your choice.
4. Basic Understanding of Java: Familiarity with Java programming language fundamentals is necessary.

## Import Packages
To begin using Aspose.Slides for Java, import the necessary packages:
```java
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.PdfOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```
This ensures that you have access to all classes and methods provided by Aspose.Slides for Java.
## Step 1: Set Up Your Project
First, create a new Java project in your IDE and include the Aspose.Slides for Java JAR file in your project's build path.
## Step 2: Initialize Presentation Object
Instantiate a `Presentation` object by loading an existing PowerPoint file (.pptx) from your local directory.
```java
String dataDir = "Your Document Directory";
String outPath = "Your Output Directory";
// Load presentation
Presentation pres = new Presentation(dataDir + "DefaultFonts.pptx");
```
Replace `"Your Document Directory"` and `"Your Output Directory"` with your actual file paths.
## Step 3: Save Presentation with Default Regular Fonts
Specify the default regular font for the output formats (HTML and PDF) using `HtmlOptions` and `PdfOptions` respectively.
```java
try {
    // HTML save options
    HtmlOptions htmlOpts = new HtmlOptions();
    htmlOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.html", SaveFormat.Html, htmlOpts);
    htmlOpts.setDefaultRegularFont("Lucida Console");
    pres.save(outPath + "Presentation-out-LucidaConsole.html", SaveFormat.Html, htmlOpts);
    // PDF save options
    PdfOptions pdfOpts = new PdfOptions();
    pdfOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.pdf", SaveFormat.Pdf, pdfOpts);
} finally {
    if (pres != null) pres.dispose();
}
```
Ensure to replace `"Arial Black"` and `"Lucida Console"` with your desired default regular fonts.

## Conclusion
By following these steps, you've learned how to manipulate PowerPoint presentations using Aspose.Slides for Java effectively. This capability allows you to automate tasks, customize presentations, and enhance your Java applications with advanced PowerPoint handling functionalities.
## FAQ's
### Can Aspose.Slides for Java work with older versions of JDK?
Aspose.Slides for Java requires JDK 1.8 or above for compatibility.
### How can I get temporary licensing for Aspose.Slides for Java?
You can obtain a temporary license from [here](https://purchase.aspose.com/temporary-license/).
### Where can I find more detailed documentation on Aspose.Slides for Java?
Explore the comprehensive documentation [here](https://reference.aspose.com/slides/java/).
### Is there community support available for Aspose.Slides for Java?
Yes, you can get community support [here](https://forum.aspose.com/c/slides/11).
### Can I try Aspose.Slides for Java for free?
Yes, download a free trial version [here](https://releases.aspose.com/).

{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
