---
date: '2026-06-03'
description: Μάθετε πώς να δημιουργήσετε clustered column chart σε Java χρησιμοποιώντας
  Aspose.Slides. Αυτός ο οδηγός καλύπτει την εξάρτηση Maven, τα βήματα δημιουργίας
  chart, και το data handling.
keywords:
- create clustered column chart
- how to create chart
- maven dependency aspose slides
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to create clustered column chart in Java using Aspose.Slides.
    This guide covers Maven dependency, chart creation steps, and data handling.
  headline: Create Clustered Column Chart in Java with Aspose.Slides
  type: TechArticle
- description: Learn how to create clustered column chart in Java using Aspose.Slides.
    This guide covers Maven dependency, chart creation steps, and data handling.
  name: Create Clustered Column Chart in Java with Aspose.Slides
  steps:
  - name: Create a Presentation and Add a Clustered Column Chart
    text: '`Presentation` class represents a PowerPoint document and allows creating
      slides.'
  - name: Manage Chart Series
    text: Now we’ll clear any default series, add a new one, and populate it with
      both positive and negative values.
  - name: Invert Negative Data Points Conditionally
    text: '`invertIfNegative` method enables inversion of negative values in a chart
      series.'
  type: HowTo
- questions:
  - answer: Aspose.Slides for Java.
    question: What library is used?
  - answer: Clustered column chart.
    question: Which chart type is demonstrated?
  - answer: Yes, using `invertIfNegative`.
    question: Can I invert negative values?
  - answer: JDK 16 or later.
    question: What Java version is required?
  - answer: Yes, a valid Aspose license.
    question: Is a license needed for production?
  type: FAQPage
title: Δημιουργία Clustered Column Chart σε Java με Aspose.Slides
url: /el/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Δημιουργία Clustered Column Chart σε Java με Aspose.Slides

## Πώς να δημιουργήσετε Chart σε Java: Εισαγωγή
Η δημιουργία δυναμικών παρουσιάσεων συχνά περιλαμβάνει την απεικόνιση δεδομένων μέσω διαγραμμάτων. Με **Aspose.Slides for Java**, μπορείτε εύκολα να **create clustered column chart** αντικείμενα, να βελτιώσετε την καθαρότητα και να έχετε μεγαλύτερο αντίκτυπο στο κοινό σας. Αυτό το σεμινάριο σας καθοδηγεί στη ρύθμιση της βιβλιοθήκης, την προσθήκη ενός clustered column chart, τη διαχείριση σειρών και την υπό όρους αντιστροφή των αρνητικών σημείων δεδομένων.

**What You'll Learn**
- Πώς να ρυθμίσετε Aspose.Slides for Java.  
- Βήματα για **create clustered column chart** στην παρουσίασή σας.  
- Τεχνικές για διαχείριση σειρών διαγράμματος και σημείων δεδομένων.  
- Μεθόδους για υπό όρους αντιστροφή αρνητικών σημείων δεδομένων για καλύτερη οπτικοποίηση.  
- Πώς να αποθηκεύσετε την παρουσίαση με ασφάλεια.  

## Γρήγορες Απαντήσεις
- **What library is used?** Aspose.Slides for Java.  
- **Which chart type is demonstrated?** Clustered column chart.  
- **Can I invert negative values?** Yes, using `invertIfNegative`.  
- **What Java version is required?** JDK 16 or later.  
- **Is a license needed for production?** Yes, a valid Aspose license.  

## Τι είναι ένα Clustered Column Chart;
Ένα clustered column chart είναι μια οπτική αναπαράσταση που τοποθετεί πολλαπλές σειρές δεδομένων πλάι‑πλάι για κάθε κατηγορία, επιτρέποντας γρήγορη σύγκριση μεταξύ ομάδων. Είναι ιδανικό για οικονομικές αναφορές, πίνακες πωλήσεων και οποιοδήποτε σενάριο όπου χρειάζεται να συγκρίνετε πολλούς δείκτες ταυτόχρονα.  

## Γιατί να χρησιμοποιήσετε Aspose.Slides για τη δημιουργία διαγραμμάτων;
Aspose.Slides σας επιτρέπει να δημιουργείτε και να προσαρμόζετε πλήρως διαγράμματα προγραμματιστικά, εξαλείφοντας την ανάγκη για χειροκίνητη επεξεργασία PowerPoint. Υποστηρίζει **70+ input and output formats** και μπορεί να επεξεργαστεί παρουσιάσεις με **up to 10,000 slides** χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη, εξασφαλίζοντας υψηλή απόδοση για μεγάλης κλίμακας αναφορές.  

## Προαπαιτούμενα
1. **Απαιτούμενες Βιβλιοθήκες**  
   - Aspose.Slides for Java (version 25.4 or later).  

2. **Περιβάλλον**  
   - JDK 16 or newer.  
   - Maven or Gradle for dependency management.  

3. **Γνώσεις**  
   - Basic Java programming.  
   - Familiarity with build tools (Maven/Gradle).  

## Ρύθμιση Aspose.Slides για Java
### Εγκατάσταση Maven
Add the following dependency to your `pom.xml` file:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Εγκατάσταση Gradle
Add the following line to your `build.gradle` file:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Άμεση Λήψη
Alternatively, download the latest version from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Απόκτηση Άδειας
- **Free Trial:** Δωρεάν Δοκιμή: Εξερευνήστε τις δυνατότητες χωρίς άδεια.  
- **Temporary License:** Προσωρινή Άδεια: Χρησιμοποιήστε την κατά τη διάρκεια αξιολόγησης.  
- **Full License:** Πλήρης Άδεια: Αγοράστε για παραγωγικές εγκαταστάσεις.  

### Βασική Αρχικοποίηση
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## Πώς να προσθέσω ένα clustered column chart σε μια διαφάνεια;
`Presentation` είναι η κύρια κλάση που αντιπροσωπεύει ένα αρχείο PowerPoint. Φορτώστε ένα νέο `Presentation`, προσθέστε μια διαφάνεια και καλέστε `slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400)`. Αυτή η εντολή δημιουργεί ένα πλήρως λειτουργικό clustered column chart στη θέση που καθορίζεται από τις συντεταγμένες. Στη συνέχεια μπορείτε να αποκτήσετε πρόσβαση στο αντικείμενο διαγράμματος για να τροποποιήσετε σειρές, σημεία δεδομένων και οπτικά στυλ.  

## Οδηγός Βήμα‑βήμα

### Βήμα 1: Δημιουργία Παρουσίασης και Προσθήκη Clustered Column Chart
`Presentation` class represents a PowerPoint document and allows creating slides.  

```java
import com.aspose.slides.*;

String YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation();
try {
    // Add a clustered column chart at (50, 50) with width 600 and height 400.
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### Βήμα 2: Διαχείριση Σειρών Διαγράμματος
Now we’ll clear any default series, add a new one, and populate it with both positive and negative values.  

```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    // Clear existing series and add a new one.
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### Βήμα 3: Αντιστροφή Αρνητικών Σημείων Δεδομένων υπό Όρους
`invertIfNegative` method enables inversion of negative values in a chart series.  

```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
    
    // Set default inversion behavior
    series.get_Item(0).invertIfNegative(false);
    
    // Conditionally invert a specific data point
    IChartDataPoint dataPoint = series.get_Item(0).getDataPoints().get_Item(0);
    if (dataPoint.getValue() < 0) {
        dataPoint.invertIfNegative(true);
    }
} finally {
    if (pres != null) pres.dispose();
}
```

## Κοινά Λάθη & Συμβουλές
- **Forgot to dispose the `Presentation` object?** Always call `dispose()` in a `finally` block to free native resources.  
- **Negative values not showing as inverted?** Ensure you call `invertIfNegative(true)` **after** adding the data point.  
- **Chart size issues:** The coordinates (X, Y) and dimensions (width, height) are in points; adjust them to fit your slide layout.  

## Συχνές Ερωτήσεις

**Q:** Μπορώ να δημιουργήσω άλλους τύπους διαγραμμάτων με την ίδια προσέγγιση;  
A: Ναι, απλώς αντικαταστήστε `ChartType.ClusteredColumn` με οποιαδήποτε άλλη τιμή του enum `ChartType` (π.χ., `Line`, `Pie`).  

**Q:** Χρειάζομαι άδεια για εκδόσεις ανάπτυξης;  
A: A temporary or evaluation license is required for full feature access; otherwise, the library works in trial mode with watermark limitations.  

**Q:** Πώς μπορώ να εξάγω την παρουσίαση σε PDF μετά την προσθήκη διαγραμμάτων;  
`SaveFormat.Pdf` specifies PDF as the output format for saving a presentation. Use `pres.save("output.pdf", SaveFormat.Pdf);` after you finish chart manipulation.  

**Q:** Είναι δυνατόν να μορφοποιήσετε μεμονωμένες στήλες (χρώμα, περίγραμμα);  
`IChartDataPoint` represents a single data point in a chart and allows formatting. Each `IChartDataPoint` provides options such as `getFillFormat().setFillType(FillType.Solid)` and `getLineFormat()`.  

**Q:** Τι γίνεται αν χρειαστεί να ενημερώσω τα δεδομένα του διαγράμματος μετά την αποθήκευση της παρουσίασης;  
A: Load the presentation again with `new Presentation("file.pptx")`, modify the chart data, and re‑save.  

---

**Last Updated:** 2026-06-03  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16)  
**Author:** Aspose  

## Σχετικά Σεμινάρια

- [Πώς να δημιουργήσετε στοίβαγμα στήλης διάγραμμα σε Java με Aspose.Slides – Ένας Πλήρης Οδηγός](/slides/java/charts-graphs/aspose-slides-java-stacked-column-charts/)
- [Πώς να Δημιουργήσετε Chart σε Java με Aspose.Slides – Κατάκτηση της Δημιουργίας και Επικύρωσης Διαγραμμάτων](/slides/java/charts-graphs/aspose-slides-chart-creation-validation-java/)
- [Δημιουργία & Μορφοποίηση Διαγραμμάτων σε Java με Aspose.Slides: Ένας Πλήρης Οδηγός](/slides/java/charts-graphs/create-format-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}