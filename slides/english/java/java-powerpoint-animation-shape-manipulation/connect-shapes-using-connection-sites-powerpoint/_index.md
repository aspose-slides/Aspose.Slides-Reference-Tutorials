---
title: Connect Shapes using Connection Sites in PowerPoint
linktitle: Connect Shapes using Connection Sites in PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to connect shapes in PowerPoint using Aspose.Slides for Java. Automate your presentations effortlessly.
weight: 19
url: /java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connection-sites-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Connect Shapes using Connection Sites in PowerPoint

## Introduction
In this tutorial, we'll explore how to connect shapes using connection sites in PowerPoint using Aspose.Slides for Java. This powerful library allows us to programmatically manipulate PowerPoint presentations, making tasks like connecting shapes seamless and efficient.
## Prerequisites
Before we begin, ensure you have the following:
1. Java Development Kit (JDK): Make sure you have Java installed on your system. You can download and install it from the [website](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2. Aspose.Slides for Java: Download and install Aspose.Slides for Java from the [download page](https://releases.aspose.com/slides/java/).
3. Integrated Development Environment (IDE): Choose an IDE for Java development, such as IntelliJ IDEA, Eclipse, or NetBeans.

## Import Packages
To get started, import the necessary packages into your Java project:
```java
import com.aspose.slides.*;

```
## Step 1: Accessing Shapes Collection
Access the shapes collection for the selected slide:
```java
// The path to the documents directory.                    
String dataDir = "Your Document Directory";
// Instantiate Presentation class that represents the PPTX file
Presentation presentation = new Presentation();
IShapeCollection shapes = presentation.getSlides().get_Item(0).getShapes();
```
## Step 2: Adding Connector Shape
Add a connector shape to the slide shape collection:
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector3, 0, 0, 10, 10);
```
## Step 3: Adding AutoShapes
Add auto shapes like ellipse and rectangle:
```java
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 200, 100, 100);
```
## Step 4: Joining Shapes to Connectors
Join the shapes to the connector:
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## Step 5: Setting Connection Site Index
Set the desired connection site index for the shapes:
```java
long wantedIndex = 6;
if (ellipse.getConnectionSiteCount() > (wantedIndex & 0xFFFFFFFFL))
{
    connector.setStartShapeConnectionSiteIndex(wantedIndex);
}
```

## Conclusion
In this tutorial, we've learned how to connect shapes using connection sites in PowerPoint using Aspose.Slides for Java. With this knowledge, you can now automate and customize your PowerPoint presentations with ease.
## FAQ's
### Can Aspose.Slides for Java be used for other PowerPoint manipulation tasks?
Yes, Aspose.Slides for Java provides a wide range of functionalities for creating, editing, and converting PowerPoint presentations.
### Is Aspose.Slides for Java free to use?
Aspose.Slides for Java is a commercial library, but you can explore its features with a free trial. Visit [here](https://releases.aspose.com/) to get started.
### Can I get support if I encounter any issues while using Aspose.Slides for Java?
Yes, you can get support from the Aspose community forums [here](https://forum.aspose.com/c/slides/11).
### Are temporary licenses available for Aspose.Slides for Java?
Yes, temporary licenses are available for testing and evaluation purposes. You can obtain one [here](https://purchase.aspose.com/temporary-license/).
### Where can I purchase a license for Aspose.Slides for Java?
You can purchase a license from the Aspose website [here](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
