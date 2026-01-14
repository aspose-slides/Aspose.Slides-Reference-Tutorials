---
date: '2026-01-14'
description: Μάθετε πώς να εξάγετε διάγραμμα σε Excel χρησιμοποιώντας το Aspose.Slides
  for Java και να προσθέσετε διαφάνεια με πίτα σε παρουσιάσεις. Οδηγός βήμα‑βήμα με
  κώδικα.
keywords:
- Aspose.Slides Java
- creating charts in Java
- exporting chart data with Aspose
title: Εξαγωγή διαγράμματος σε Excel με το Aspose.Slides Java
url: /el/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Εξαγωγή Διαγράμματος σε Excel Χρησιμοποιώντας το Aspose.Slides για Java

**Κατακτήστε τις Τεχνικές Οπτικοποίησης Δεδομένων με το Aspose.Slides για Java**

Στο σημερινό δεδομενο‑προσανατολισμένο τοπίο, η δυνατότητα **export chart to excel** απευθείας από την εφαρμογή Java σας μπορεί να μετατρέψει στατικά οπτικά στοιχεία PowerPoint σε επαναχρησιμοποιήσιμα, αναλύσιμα σύνολα δεδομένων. Είτε χρειάζεστε να δημιουργήσετε αναφορές, να τροφοδοτήσετε pipelines ανάλυσης, είτε απλώς να επιτρέψετε στους επιχειρηματικούς χρήστες να επεξεργαστούν τα δεδομένα του διαγράμματος στο Excel, το Aspose.Slides το κάνει απλό. Αυτό το tutorial σας καθοδηγεί στη δημιουργία ενός διαγράμματος, στην προσθήκη μιας διαφάνειας με **pie chart** και στην εξαγωγή των δεδομένων του διαγράμματος σε ένα βιβλίο εργασίας Excel.

**What You'll Learn:**
- Φορτώστε και διαχειριστείτε αρχεία παρουσίασης με ευκολία
- **Add pie chart slide** και άλλους τύπους διαγραμμάτων στις διαφάνειές σας
- **Export chart to excel** (generate excel from chart) για ανάλυση downstream
- Ορίστε διαδρομή εξωτερικού βιβλίου εργασίας για **embed chart in presentation** και διατηρήστε τα δεδομένα συγχρονισμένα

Ας ξεκινήσουμε!

## Γρήγορες Απαντήσεις
- **Ποιος είναι ο κύριος σκοπός;** Export chart data from a PowerPoint slide to an Excel file.  
- **Ποια έκδοση της βιβλιοθήκης απαιτείται;** Aspose.Slides for Java 25.4 or later.  
- **Χρειάζομαι άδεια;** A free trial works for evaluation; a commercial license is required for production.  
- **Μπορώ να προσθέσω μια διαφάνεια με pie chart;** Yes – the tutorial shows how to add a Pie chart.  
- **Είναι η Java 16 ελάχιστη;** Yes, JDK 16 or higher is recommended.

## Πώς να εξάγετε chart to excel χρησιμοποιώντας το Aspose.Slides;
Η εξαγωγή δεδομένων διαγράμματος σε Excel είναι τόσο απλή όσο το φόρτωμα μιας παρουσίασης, η δημιουργία ενός διαγράμματος και στη συνέχεια η εγγραφή του ρεύματος του βιβλίου εργασίας του διαγράμματος σε αρχείο. Τα παρακάτω βήματα σας καθοδηγούν σε όλη τη διαδικασία, από τη ρύθμιση του έργου μέχρι την τελική επαλήθευση.

## Prerequisites
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα παρακάτω έτοιμα:

### Required Libraries and Versions
- **Aspose.Slides for Java** version 25.4 or later

### Environment Setup Requirements
- Java Development Kit (JDK) 16 or higher
- Ένας κώδικας επεξεργαστής ή IDE όπως IntelliJ IDEA ή Eclipse

### Knowledge Prerequisites
- Βασικές γνώσεις προγραμματισμού Java
- Εξοικείωση με συστήματα κατασκευής Maven ή Gradle

## Setting Up Aspose.Slides for Java
Για να αρχίσετε να χρησιμοποιείτε το Aspose.Slides, συμπεριλάβετε το στο έργο σας χρησιμοποιώντας Maven ή Gradle.

**Maven**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Εναλλακτικά, μπορείτε να [κατεβάσετε την πιο πρόσφατη έκδοση απευθείας](https://releases.aspose.com/slides/java/).

### License Acquisition Steps
Το Aspose.Slides προσφέρει δωρεάν άδεια δοκιμής για να εξερευνήσετε όλες τις δυνατότητές του. Μπορείτε επίσης να υποβάλετε αίτηση για προσωρινή άδεια ή να αγοράσετε μία για παρατεταμένη χρήση. Ακολουθήστε τα παρακάτω βήματα:
1. Επισκεφθείτε τη σελίδα [Aspose Purchase page](https://purchase.aspose.com/buy) για να αποκτήσετε την άδειά σας.  
2. Για δωρεάν δοκιμή, κατεβάστε από το [Releases](https://releases.aspose.com/slides/java/).  
3. Υποβάλετε αίτηση για προσωρινή άδεια [εδώ](https://purchase.aspose.com/temporary-license/).

Μόλις έχετε το αρχείο άδειας, αρχικοποιήστε το στην εφαρμογή Java:
```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## Implementation Guide

### Feature 1: Load Presentation
Φορτώντας μια παρουσίαση είναι το πρώτο βήμα για οποιαδήποτε εργασία επεξεργασίας.

#### Overview
Αυτή η δυνατότητα δείχνει πώς να φορτώσετε ένα υπάρχον αρχείο PowerPoint χρησιμοποιώντας το Aspose.Slides for Java.

#### Step‑by‑Step Implementation
**Load Presentation**
```java
import com.aspose.slides.Presentation;

public class Feature1 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        // Load an existing presentation
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        
        // Clean up resources
        if (pres != null) pres.dispose();
    }
}
```
**Explanation:**  
- `Presentation` is initialized with the path to your `.pptx` file.  
- Always dispose of the `Presentation` object to free native resources.

### Feature 2: Add Pie Chart Slide
Η προσθήκη ενός διαγράμματος μπορεί να ενισχύσει σημαντικά την παρουσίαση δεδομένων, και πολλοί προγραμματιστές ρωτούν **how to add chart slide** σε Java.

#### Overview
Αυτή η δυνατότητα δείχνει πώς να προσθέσετε μια **pie chart slide** (το κλασικό σενάριο “add pie chart slide”) στην πρώτη διαφάνεια μιας παρουσίασης.

#### Step‑by‑Step Implementation
**Add Pie Chart**
```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature2 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Add a Pie chart at position (50, 50) with width 400 and height 600
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                ChartType.Pie, 50, 50, 400, 600);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```
**Explanation:**  
- `addChart` inserts a Pie chart.  
- The parameters define the chart type and its position/size on the slide.

### Feature 3: Generate Excel from Chart
Η εξαγωγή των δεδομένων του διαγράμματος σας επιτρέπει να **generate excel from chart** για πιο βαθιά ανάλυση.

#### Overview
Αυτή η δυνατότητα δείχνει πώς να εξάγετε δεδομένα διαγράμματος από μια παρουσίαση σε εξωτερικό βιβλίο εργασίας Excel.

#### Step‑by‑Step Implementation
**Export Data**
```java
import com.aspose.slides.IChart;
import java.io.File;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.FileNotFoundException;
import com.aspose.slides.Presentation;

public class Feature3 {
    public static void main(String[] args) {
        // Set the path to your document directory and output directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            File file = new File(externalWbPath);
            if (file.exists()) file.delete();
            
            // Export chart data to an Excel stream
            byte[] workbookData = chart.getChartData().readWorkbookStream();
            FileOutputStream outputStream = new FileOutputStream(file);
            outputStream.write(workbookData);
            outputStream.close();
        } catch (FileNotFoundException e) {
            e.printStackTrace();
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```
**Explanation:**  
- `readWorkbookStream` extracts the chart’s workbook data.  
- The byte array is written to an `.xlsx` file using `FileOutputStream`.

### Feature 4: Embed Chart in Presentation with External Workbook
Η σύνδεση ενός διαγράμματος με εξωτερικό βιβλίο εργασίας σας βοηθά να **embed chart in presentation** και να διατηρείτε τα δεδομένα συγχρονισμένα.

#### Overview
Αυτή η δυνατότητα δείχνει πώς να ορίσετε μια διαδρομή εξωτερικού βιβλίου εργασίας ώστε το διάγραμμα να μπορεί να διαβάζει/γράφει δεδομένα απευθείας από το Excel.

#### Step‑by‑Step Implementation
**Set External Workbook Path**
```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature4 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define and set the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            chart.getChartData().setExternalWorkbook(externalWbPath);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```
**Explanation:**  
- `setExternalWorkbook` links the chart to an Excel file, allowing dynamic updates without rebuilding the slide.

## Practical Applications
Το Aspose.Slides προσφέρει ευέλικτες λύσεις για διάφορα σενάρια:

1. **Business Reports:** Create detailed reports with charts directly from Java applications.  
2. **Academic Presentations:** Enhance lectures with interactive pie chart slides.  
3. **Financial Analysis:** **Export chart to excel** for in‑depth financial modeling.  
4. **Marketing Analytics:** Visualize campaign performance and **generate excel from chart** for the analytics team.

## Frequently Asked Questions

**Q: Μπορώ να χρησιμοποιήσω αυτήν την προσέγγιση με άλλους τύπους διαγραμμάτων (π.χ., Bar, Line);**  
A: Absolutely. Replace `ChartType.Pie` with any other `ChartType` enum value.

**Q: Χρειάζομαι ξεχωριστή βιβλιοθήκη Excel για να διαβάσω το εξαγόμενο αρχείο;**  
A: No. The exported `.xlsx` file is a standard Excel workbook that can be opened with any spreadsheet application.

**Q: Πώς επηρεάζει το εξωτερικό βιβλίο εργασίας το μέγεθος της διαφάνειας;**  
A: Linking to an external workbook does not increase the PPTX file size significantly; the chart references the workbook at runtime.

**Q: Είναι δυνατόν να ενημερώσω τα δεδομένα στο Excel και η διαφάνεια να αντανακλά τις αλλαγές αυτόματα;**  
A: Yes. After calling `setExternalWorkbook`, any changes saved to the workbook will be reflected the next time the presentation is opened.

**Q: Τι γίνεται αν χρειαστεί να εξάγω πολλαπλά διαγράμματα από την ίδια παρουσίαση;**  
A: Iterate over each slide’s chart collection, call `readWorkbookStream()` for each, and write to separate workbook files.

---

**Last Updated:** 2026-01-14  
**Tested With:** Aspose.Slides 25.4 for Java  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}