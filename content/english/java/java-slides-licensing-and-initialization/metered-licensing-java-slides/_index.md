---
title: Metered Licensing in Java Slides
linktitle: Metered Licensing in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 10
url: /java/java-slides-licensing-and-initialization/metered-licensing-java-slides/
---

## Complete Source Code
```java
        // Create an instance of CAD Metered class
        Metered metered = new Metered();
        try
        {
            // Access the setMeteredKey property and pass public and private keys as parameters
            metered.setMeteredKey("*****", "*****");
            // Get metered data amount before calling API
            double amountbefore = Metered.getConsumptionQuantity();
            // Display information
            System.out.println("Amount Consumed Before: " + amountbefore);
            // Get metered data amount After calling API
            double amountafter = Metered.getConsumptionQuantity();
            // Display information
            System.out.println("Amount Consumed After: " + amountafter);
        }
        catch (Exception ex)
        {
            Logger.getLogger(MeteredLicensing.class.getName()).log(Level.SEVERE, null, ex);
        }
```
