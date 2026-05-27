---
date: '2026-03-07'
description: Μάθετε πώς να δημιουργήσετε διάγραμμα δακτυλίου σε Java χρησιμοποιώντας
  το Aspose.Slides. Αυτός ο οδηγός βήμα‑βήμα καλύπτει τη ρύθμιση της εξάρτησης Maven
  Aspose Slides, τη διαμόρφωση του διαγράμματος και την αποθήκευση των παρουσιάσεων.
keywords:
- create doughnut charts Java
- Aspose.Slides Java guide
- Java data visualization
title: Δημιουργία διαγράμματος δαχτυλιδιού Java με οδηγό Aspose.Slides
url: /el/java/charts-graphs/create-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Δημιουργία Διάγραμμα Ντόνατ Java με Οδηγό Aspose.Slides

## Εισαγωγή

Η δημιουργία ενός **doughnut chart** προγραμματιστικά μπορεί να μετατρέψει ακατέργαστους αριθμούς σε ένα εντυπωσιακό οπτικό στοιχείο που αφηγείται αμέσως μια ιστορία. Στη Java, το **Aspose.Slides** κάνει αυτή τη διαδικασία απλή, επιτρέποντάς σας να δημιουργήσετε διαγράμματα έτοιμα για παρουσίαση χωρίς να ανοίξετε ποτέ το PowerPoint. Σε αυτό το tutorial θα μάθετε πώς να **create doughnut chart java** βήμα‑βήμα — από τη ρύθμιση της εξάρτησης Maven Aspose Slides μέχρι την προσαρμογή σειρών, κατηγοριών και, τέλος, την αποθήκευση της παρουσίασης.

Με το τέλος αυτού του οδηγού θα μπορείτε να ενσωματώσετε δυναμικά doughnut charts σε οποιοδήποτε αρχείο PPTX, ιδανικά για αναφορές, πίνακες ελέγχου ή αυτοματοποιημένες παρουσιάσεις.

### Γρήγορες Απαντήσεις
- **What library is used?** Aspose.Slides for Java  
- **Primary task?** Create doughnut chart java in a PPTX file  
- **How to add the library?** Use the Maven Aspose Slides dependency (or Gradle)  
- **Minimum Java version?** JDK 16 or higher  
- **Can I customize colors and labels?** Yes, the API provides full formatting control  

## Τι είναι ένα Διάγραμμα Ντόνατ και Γιατί να το Χρησιμοποιήσετε;

Ένα doughnut chart είναι μια παραλλαγή του pie chart με κενό κέντρο, επιτρέποντάς σας να εμφανίσετε πολλαπλές σειρές δεδομένων σε συγκεντρικούς δακτυλίους. Αυτό το καθιστά ιδανικό για σύγκριση μερών ενός συνόλου σε πολλές κατηγορίες — σκεφτείτε πωλήσεις ανά περιοχή σε πολλαπλά τρίμηνα ή κατανομές προϋπολογισμού ανά τμήμα.

## Γιατί να Χρησιμοποιήσετε το Aspose.Slides για Java;

- **No Office installation required** – generate PPTX files on any server.  
- **Rich API** – full control over chart types, data points, and styling.  
- **High performance** – optimized for large presentations.  
- **Cross‑platform** – works on Windows, Linux, and macOS.

## Προαπαιτούμενα

- **Required Libraries:**  
  - Aspose.Slides for Java version 25.4 or later.  

- **Environment Setup:**  
  - JDK 16 or higher.  
  - Your favorite IDE (IntelliJ IDEA, Eclipse, NetBeans, etc.).  

- **Knowledge Prerequisites:**  
  - Basic Java programming.  
  - Familiarity with Maven or Gradle for dependency management.

## Εξάρτηση Maven Aspose Slides

Προσθέστε την παρακάτω εξάρτηση Maven στο `pom.xml`. Αυτή είναι η **maven aspose slides dependency** που χρειάζεστε για να ενσωματώσετε τη βιβλιοθήκη στο έργο σας.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

Αν προτιμάτε Gradle, χρησιμοποιήστε το αντίστοιχο απόσπασμα παρακάτω.

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Μπορείτε επίσης να κατεβάσετε το JAR απευθείας από τη σελίδα κυκλοφορίας:  
[ Aspose.Slides for Java releases ](https://releases.aspose.com/slides/java/)

### Απόκτηση Άδειας

Για να αφαιρέσετε το υδατογράφημα αξιολόγησης και να ξεκλειδώσετε το πλήρες σύνολο λειτουργιών:

- **Free trial** – start with a temporary license.  
- **Temporary license** – request one from the [Aspose website](https://purchase.aspose.com/temporary-license/).  
- **Commercial license** – purchase for production use.

Εφαρμόστε την άδεια στον κώδικά σας:

```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

## Οδηγός Υλοποίησης

### Αρχικοποίηση Παρουσίασης και Προσθήκη Διάγραμμα Ντόνατ

Πρώτα, δημιουργήστε ή φορτώστε μια παρουσίαση και προσθέστε ένα doughnut chart στην πρώτη διαφάνεια.

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### Διαμόρφωση του Workbook Δεδομένων του Διαγράμματος και Καθαρισμός Υπάρχοντων Δεδομένων

Στη συνέχεια, αποκτήστε το workbook που υποστηρίζει το διάγραμμα και διαγράψτε τυχόν προεπιλεγμένες σειρές ή κατηγορίες.

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

### Προσθήκη Σειρών στο Διάγραμμα

Τώρα θα προσθέσουμε έως και 15 σειρές. Κάθε σειρά μπορεί να προσαρμοστεί — εδώ ορίζουμε την έκρηξη, το μέγεθος της τρύπας του ντόνατ και τη γωνία του πρώτου κομματιού.

```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // Customize the series
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### Προσθήκη Κατηγοριών και Σημείων Δεδομένων

Θα δημιουργήσουμε 15 κατηγορίες και θα γεμίσουμε κάθε σειρά με ένα σημείο δεδομένων. Η τελευταία σειρά λαμβάνει ειδική μορφοποίηση ετικετών.

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // Data point format settings
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // Label formatting for the last series
    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .setFillType(FillType.Solid);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .getSolidFillColor().setColor(Color.LIGHT_GRAY);

        // Adjust display options
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // Adjust label position
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

### Αποθήκευση της Παρουσίασης

Τέλος, γράψτε την ενημερωμένη παρουσίαση στο δίσκο.

```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## Κοινά Προβλήματα και Λύσεις

- **License not found** – Verify the path to `license.lic` is correct and the file is readable.  
- **Chart appears blank** – Ensure you cleared existing series/categories before adding new ones.  
- **Incorrect colors** – Check that `FillType.Solid` is set for both fill and line formats.  
- **Performance with many series** – Limit the number of series/categories or reuse the workbook cells.

## Συχνές Ερωτήσεις

**Q: Can I generate a doughnut chart without a pre‑existing PPTX file?**  
A: Yes, instantiate `new Presentation()` to start from a blank slide deck.

**Q: Does Aspose.Slides support exporting to PDF?**  
A: Absolutely. After creating the chart, call `pres.save("output.pdf", SaveFormat.Pdf);`.

**Q: How do I change the doughnut hole size?**  
A: Use `series.getParentSeriesGroup().setDoughnutHoleSize((byte) value);` where value is 0‑100.

**Q: Is it possible to add data labels to all series, not just the last one?**  
A: Yes, move the label‑formatting block outside the `if (i == ...)` condition and apply it to each `dataPoint`.

**Q: What versions of Java are supported?**  
A: Aspose.Slides 25.4 supports JDK 16 and newer. Earlier JDKs require the appropriate classifier.

---

**Last Updated:** 2026-03-07  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}