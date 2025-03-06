---
title: Add Custom Document Properties in Java Slides
linktitle: Add Custom Document Properties in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to enhance PowerPoint presentations with custom document properties in Java Slides. Step-by-step guide with code examples using Aspose.Slides for Java.
weight: 13
url: /java/presentation-properties/add-custom-document-properties-in-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Introduction to Adding Custom Document Properties in Java Slides

In this tutorial, we'll walk you through the process of adding custom document properties to a PowerPoint presentation using Aspose.Slides for Java. Custom document properties allow you to store additional information about the presentation for reference or categorization.

## Prerequisites

Before you begin, make sure you have the Aspose.Slides for Java library installed and set up in your Java project.

## Step 1: Import Required Packages

```java
import com.aspose.slides.*;
```

## Step 2: Create a New Presentation

First, you need to create a new presentation object. You can do this as follows:

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";

// Instantiate the Presentation class
Presentation presentation = new Presentation();
```

## Step 3: Getting Document Properties

Next, you'll retrieve the document properties of the presentation. These properties include built-in properties like title, author, and custom properties that you can add.

```java
// Getting Document Properties
IDocumentProperties documentProperties = presentation.getDocumentProperties();
```

## Step 4: Adding Custom Properties

Now, let's add custom properties to the presentation. Custom properties consist of a name and a value. You can use them to store any information you want.

```java
documentProperties.set_Item("New Custom", 12);
documentProperties.set_Item("My Name", "Mudassir");
documentProperties.set_Item("Custom", 124);
```

## Step 5: Getting a Property Name at a Particular Index

You can also retrieve the name of a custom property at a specific index. This can be useful if you need to work with specific properties.

```java
// Getting property name at a particular index
String getPropertyName = documentProperties.getCustomPropertyName(2);
```

## Step 6: Removing a Selected Property

If you want to remove a custom property, you can do so by specifying its name. Here, we're removing the property we obtained in Step 5.

```java
// Removing selected property
documentProperties.removeCustomProperty(getPropertyName);
```

## Step 7: Saving the Presentation

Finally, save the presentation with the added and removed custom properties to a file.

```java
// Saving presentation
presentation.save(dataDir + "CustomDocumentProperties_out.pptx", SaveFormat.Pptx);
```

## Complete Source Code For Add Custom Document Properties in Java Slides

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Instantiate the Presentation class
Presentation presentation = new Presentation();
// Getting Document Properties
IDocumentProperties documentProperties = presentation.getDocumentProperties();
// Adding Custom properties
documentProperties.set_Item("New Custom", 12);
documentProperties.set_Item("My Name", "Mudassir");
documentProperties.set_Item("Custom", 124);
// Getting property name at particular index
String getPropertyName = documentProperties.getCustomPropertyName(2);
// Removing selected property
documentProperties.removeCustomProperty(getPropertyName);
// Saving presentation
presentation.save(dataDir + "CustomDocumentProperties_out.pptx", SaveFormat.Pptx);
```

## Conclusion

You've learned how to add custom document properties to a PowerPoint presentation in Java using Aspose.Slides. Custom properties can be valuable for storing additional information related to your presentations. You can extend this knowledge to include more custom properties as needed for your specific use case.

## FAQ's

### How do I retrieve a custom property's value?

To retrieve the value of a custom property, you can use the `get_Item` method on the `documentProperties` object. For example:

```java
Object customPropertyValue = documentProperties.get_Item("New Custom");
```

### Can I add custom properties of different data types?

Yes, you can add custom properties of various data types, including numbers, strings, dates, and more, as shown in the example. Aspose.Slides for Java handles different data types seamlessly.

### Is there a limit to the number of custom properties I can add?

There is no strict limit to the number of custom properties you can add. However, keep in mind that adding an excessive number of properties may affect the performance and size of your presentation file.

### How can I list all custom properties in a presentation?

You can loop through all custom properties to list them. Here's an example of how to do this:

```java
for (int i = 0; i < documentProperties.getCustomCount(); i++) {
    String propertyName = documentProperties.getCustomPropertyName(i);
    Object propertyValue = documentProperties.get_Item(propertyName);
    System.out.println("Property Name: " + propertyName);
    System.out.println("Property Value: " + propertyValue);
}
```

This code will display the names and values of all custom properties in the presentation.

{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
