---
title: Add Assistant Node to SmartArt in Java PowerPoint
linktitle: Add Assistant Node to SmartArt in Java PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to add an assistant node to SmartArt in Java PowerPoint presentations using Aspose.Slides. Enhance your PowerPoint editing skills.
type: docs
weight: 17
url: /java/java-powerpoint-smartart-manipulation/add-assistant-node-smartart-java-powerpoint/
---
## Introduction
In this tutorial, we'll guide you through the process of adding an assistant node to SmartArt in Java PowerPoint presentations using Aspose.Slides.
## Prerequisites
Before we begin, ensure you have the following prerequisites in place:
1. Java Development Kit (JDK): Make sure you have Java installed on your system. You can download and install the latest JDK from [here](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2. Aspose.Slides for Java: Download and install the Aspose.Slides for Java library from [this link](https://releases.aspose.com/slides/java/).

## Import Packages
To start with, import the necessary packages in your Java code:
```java
import com.aspose.slides.*;
```
## Step 1: Set up the Presentation
Begin by creating a Presentation instance using the path to your PowerPoint file:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "AssistantNode.pptx");
```
## Step 2: Traverse Through Shapes
Traverse through every shape inside the first slide of the presentation:
```java
for (IShape shape : pres.getSlides().get_Item(0).getShapes())
```
## Step 3: Check for SmartArt Shapes
Check if the shape is of SmartArt type:
```java
if (shape instanceof ISmartArt)
```
## Step 4: Traverse Through SmartArt Nodes
Traverse through all nodes of the SmartArt shape:
```java
for (ISmartArtNode node : smart.getAllNodes())
```
## Step 5: Check for Assistant Node
Check if the node is an assistant node:
```java
if (node.isAssistant())
```
## Step 6: Set Assistant Node to Normal
If the node is an assistant node, set it to a normal node:
```java
node.setAssistant(false);
```
## Step 7: Save Presentation
Save the modified presentation:
```java
pres.save(dataDir + "ChangeAssistantNode_out.pptx", SaveFormat.Pptx);
```

## Conclusion
Congratulations! You have successfully added an assistant node to SmartArt in your Java PowerPoint presentation using Aspose.Slides.

## FAQ's
### Can I add multiple assistant nodes to a SmartArt in the presentation?
Yes, you can add multiple assistant nodes by repeating the process for each node.
### Does this tutorial work for both PowerPoint and PowerPoint templates?
Yes, you can apply this tutorial to both PowerPoint presentations and templates.
### Is Aspose.Slides compatible with all versions of PowerPoint?
Aspose.Slides supports PowerPoint versions from 97-2003 to the latest version.
### Can I customize the appearance of the assistant node?
Yes, you can customize the appearance using various properties and methods provided by Aspose.Slides.
### Is there any limit to the number of nodes in a SmartArt?
SmartArt in PowerPoint supports a large number of nodes, but it's recommended to keep it reasonable for better readability.
