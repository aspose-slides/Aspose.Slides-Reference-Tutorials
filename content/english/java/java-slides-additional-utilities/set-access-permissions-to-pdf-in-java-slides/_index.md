---
title: Set Access Permissions to PDF in Java Slides
linktitle: Set Access Permissions to PDF in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 17
url: /java/java-slides-additional-utilities/set-access-permissions-to-pdf-in-java-slides/
---

## Complete Source Code
```java
        String dataDir = "Your Document Directory";
        PdfOptions pdfOptions = new PdfOptions();
        pdfOptions.setPassword("my_password");
        pdfOptions.setAccessPermissions(PdfAccessPermissions.PrintDocument | PdfAccessPermissions.HighQualityPrint);
        Presentation presentation = new Presentation();
        try
        {
            presentation.save(dataDir + "PDFWithPermissions.pdf", SaveFormat.Pdf, pdfOptions);
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
```
