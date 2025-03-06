---
title: Root Directory ClsId in Java Slides
linktitle: Root Directory ClsId in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to set Root Directory ClsId in Aspose.Slides for Java presentations. Customize hyperlink behavior with CLSID.
weight: 10
url: /java/media-controls/root-directory-clsid-in-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introduction to Setting Root Directory ClsId in Aspose.Slides for Java

In Aspose.Slides for Java, you can set the Root Directory ClsId, which is the CLSID (Class Identifier) used to specify the application to be used as the root directory when a hyperlink in your presentation is activated. In this guide, we will walk you through how to do this step by step.

## Prerequisites

Before you begin, make sure you have the following prerequisites:

- Java Development Kit (JDK) installed on your system.
- Aspose.Slides for Java library added to your project. You can download it from [Aspose.Slides for Java Documentation](https://reference.aspose.com/slides/java/).
- A code editor or Integrated Development Environment (IDE) set up for Java development.

## Step 1: Create a New Presentation

First, let's create a new presentation using Aspose.Slides for Java. In this example, we will create an empty presentation.

```java
// Output file name
String resultPath = "your_output_path/pres.ppt"; // Replace "your_output_path" with your desired output directory.
Presentation pres = new Presentation();
```

In the code above, we define the path for the output presentation file and create a new `Presentation` object.

## Step 2: Set Root Directory ClsId

To set the Root Directory ClsId, you need to create an instance of `PptOptions` and set the desired CLSID. The CLSID represents the application that will be used as the root directory when a hyperlink is activated.

```java
PptOptions pptOptions = new PptOptions();
// Set CLSID to 'Microsoft Powerpoint.Show.8'
pptOptions.setRootDirectoryClsid(UUID.fromString("64818D10-4F9B-11CF-86EA-00AA00B929E8"));
```

In the code above, we create a `PptOptions` object and set the CLSID to 'Microsoft Powerpoint.Show.8'. You can replace it with the CLSID of the application you want to use as the root directory.

## Step 3: Save the Presentation

Now, let's save the presentation with the Root Directory ClsId set.

```java
// Save presentation
pres.save(resultPath, SaveFormat.Ppt, pptOptions);
```

In this step, we save the presentation to the specified `resultPath` with the `PptOptions` we created earlier.

## Step 4: Cleanup

Don't forget to dispose of the `Presentation` object to release any allocated resources.

```java
if (pres != null) {
    pres.dispose();
}
```

## Complete Source Code For Root Directory ClsId in Java Slides

```java
// Output file name
String resultPath = "Your Output Directory" + "pres.ppt";
Presentation pres = new Presentation();
try {
	PptOptions pptOptions = new PptOptions();
	// set CLSID to 'Microsoft Powerpoint.Show.8'
	pptOptions.setRootDirectoryClsid(UUID.fromString("64818D10-4F9B-11CF-86EA-00AA00B929E8"));
	// Save presentation
	pres.save(resultPath, SaveFormat.Ppt, pptOptions);
} finally {
	if (pres != null) pres.dispose();
}
```

## Conclusion

You have successfully set the Root Directory ClsId in Aspose.Slides for Java. This allows you to specify the application that will be used as the root directory when hyperlinks are activated in your presentation. You can customize the CLSID according to your specific requirements.

## FAQ's

### How do I find the CLSID for a specific application?

To find the CLSID for a specific application, you can refer to the documentation or resources provided by the application's developer. CLSIDs are unique identifiers assigned to COM objects and are typically specific to each application.

### Can I set a custom CLSID for the root directory?

Yes, you can set a custom CLSID for the root directory by specifying the desired CLSID value using the `setRootDirectoryClsid` method, as shown in the code example. This allows you to use a specific application as the root directory when hyperlinks are activated in your presentation.

### What happens if I don't set the Root Directory ClsId?

If you don't set the Root Directory ClsId, the default behavior will depend on the viewer or application used to open the presentation. It may use its own default application as the root directory when hyperlinks are activated.

### Can I change the Root Directory ClsId for individual hyperlinks?

No, the Root Directory ClsId is typically set at the presentation level and applies to all hyperlinks within the presentation. If you need to specify different applications for individual hyperlinks, you may need to handle those hyperlinks separately in your code.

### Are there any limitations on the CLSIDs I can use?

The CLSIDs you can use are typically determined by the applications installed on the system. You should use CLSIDs that correspond to valid applications capable of handling hyperlinks. Be aware that using an invalid CLSID may result in unexpected behavior.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
