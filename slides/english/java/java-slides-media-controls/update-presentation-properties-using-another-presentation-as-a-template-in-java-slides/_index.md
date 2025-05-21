---
title: Update Presentation Properties Using Another Presentation as a Template in Java Slides
linktitle: Update Presentation Properties Using Another Presentation as a Template in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Enhance PowerPoint presentations with updated metadata using Aspose.Slides for Java. Learn to update properties like author, title, and keywords using templates in Java Slides.
weight: 14
url: /java/media-controls/update-presentation-properties-using-another-presentation-as-a-template-in-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Update Presentation Properties Using Another Presentation as a Template in Java Slides


## Introduction to Update Presentation Properties Using Another Presentation as a Template in Java Slides

In this tutorial, we'll walk you through the process of updating presentation properties (metadata) for PowerPoint presentations using Aspose.Slides for Java. You can use another presentation as a template to update properties like author, title, keywords, and more. We'll provide you with step-by-step instructions and source code examples.

## Prerequisites

Before you begin, make sure you have the Aspose.Slides for Java library integrated into your Java project. You can download it from [here](https://releases.aspose.com/slides/java/).

## Step 1: Set up Your Project

Make sure you have created a Java project and added the Aspose.Slides for Java library to your project's dependencies.

## Step 2: Import Required Packages

You'll need to import the necessary Aspose.Slides packages for working with presentation properties. Include the following import statements at the beginning of your Java class:

```java
import com.aspose.slides.DocumentProperties;
import com.aspose.slides.IDocumentProperties;
import com.aspose.slides.IPresentationInfo;
import com.aspose.slides.PresentationFactory;
```

## Step 3: Update Presentation Properties

Now, let's update presentation properties using another presentation as a template. In this example, we'll update properties for multiple presentations, but you can adapt this code to your specific use case.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";

// Load the template presentation from which you want to copy properties
DocumentProperties template;
IPresentationInfo info = PresentationFactory.getInstance().getPresentationInfo(dataDir + "template.pptx");
template = (DocumentProperties) info.readDocumentProperties();

// Set the properties you want to update
template.setAuthor("Template Author");
template.setTitle("Template Title");
template.setCategory("Template Category");
template.setKeywords("Keyword1, Keyword2, Keyword3");
template.setCompany("Our Company");
template.setComments("Created from template");
template.setContentType("Template Content");
template.setSubject("Template Subject");

// Update multiple presentations using the same template
updateByTemplate(dataDir + "doc1.pptx", template);
updateByTemplate(dataDir + "doc2.odp", template);
updateByTemplate(dataDir + "doc3.ppt", template);
```

## Step 4: Define the `updateByTemplate` Method

Let's define a method to update the properties of individual presentations using the template. This method will take the path of the presentation to be updated and the template properties as parameters.

```java
private static void updateByTemplate(String path, IDocumentProperties template)
{
    // Load the presentation to be updated
    IPresentationInfo toUpdate = PresentationFactory.getInstance().getPresentationInfo(path);
    
    // Update the document properties using the template
    toUpdate.updateDocumentProperties(template);
    
    // Save the updated presentation
    toUpdate.writeBindedPresentation(path);
}
```

## Complete Source Code For Update Presentation Properties Using Another Presentation as a Template in Java Slides

```java
	// The path to the documents directory.
	String dataDir = "Your Document Directory";
	DocumentProperties template;
	IPresentationInfo info = PresentationFactory.getInstance().getPresentationInfo(dataDir + "template.pptx");
	template = (DocumentProperties) info.readDocumentProperties();
	template.setAuthor("Template Author");
	template.setTitle("Template Title");
	template.setCategory("Template Category");
	template.setKeywords("Keyword1, Keyword2, Keyword3");
	template.setCompany("Our Company");
	template.setComments("Created from template");
	template.setContentType("Template Content");
	template.setSubject("Template Subject");
	updateByTemplate(dataDir + "doc1.pptx", template);
	updateByTemplate(dataDir + "doc2.odp", template);
	updateByTemplate(dataDir + "doc3.ppt", template);
}
private static void updateByTemplate(String path, IDocumentProperties template)
{
	IPresentationInfo toUpdate = PresentationFactory.getInstance().getPresentationInfo(path);
	toUpdate.updateDocumentProperties(template);
	toUpdate.writeBindedPresentation(path);
```

## Conclusion

In this comprehensive tutorial, we have explored how to update presentation properties in PowerPoint presentations using Aspose.Slides for Java. We specifically focused on using another presentation as a template to efficiently update metadata such as author names, titles, keywords, and more.

## FAQ's

### How can I update properties for more presentations?

You can update properties for multiple presentations by calling the `updateByTemplate` method for each presentation with the desired path.

### Can I customize this code for different properties?

Yes, you can customize the code to update specific properties based on your requirements. Simply modify the `template` object with the desired property values.

### Is there any limitation on the type of presentations that can be updated?

No, you can update properties for presentations in various formats, including PPTX, ODP, and PPT.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
