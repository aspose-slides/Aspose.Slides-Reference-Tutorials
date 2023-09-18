---
title: Convert to PDF Compliance in Java Slides
linktitle: Convert to PDF Compliance in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 26
url: /java/java-slides-presentation-conversion/convert-pdf-compliance-java-slides/
---

## Complete Source Code
```java
        String presentationName = RunExamples.getDataDir_Conversion() + "ConvertToPDF.pptx";
        String outPath = RunExamples.getOutPath() + "ConvertToPDF-Comp.pdf";
        Presentation presentation = new Presentation(presentationName);
        try {
            PdfOptions pdfOptions = new PdfOptions();
            pdfOptions.setCompliance(PdfCompliance.PdfA2a);
            presentation.save(outPath, SaveFormat.Pdf, pdfOptions);
        } finally {
            if (presentation != null) presentation.dispose();
        }
```
