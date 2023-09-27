---
title: Read-Only Recommended Properties in Java Slides
linktitle: Read-Only Recommended Properties in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Learn how to enable Read-Only Recommended properties in Java PowerPoint presentations using Aspose.Slides for Java. Follow our step-by-step guide with source code examples for enhanced presentation security.
type: docs
weight: 17
url: /java/presentation-properties/read-only-recommended-properties-in-java-slides/
---

## Introduction to Enabling Read-Only Recommended Properties in Java Slides

In this tutorial, we will explore how to enable Read-Only Recommended properties for PowerPoint presentations using Aspose.Slides for Java. Read-Only Recommended properties can be useful when you want to encourage users to view a presentation without making any changes. These properties suggest that the presentation should be opened in read-only mode. We will provide you with a step-by-step guide along with Java source code to achieve this.

## Prerequisites

Before we begin, make sure you have the Aspose.Slides for Java library set up in your project. You can download it from the [Aspose.Slides for Java website](https://products.aspose.com/slides/java/).

## Step 1: Create a New PowerPoint Presentation

We'll start by creating a new PowerPoint presentation using Aspose.Slides for Java. If you already have a presentation, you can skip this step.

```java
String outPptxPath = RunExamples.getOutPath() + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
```

In the code above, we've defined the path for the output PowerPoint file and created a new presentation object.

## Step 2: Enable Read-Only Recommended Property

Now, let's enable the Read-Only Recommended property for the presentation.

```java
try
{
    pres.getProtectionManager().setReadOnlyRecommended(true);
    pres.save(outPptxPath, SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

In this code snippet, we use the `getProtectionManager().setReadOnlyRecommended(true)` method to set the Read-Only Recommended property to `true`. This ensures that when someone opens the presentation, they will be prompted to open it in read-only mode.

## Step 3: Save the Presentation

Finally, we save the presentation with the Read-Only Recommended property enabled.

## Complete Source Code For Read-Only Recommended Properties in Java Slides

```java
String outPptxPath = RunExamples.getOutPath() + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
try
{
	pres.getProtectionManager().setReadOnlyRecommended(true);
	pres.save(outPptxPath, SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusion

In this tutorial, you have learned how to enable the Read-Only Recommended property for a PowerPoint presentation using Aspose.Slides for Java. This feature can be helpful when you want to restrict editing and encourage viewers to use the presentation in read-only mode. You can further enhance security by setting a password for the presentation.

## FAQ's

### How do I disable the Read-Only Recommended property?

To disable the Read-Only Recommended property, simply use the following code:

```java
pres.getProtectionManager().setReadOnlyRecommended(false);
```

### Can I set a password for a Read-Only Recommended presentation?

Yes, you can set a password for a Read-Only Recommended presentation using Aspose.Slides for Java. You can use the `setPassword` method to set a password for the presentation. If a password is set, users will need to enter it to open the presentation, even in read-only mode.

```java
pres.getProtectionManager().setPassword("YourPassword");
```

Remember to replace `"YourPassword"` with your desired password.
