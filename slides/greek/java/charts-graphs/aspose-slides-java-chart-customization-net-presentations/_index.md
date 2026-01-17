---
date: '2026-01-17'
description: Μάθετε πώς να προσθέτετε σειρές σε γράφημα και να προσαρμόζετε τα στοιβαγμένα
  διαγράμματα στήλης σε παρουσιάσεις .NET χρησιμοποιώντας το Aspose.Slides for Java.
keywords:
- Aspose.Slides for Java
- .NET Presentations
- Chart Customization
title: Προσθήκη σειράς σε διάγραμμα με το Aspose.Slides for Java στο .NET
url: /el/java/charts-graphs/aspose-slides-java-chart-customization-net-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Κατάκτηση της Προσαρμογής Διαγραμμάτων σε Παρουσιάσεις .NET με τη χρήση του Aspose.Slides για Java

## Introduction
Στον κόσμο των παρουσιάσεων που βασίζονται σε δεδομένα, τα διαγράμματα είναι απαραίτητα εργαλεία που μετατρέπουν ακατέργαστους αριθμούς σε συναρπαστικές οπτικές ιστορίες. Όταν χρειάζεται να **add series to chart** προγραμματιστικά, ειδικά μέσα σε αρχεία παρουσίασης .NET, η εργασία μπορεί να φαίνεται δύσκολη. Ευτυχώς, το **Aspose.Slides for Java** προσφέρει ένα ισχυρό, γλώσσα‑ανεξάρτητο API που κάνει τη δημιουργία και προσαρμογή διαγραμμάτων απλή—ακόμη και όταν ο στόχος σας είναι ένα .NET PPTX.

Σε αυτό το tutorial θα ανακαλύψετε πώς να **add series to chart**, πώς να **add chart** τύπου stacked column, και πώς να ρυθμίσετε λεπτομερώς οπτικές παραμέτρους όπως το gap width. Στο τέλος, θα μπορείτε να δημιουργήσετε δυναμικές, πλούσιες σε δεδομένα διαφάνειες που φαίνονται επαγγελματικές και καλοσχεδιασμένες.

**What You’ll Learn**
- Πώς να δημιουργήσετε μια κενή παρουσίαση χρησιμοποιώντας το Aspose.Slides  
- Πώς να **add stacked column chart** σε μια διαφάνεια  
- Πώς να **add series to chart** και να ορίσετε κατηγορίες  
- Πώς να γεμίσετε σημεία δεδομένων και να προσαρμόσετε οπτικές ρυθμίσεις  

Ας ετοιμάσουμε το περιβάλλον ανάπτυξής σας.

## Quick Answers
- **What is the primary class to start a presentation?** `Presentation`  
- **Which method adds a chart to a slide?** `slide.getShapes().addChart(...)`  
- **How do you add a new series?** `chart.getChartData().getSeries().add(...)`  
- **Can you change the gap width between bars?** Yes, using `setGapWidth()` on the series group  
- **Do I need a license for production?** Yes, a valid Aspose.Slides for Java license is required  

## What is “add series to chart”?
Η προσθήκη σειράς σε ένα διάγραμμα σημαίνει την εισαγωγή μιας νέας συλλογής δεδομένων που το διάγραμμα θα αποτυπώσει ως ξεχωριστό οπτικό στοιχείο (π.χ. μια νέα ράβδο, γραμμή ή φέτα). Κάθε σειρά μπορεί να έχει το δικό της σύνολο τιμών, χρωμάτων και μορφοποίησης, επιτρέποντάς σας να συγκρίνετε πολλαπλά σύνολα δεδομένων πλάι‑πλάι.

## Why use Aspose.Slides for Java to modify .NET presentations?
- **Cross‑platform**: Γράψτε κώδικα Java μία φορά και στοχεύστε αρχεία PPTX που χρησιμοποιούνται από εφαρμογές .NET.  
- **No COM or Office dependencies**: Λειτουργεί σε διακομιστές, CI pipelines και containers.  
- **Rich chart API**: Υποστηρίζει πάνω από 50 τύπους διαγραμμάτων, συμπεριλαμβανομένων των stacked column charts.  

## Prerequisites
1. **Aspose.Slides for Java** βιβλιοθήκη (έκδοση 25.4 ή νεότερη).  
2. Maven ή Gradle εργαλείο κατασκευής, ή χειροκίνητη λήψη JAR.  
3. Βασικές γνώσεις Java και εξοικείωση με τη δομή PPTX.  

## Setting Up Aspose.Slides for Java
### Maven Installation
Προσθέστε την ακόλουθη εξάρτηση στο `pom.xml` σας:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle Installation
Συμπεριλάβετε αυτή τη γραμμή στο αρχείο `build.gradle` σας:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direct Download
Εναλλακτικά, κατεβάστε το τελευταίο JAR από τη σελίδα κυκλοφορίας: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**License Acquisition**  
Ξεκινήστε με μια δωρεάν δοκιμή κατεβάζοντας μια προσωρινή άδεια από [here](https://purchase.aspose.com/temporary-license/). Για παραγωγική χρήση, αγοράστε πλήρη άδεια για να ξεκλειδώσετε όλες τις δυνατότητες.

## Step‑by‑Step Implementation Guide
Below each step you’ll find a concise code snippet (unchanged from the original tutorial) followed by an explanation of what it does.

### Step 1: Create an Empty Presentation
```java
import com.aspose.slides.*;

// Initialize an empty presentation
Presentation presentation = new Presentation();

// Access the first slide (automatically created)
ISlide slide = presentation.getSlides().get_Item(0);

// Save the presentation to a specified path
presentation.save("YOUR_OUTPUT_DIRECTORY/Empty_Presentation.pptx", SaveFormat.Pptx);
```
*Ξεκινάμε με ένα καθαρό αρχείο PPTX, το οποίο μας παρέχει έναν καμβά για την προσθήκη διαγραμμάτων.*

### Step 2: Add a Stacked Column Chart to the Slide
```java
// Import necessary Aspose.Slides classes
import com.aspose.slides.*;

// Add a chart of type StackedColumn
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);

// Save the presentation with the new chart
presentation.save("YOUR_OUTPUT_DIRECTORY/Chart_Added.pptx", SaveFormat.Pptx);
```
*Η μέθοδος `addChart` δημιουργεί ένα **add stacked column chart** και το τοποθετεί στην πάνω‑αριστερή γωνία της διαφάνειας.*

### Step 3: Add Series to the Chart (Primary Goal)
```java
// Accessing the default worksheet index for chart data
int defaultWorksheetIndex = 0;

// Adding series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Save the presentation after adding series
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Added.pptx", SaveFormat.Pptx);
```
*Εδώ **add series to chart** – κάθε κλήση δημιουργεί μια νέα σειρά δεδομένων που θα εμφανιστεί ως ξεχωριστή ομάδα στηλών.*

### Step 4: Add Categories to the Chart
```java
// Adding categories to the chart
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));

// Save the presentation after adding categories
presentation.save("YOUR_OUTPUT_DIRECTORY/Categories_Added.pptx", SaveFormat.Pptx);
```
*Οι κατηγορίες λειτουργούν ως ετικέτες του άξονα X, δίνοντας νόημα σε κάθε στήλη.*

### Step 5: Populate Series Data
```java
// Accessing a particular series for data population
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Adding data points to the series
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Save the presentation with populated data
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Data_Populated.pptx", SaveFormat.Pptx);
```
*Τα σημεία δεδομένων δίνουν σε κάθε σειρά τις αριθμητικές της τιμές, τις οποίες το διάγραμμα θα αποδώσει ως ύψος ράβδων.*

### Step 6: Set Gap Width for Chart Series Group
```java
// Setting the gap width between bars
series.getParentSeriesGroup().setGapWidth(50);

// Save the presentation after adjusting the gap width
presentation.save("YOUR_OUTPUT_DIRECTORY/Set_GapWidth.pptx", SaveFormat.Pptx);
```
*Η ρύθμιση του πλάτους του κενού βελτιώνει την αναγνωσιμότητα, ειδικά όταν υπάρχουν πολλές κατηγορίες.*

## Common Use Cases
- **Financial reporting** – σύγκριση τριμηνιαίων εσόδων ανά επιχειρησιακή μονάδα.  
- **Project dashboards** – εμφάνιση ποσοστών ολοκλήρωσης εργασιών ανά ομάδα.  
- **Marketing analytics** – οπτικοποίηση απόδοσης εκστρατειών πλάι‑πλάι.

## Performance Tips
- **Reuse the `Presentation` object** όταν δημιουργείτε πολλά διαγράμματα για να μειώσετε την κατανάλωση μνήμης.  
- **Limit the number of data points** στα απαραίτητα για την οπτική ιστορία.  
- **Dispose of objects** (`presentation.dispose()`) μετά την αποθήκευση για απελευθέρωση πόρων.

## Frequently Asked Questions
**Q: Can I add other chart types besides stacked column?**  
A: Yes, Aspose.Slides supports line, pie, area, and many more chart types.

**Q: Do I need a separate license for .NET output?**  
A: No, the same Java license works for all output formats, including .NET PPTX files.

**Q: How do I change the chart’s color palette?**  
A: Use `chart.getChartData().getSeries().get_Item(i).getFormat().getFill().setFillType(FillType.Solid)` and set the desired `Color`.

**Q: Is it possible to add data labels programmatically?**  
A: Absolutely. Call `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)` to display values.

**Q: What if I need to update an existing presentation?**  
A: Load the file with `new Presentation("existing.pptx")`, modify the chart, and save it back.

## Conclusion
Τώρα έχετε έναν πλήρη οδηγό από την αρχή μέχρι το τέλος για το πώς να **add series to chart**, να δημιουργήσετε ένα **stacked column chart**, και να ρυθμίσετε την εμφάνισή του σε παρουσιάσεις .NET χρησιμοποιώντας το Aspose.Slides for Java. Πειραματιστείτε με διαφορετικούς τύπους διαγραμμάτων, χρώματα και πηγές δεδομένων για να δημιουργήσετε εντυπωσιακές οπτικές αναφορές που θα εντυπωσιάσουν τα ενδιαφερόμενα μέρη.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-17  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose