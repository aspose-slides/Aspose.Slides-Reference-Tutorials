---
date: '2026-08-16'
description: Μάθετε πώς να προσθέσετε doughnut charts σε Java χρησιμοποιώντας Aspose.Slides.
  Αυτός ο οδηγός βήμα‑βήμα καλύπτει τη ρύθμιση εξαρτήσεων Maven, τη διαμόρφωση του
  διαγράμματος, τα χρώματα, τις ετικέτες και την αποθήκευση του PPTX.
keywords:
- how to add doughnut
- java create chart pptx
- maven aspose slides dependency
- customize doughnut chart colors
lastmod: '2026-08-16'
og_description: Πώς να προσθέσετε doughnut charts σε Java χρησιμοποιώντας Aspose.Slides.
  Ακολουθήστε αυτόν τον οδηγό για να ρυθμίσετε το Maven, να προσαρμόσετε τα χρώματα,
  τις ετικέτες και να δημιουργήσετε αρχεία PPTX.
og_image_alt: Developer guide showing doughnut chart creation in Java with Aspose.Slides
og_title: Πώς να προσθέσετε doughnut chart σε Java με Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-08-16'
  description: Learn how to add doughnut charts in Java using Aspose.Slides. This
    step‑by‑step guide covers Maven dependency setup, chart configuration, colors,
    labels and saving the PPTX.
  headline: How to add doughnut chart in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Yes, instantiate `new Presentation()` to start from a blank slide deck,
      then add a chart as shown above.
    question: Can I generate a doughnut chart without a pre‑existing PPTX file?
  - answer: Absolutely. After creating the chart, call `pres.save("output.pdf", SaveFormat.Pdf);`
      to get a PDF version of the slide.
    question: Does Aspose.Slides support exporting to PDF?
  - answer: Use `chart.getParentSeriesGroup().setDoughnutHoleSize((byte) value);`
      where `value` ranges from 0 to 100.
    question: How do I change the doughnut hole size?
  - answer: Yes, move the label‑formatting block outside the `if (i == ...)` condition
      and apply it to each `dataPoint`.
    question: Is it possible to add data labels to all series, not just the last one?
  - answer: Aspose.Slides 25.4 supports JDK 16 and newer. Earlier JDKs require the
      appropriate classifier in the Maven dependency.
    question: What versions of Java are supported?
  type: FAQPage
tags:
- doughnut chart
- Aspose.Slides
- Java PPTX
- data visualization
title: Πώς να προσθέσετε doughnut chart σε Java με Aspose.Slides
url: /el/java/charts-graphs/create-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Πώς να προσθέσετε γράφημα δακτυλίου σε Java με Aspose.Slides

## Εισαγωγή

Η δημιουργία ενός **γράφηματος δακτυλίου** προγραμματιστικά μπορεί να μετατρέψει ακατέργαστους αριθμούς σε ένα εντυπωσιακό οπτικό στοιχείο που αφηγείται αμέσως μια ιστορία. Σε Java, το **Aspose.Slides** καθιστά αυτή τη διαδικασία απλή, επιτρέποντάς σας να δημιουργείτε γραφήματα έτοιμα για παρουσίαση χωρίς καν να ανοίξετε το PowerPoint. Σε αυτόν τον **οδηγό** θα μάθετε **πώς να προσθέσετε δακτυλιοειδές** γραφήματα σε ένα αρχείο PPTX βήμα προς βήμα — από τη ρύθμιση της εξάρτησης Maven Aspose Slides μέχρι την προσαρμογή σειρών, κατηγοριών, χρωμάτων και ετικετών, και τέλος την αποθήκευση της παρουσίασης.

Στο τέλος αυτού του οδηγού θα μπορείτε να ενσωματώσετε δυναμικά γραφήματα δακτυλίου σε οποιοδήποτε αρχείο PPTX, ιδανικά για αναφορές, πίνακες ελέγχου ή αυτοματοποιημένες παρουσιάσεις.

### Γρήγορες Απαντήσεις
- **What library is used?** Aspose.Slides for Java  
- **Primary task?** Προσθήκη γραφήματος δακτυλίου σε αρχείο PPTX  
- **How to add the library?** Χρησιμοποιήστε την εξάρτηση Maven Aspose Slides (ή Gradle)  
- **Minimum Java version?** JDK 16 or higher  
- **Can I customize colors and labels?** Ναι, το API παρέχει πλήρη έλεγχο μορφοποίησης  

## Τι είναι το γράφημα δακτυλίου και γιατί να το χρησιμοποιήσετε;

Ένα γράφημα δακτυλίου είναι μια παραλλαγή του διαγράμματος πίτας με κενό κέντρο, επιτρέποντας την εμφάνιση πολλαπλών σειρών δεδομένων ως συνελικτικές δακτυλίους. **Οπτικοποιεί μέρη‑από‑ολό σε πολλές κατηγορίες ενώ διατηρεί χώρο για πρόσθετες πληροφορίες στο κέντρο.** Αυτό το καθιστά ιδανικό για σύγκριση πωλήσεων ανά περιοχή σε πολλαπλά τρίμηνα, κατανομές προϋπολογισμού ανά τμήμα, ή οποιοδήποτε σενάριο όπου χρειάζεται να δείξετε ιεραρχικά δεδομένα αναλογίας.

## Γιατί να χρησιμοποιήσετε το Aspose.Slides για Java;

Μπορείτε να προσθέσετε ένα γράφημα δακτυλίου χωρίς να εγκαταστήσετε το Microsoft Office, και η βιβλιοθήκη επεξεργάζεται **πάνω από 50 + μορφές εισόδου και εξόδου** ενώ διαχειρίζεται παρουσιάσεις που υπερβαίνουν τις 500 διαφάνειες. Το Aspose.Slides προσφέρει **ταχύτητα απόδοσης έως 3×** σε σύγκριση με την εγγενή αυτοματοποίηση του Office στο ίδιο υλικό, και λειτουργεί σε Windows, Linux και macOS. Αυτά τα ποσοτικά οφέλη σημαίνουν ότι μπορείτε να δημιουργήσετε μεγάλες συλλογές διαφανειών σε servers χωρίς γραφικό περιβάλλον με προβλέψιμη απόδοση.

## Προαπαιτούμενα

- **Απαιτούμενες βιβλιοθήκες**  
  - Aspose.Slides for Java 25.4 or later (the library that enables you to add doughnut charts).  

- **Περιβάλλον**  
  - JDK 16 or higher installed on your machine.  
  - An IDE such as IntelliJ IDEA, Eclipse or NetBeans.  

- **Γνώσεις**  
  - Basic Java syntax and object‑oriented concepts.  
  - Familiarity with Maven or Gradle for dependency management.  

## Εξάρτηση Maven Aspose Slides

Προσθέστε την παρακάτω εξάρτηση Maven στο `pom.xml`. Αυτή είναι η **εξάρτηση maven aspose slides** που χρειάζεστε για να ενσωματώσετε τη βιβλιοθήκη στο έργο σας.

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
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

Μπορείτε επίσης να κατεβάσετε το JAR απευθείας από τη σελίδα επίσημων εκδόσεων:  
[ Κυκλοφορίες Aspose.Slides για Java ](https://releases.aspose.com/slides/java/)

### Απόκτηση άδειας

Για να αφαιρέσετε το υδατογράφημα αξιολόγησης και να ξεκλειδώσετε το πλήρες σύνολο λειτουργιών:

- **Δωρεάν δοκιμή** – ξεκινήστε με μια προσωρινή άδεια.  
- **Προσωρινή άδεια** – ζητήστε μία από την [Aspose website](https://purchase.aspose.com/temporary-license/).  
- **Εμπορική άδεια** – αγοράστε για παραγωγική χρήση.

Εφαρμόστε την άδεια στον κώδικά σας:

```java
License license = new License();
license.setLicense("path/to/license.lic");
```

## Οδηγός υλοποίησης

### Αρχικοποίηση παρουσίασης και προσθήκη γραφήματος δακτυλίου

Presentation είναι η κλάση Aspose.Slides που αντιπροσωπεύει μια παρουσίαση PowerPoint. Φορτώστε ένα υπάρχον PPTX ή δημιουργήστε ένα νέο αντικείμενο `Presentation`, στη συνέχεια προσθέστε ένα γράφημα δακτυλίου στην πρώτη διαφάνεια.

```java
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 50, 50, 500, 400);
```

### Διαμόρφωση του φύλλου δεδομένων του γραφήματος και εκκαθάριση υπαρχόντων δεδομένων

Το workbook είναι ένα εσωτερικό φύλλο υπολογισμού που αποθηκεύει τα δεδομένα του γραφήματος. Αποκτήστε το workbook που υποστηρίζει το γράφημα, στη συνέχεια εκκαθαρίστε τυχόν προεπιλεγμένες σειρές ή κατηγορίες ώστε να ξεκινήσετε με καθαρό καμβά.

```java
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Προσθήκη σειρών στο γράφημα

Μια σειρά αντιπροσωπεύει μια συλλογή σημείων δεδομένων που σχεδιάζονται στο γράφημα. Μπορείτε να προσθέσετε έως και 15 σειρές. Κάθε σειρά μπορεί να προσαρμοστεί — εδώ ορίζουμε την έκρηξη, το μέγεθος του κεντρικού οπής και τη γωνία της πρώτης φέτας.

```java
for (int i = 0; i < 15; i++) {
    IChartSeries series = chart.getChartData().getSeries().add(wb.getCell(0, i + 1, 0), chart.getType());
    series.getParentSeriesGroup().setExplosion(i * 5);
}
chart.getParentSeriesGroup().setDoughnutHoleSize((byte) 50);
chart.getParentSeriesGroup().setFirstSliceAngle(30);
```

### Προσθήκη κατηγοριών και σημείων δεδομένων

Οι κατηγορίες είναι οι ετικέτες για κάθε σημείο δεδομένων κατά μήκος του άξονα του γραφήματος. Δημιουργήστε 15 κατηγορίες και γεμίστε κάθε σειρά με ένα σημείο δεδομένων. Η τελευταία σειρά λαμβάνει ειδική μορφοποίηση ετικέτας.

```java
for (int i = 0; i < 15; i++) {
    IChartCategory category = chart.getChartData().getCategories().add(wb.getCell(0, 0, i + 1));
    for (int j = 0; j < 15; j++) {
        IChartDataPoint dp = chart.getChartData().getSeries().get_Item(j).getDataPoints().addDataPointForDoughnutSeries(wb.getCell(0, j + 1, i + 1));
        dp.getValue().setData(wb.getCell(0, j + 1, i + 1).getDoubleValue());
    }
}
```

### Προσαρμογή χρωμάτων και ετικετών δεδομένων

`FillType.Solid` καθορίζει ένα συμπαγές χρώμα γεμίσματος για τα στοιχεία του γραφήματος. Ορίστε ένα συμπαγές χρώμα γεμίσματος για κάθε σειρά και ενεργοποιήστε τις ετικέτες δεδομένων. Για την τελική σειρά αλλάζουμε επίσης το χρώμα γραμματοσειράς της ετικέτας.

```java
for (int i = 0; i < 15; i++) {
    IChartSeries series = chart.getChartData().getSeries().get_Item(i);
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getFill().getSolidFillColor().setColor(Color.fromArgb(255, (i * 15) % 256, (i * 30) % 256));
    series.getDataPoints().forEach(dp -> dp.getLabel().setShowValue(true));
}
IChartSeries lastSeries = chart.getChartData().getSeries().get_Item(14);
lastSeries.getDataPoints().forEach(dp -> dp.getLabel().getFont().setColor(Color.Red));
```

### Αποθήκευση της παρουσίασης

`save` γράφει την παρουσίαση σε αρχείο στην επιλεγμένη μορφή. Γράψτε την ενημερωμένη παρουσίαση στο δίσκο σε μορφή PPTX ή εξάγετε σε PDF εάν απαιτείται.

```java
pres.save("DoughnutChartDemo.pptx", SaveFormat.Pptx);
```

## Κοινά προβλήματα και λύσεις

- **License not found** – Επαληθεύστε ότι η διαδρομή προς το `license.lic` είναι σωστή και το αρχείο είναι αναγνώσιμο.  
- **Chart appears blank** – Βεβαιωθείτε ότι εκκαθαρίσατε τις υπάρχουσες σειρές/κατηγορίες πριν προσθέσετε νέες.  
- **Incorrect colors** – Επιβεβαιώστε ότι το `FillType.Solid` είναι ορισμένο τόσο για το γέμισμα όσο και για τις μορφές γραμμής.  
- **Performance with many series** – Περιορίστε τον αριθμό σειρών/κατηγοριών ή επαναχρησιμοποιήστε κελιά του workbook για να διατηρήσετε τη χρήση μνήμης υπό έλεγχο.  

## Συχνές ερωτήσεις

**Q: Μπορώ να δημιουργήσω ένα γράφημα δακτυλίου χωρίς προϋπάρχιο αρχείο PPTX;**  
A: Ναι, δημιουργήστε `new Presentation()` για να ξεκινήσετε από μια κενή συλλογή διαφανειών, στη συνέχεια προσθέστε το γράφημα όπως φαίνεται παραπάνω.

**Q: Υποστηρίζει το Aspose.Slides εξαγωγή σε PDF;**  
A: Απόλυτα. Μετά τη δημιουργία του γραφήματος, καλέστε `pres.save("output.pdf", SaveFormat.Pdf);` για να λάβετε μια έκδοση PDF της διαφάνειας.

**Q: Πώς αλλάζω το μέγεθος της κεντρικής οπής του δακτυλίου;**  
A: Χρησιμοποιήστε `chart.getParentSeriesGroup().setDoughnutHoleSize((byte) value);` όπου η `value` κυμαίνεται από 0 to 100.

**Q: Είναι δυνατόν να προσθέσω ετικέτες δεδομένων σε όλες τις σειρές, όχι μόνο στην τελευταία;**  
A: Ναι, μετακινήστε το τμήμα μορφοποίησης ετικέτας εκτός της συνθήκης `if (i == ...)` και εφαρμόστε το σε κάθε `dataPoint`.

**Q: Ποιες εκδόσεις της Java υποστηρίζονται;**  
A: Το Aspose.Slides 25.4 υποστηρίζει JDK 16 και νεότερες. Παλαιότερες εκδόσεις JDK απαιτούν τον κατάλληλο classifier στην εξάρτηση Maven.

---

**Last Updated:** 2026-08-16  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Author:** Aspose

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

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

```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## Σχετικά Μαθήματα

- [Πώς να προσθέσετε γράφημα στο PowerPoint χρησιμοποιώντας το Aspose.Slides για Java: Οδηγός βήμα‑βήμα](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Πώς να προσαρμόσετε τα χρώματα γραφήματος πίτας σε Java με το Aspose.Slides – Πλήρης Οδηγός](/slides/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/)
- [Κίνηση κατηγοριών γραφήματος PowerPoint με Aspose.Slides για Java | Οδηγός βήμα‑βήμα](/slides/java/charts-graphs/animate-ppt-chart-categories-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}