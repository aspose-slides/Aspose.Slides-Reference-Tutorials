---
date: '2026-09-12'
description: Μάθετε πώς να χρησιμοποιήσετε το Maven Aspose Slides για να προσθέσετε
  και να προσαρμόσετε dynamic stock charts στο PowerPoint με Java. Περιλαμβάνει setup,
  adding data series, formatting lines, και saving.
keywords:
- maven aspose slides
- add data series chart
- format chart lines
- customize chart java
lastmod: '2026-09-12'
og_description: Το tutorial Maven Aspose Slides δείχνει πώς να δημιουργήσετε και να
  προσαρμόσετε dynamic stock charts στο PowerPoint χρησιμοποιώντας Java, καλύπτοντας
  data series, line formatting, και saving.
og_image_alt: Illustration of a Java-generated stock chart in PowerPoint using Aspose.Slides
og_title: 'Οδηγός Maven Aspose Slides: δημιουργία dynamic stock charts στο PowerPoint'
schemas:
- author: Aspose
  dateModified: '2026-09-12'
  description: Learn how to use Maven Aspose Slides to add and customize dynamic stock
    charts in PowerPoint with Java. Includes setup, adding data series, formatting
    lines, and saving.
  headline: 'Maven Aspose Slides: create dynamic stock charts in PowerPoint with Java'
  type: TechArticle
- questions:
  - answer: Yes. The library is pure Java, so you can run it in any servlet container
      or Spring Boot service.
    question: Can I use this code in a web application?
  - answer: Absolutely. It supports over 70 chart types, including Line, Bar, Pie,
      and Radar charts.
    question: Does Aspose.Slides support other chart types besides Stock?
  - answer: Use `chart.getTitle().addTextFrameForOverriding("Quarterly Stock Overview")`
      and then format the title as needed.
    question: How do I add a chart title programmatically?
  - answer: Practically, you can add tens of thousands of points; memory usage scales
      linearly, and the library streams data to keep the footprint low.
    question: Is there a limit to the number of data points per series?
  - answer: The latest version is always available under `com.aspose:aspose-slides:25.4`
      (or newer) on Maven Central.
    question: Which Maven coordinates should I use for the latest version?
  type: FAQPage
tags:
- maven aspose slides
- dynamic stock charts
- java charting
- aspose.slides
title: 'Maven Aspose Slides: δημιουργία dynamic stock charts στο PowerPoint με Java'
url: /el/java/charts-graphs/dynamic-stock-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maven Aspose Slides: δημιουργία δυναμικών διαγραμμάτων μετοχών στο PowerPoint με Java

## Εισαγωγή

**Maven Aspose Slides** σας επιτρέπει να δημιουργείτε προγραμματιστικά εξελιγμένες παρουσιάσεις PowerPoint από τη Java. Σε αυτό το tutorial θα μάθετε πώς να δημιουργείτε δυναμικά διαγράμματα μετοχών, να προσθέτετε και να μορφοποιείτε σειρές δεδομένων, να προσαρμόζετε τις γραμμές του διαγράμματος και τελικά να αποθηκεύετε το αρχείο. Είτε είστε οικονομικός αναλυτής που ετοιμάζει τριμηνιαίες αναφορές είτε προγραμματιστής που δημιουργεί αυτοματοποιημένα slide decks, τα παρακάτω βήματα σας παρέχουν μια πλήρη, έτοιμη για παραγωγή λύση.

**Τι θα μάθετε**
- Πώς να ρυθμίσετε το Maven με Aspose.Slides for Java
- Πώς να προσθέσετε ένα διάγραμμα μετοχών και να διαγράψετε τα προεπιλεγμένα δεδομένα
- Πώς να **προσθέσετε διάγραμμα σειράς δεδομένων** και **μορφοποιήσετε τις γραμμές του διαγράμματος**
- Πώς να **προσαρμόσετε τα οπτικά στοιχεία του διαγράμματος ειδικά για Java**
- Πώς να αποθηκεύσετε την ενημερωμένη παρουσίαση

Έτοιμοι να μετατρέψετε ακατέργαστους αριθμούς σε εντυπωσιακά οπτικά στοιχεία μετοχών; Ας ξεκινήσουμε!

## Γρήγορες απαντήσεις
- **Ποιο Maven artifact χρειάζομαι;** `aspose-slides` version 25.4 (ή νεότερο).  
- **Μπορώ να το τρέξω σε οποιοδήποτε OS;** Ναι – η βιβλιοθήκη είναι καθαρή Java και λειτουργεί σε Windows, macOS και Linux.  
- **Χρειάζομαι άδεια για ανάπτυξη;** Μια δωρεάν προσωρινή άδεια λειτουργεί για δοκιμές· απαιτείται πλήρης άδεια για παραγωγή.  
- **Ποιοι τύποι διαγραμμάτων υποστηρίζονται;** Πάνω από 70 ενσωματωμένους τύπους διαγραμμάτων, συμπεριλαμβανομένων Stock, Line και Bar.  
- **Πόσο μεγάλη παρουσίαση μπορώ να επεξεργαστώ;** Το Aspose.Slides μπορεί να διαχειριστεί αρχεία με 500+ διαφάνειες χωρίς να φορτώνει ολόκληρο το αρχείο στη μνήμη.

## Τι είναι το Maven Aspose Slides;
`Aspose.Slides for Java` είναι ένα Java API που επιτρέπει τη δημιουργία, τη διαχείριση και τη μετατροπή αρχείων PowerPoint χωρίς το Microsoft Office. Η ενσωμάτωση Maven απλοποιεί τη διαχείριση εξαρτήσεων, επιτρέποντάς σας να κατεβάζετε τη βιβλιοθήκη απευθείας από το Maven Central.

## Γιατί να χρησιμοποιήσετε το Maven Aspose Slides για διαγράμματα μετοχών;
Το Aspose.Slides υποστηρίζει **πάνω από 70 τύπους διαγραμμάτων** και μπορεί να αποδώσει παρουσιάσεις πολλαπλών εκατοντάδων σελίδων σε λιγότερο από ένα δευτερόλεπτο σε τυπικό υλικό διακομιστή. Οι δυνατότητες **γραμμής υψηλού-χαμηλού** και **μπάρας άνω/κάτω** παρέχουν ακριβή έλεγχο στις χρηματοοικονομικές απεικονίσεις, πολύ πιο πέρα από ό,τι προσφέρει η διεπαφή του PowerPoint.

## Προαπαιτούμενα
- **Java Development Kit (JDK)** – έκδοση 11 ή νεότερη.  
- **IDE** – IntelliJ IDEA, Eclipse ή οποιονδήποτε επεξεργαστή προτιμάτε.  
- **Aspose.Slides for Java** – έκδοση 25.4 (η πιο πρόσφατη τη στιγμή της συγγραφής).  

### Ρύθμιση Aspose.Slides for Java

#### Maven
Για να ενσωματώσετε το Aspose.Slides στο έργο σας χρησιμοποιώντας Maven, προσθέστε την ακόλουθη εξάρτηση στο `pom.xml` σας:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### Gradle
Για χρήστες Gradle, συμπεριλάβετε αυτό στο `build.gradle` σας:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### Άμεση λήψη
Εναλλακτικά, κατεβάστε το πιο πρόσφατο JAR από [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**Απόκτηση άδειας** – ξεκινήστε με μια δωρεάν δοκιμή ή ζητήστε μια προσωρινή άδεια. Για εμπορική χρήση, αγοράστε πλήρη άδεια.

Για λεπτομερή αναφορά API, δείτε την [Aspose.Slides documentation](https://docs.aspose.com/slides/java/).

## Πώς να δημιουργήσετε ένα δυναμικό διάγραμμα μετοχών βήμα προς βήμα
Φορτώστε την παρουσίασή σας, προσθέστε ένα διάγραμμα μετοχών, διαγράψτε τα προεπιλεγμένα δεδομένα και, στη συνέχεια, ενσωματώστε τις δικές σας σειρές και κατηγορίες. Η άμεση απάντηση στην κύρια ερώτηση είναι:

> Φορτώστε ένα υπάρχον PPTX με `new Presentation("template.pptx")`, προσθέστε ένα `Chart` τύπου `ChartType.Stock`, διαγράψτε τις προεπιλεγμένες σειρές και κατηγορίες, στη συνέχεια γεμίστε το με τα δικά σας σημεία δεδομένων και επιλογές μορφοποίησης. Τέλος, καλέστε `presentation.save("output.pptx", SaveFormat.Pptx)`.

### Αρχικοποίηση παρουσίασης
#### Επισκόπηση
Ξεκινήστε φορτώνοντας ένα υπάρχον αρχείο PowerPoint ώστε να μπορείτε να το τροποποιήσετε επί τόπου.

#### Βήμα‑βήμα
1. **Εισαγωγή της βιβλιοθήκης** – η κλάση `Presentation` είναι το σημείο εισόδου για όλες τις λειτουργίες διαφανειών.  

   ```java
   import com.aspose.slides.Presentation;
   ```

2. **Φόρτωση του αρχείου παρουσίασης** – δώστε τη διαδρομή προς το πρότυπο PPTX σας.  

   ```java
   String documentDirectory = "YOUR_DOCUMENT_DIRECTORY";
   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       // Ready to perform operations on 'pres'
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Προσθήκη διαγράμματος μετοχών στη διαφάνεια
#### Επισκόπηση
Εισάγετε ένα διάγραμμα Stock στην πρώτη διαφάνεια της παρουσίασης.

Η κλάση `Chart` αντιπροσωπεύει ένα σχήμα διαγράμματος που μπορεί να προστεθεί σε μια διαφάνεια.

#### Άμεση απάντηση
Προσθέτετε ένα διάγραμμα μετοχών καλώντας `slide.getShapes().addChart(ChartType.Stock, x, y, width, height)`. Αυτό δημιουργεί ένα αντικείμενο διαγράμματος που μπορείτε άμεσα να χειριστείτε.

```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.ChartType;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Διαγραφή υπαρχουσών σειρών δεδομένων και κατηγοριών στο διάγραμμα
#### Επισκόπηση
Αφαιρέστε τυχόν προ‑συμπληρωμένες σειρές ή κατηγορίες ώστε να ξεκινήσετε με ένα καθαρό σύνολο δεδομένων.

Το αντικείμενο `ChartData` περιέχει τις σειρές και τις κατηγορίες για ένα διάγραμμα.

#### Άμεση απάντηση
Καλείτε `chart.getChartData().getSeries().clear()` και `chart.getChartData().getCategories().clear()` για να διαγράψετε το προεπιλεγμένο περιεχόμενο πριν προσθέσετε τα δικά σας.

```java
   import com.aspose.slides.IChart;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       chart.getChartData().getSeries().clear();
       chart.getChartData().getCategories().clear();
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Προσθήκη κατηγοριών στα δεδομένα διαγράμματος
#### Επισκόπηση
Ορίστε τις κατηγορίες του άξονα X (π.χ., ημερομηνίες) που ομαδοποιούν τις τιμές των μετοχών σας.

Ένα `ChartCategory` αντιπροσωπεύει μια ετικέτα του άξονα X για ένα διάγραμμα.

#### Άμεση απάντηση
Δημιουργήστε ένα νέο `ChartCategory` για κάθε ετικέτα χρησιμοποιώντας `chart.getChartData().getCategories().add(dataWorkbook.getCell(0, row, 0), "Jan")`, επαναλαμβάνοντας για κάθε μήνα ή περίοδο.

```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
       
       // Add categories
       chart.getChartData().getCategories().add(wb.getCell(0, 1, 0, "A"));
       chart.getChartData().getCategories().add(wb.getCell(0, 2, 0, "B"));
       chart.getChartData().getCategories().add(wb.getCell(0, 3, 0, "C"));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Προσθήκη σειρών δεδομένων στο διάγραμμα
#### Επισκόπηση
Προσθέστε τις τέσσερις βασικές σειρές: Open, High, Low και Close.

Ένα `ChartSeries` περιέχει μια συλλογή σημείων δεδομένων για μια συγκεκριμένη σειρά στο διάγραμμα.

#### Άμεση απάντηση
Για κάθε σειρά, καλέστε `chart.getChartData().getSeries().add(dataWorkbook.getCell(0, 0, colIndex), chart.getType())`. Αυτό καταχωρεί τη σειρά στο βιβλίο δεδομένων του διαγράμματος.

```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // Add series for 'Open', 'High', 'Low', and 'Close'
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 1, "Open"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 2, "High"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 3, "Low"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 4, "Close"), chart.getType());
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Προσθήκη σημείων δεδομένων στις σειρές
#### Επισκόπηση
Γεμίστε κάθε σειρά με αριθμητικές τιμές που αντιπροσωπεύουν τις τιμές των μετοχών.

Ένα `DataPoint` αντιπροσωπεύει μια μοναδική τιμή σε μια σειρά.

#### Άμεση απάντηση
Κάντε βρόχο στη συλλογή δεδομένων σας και χρησιμοποιήστε `series.getDataPoints().addDataPointForBarSeries(dataWorkbook.getCell(0, row, col), value)` (ή τη σχετική μέθοδο για τον τύπο της σειράς) για να εισάγετε κάθε σημείο.

```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // Add data points to 'Open' series
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 1, 72));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 1, 25));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 1, 38));

       // Add data points to 'High' series
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 2, 172));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 2, 57));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 2, 57));

       // Add data points to 'Low' series
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 3, 13));

       // Add data points to 'Close' series
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 4, 25));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 4, 38));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 4, 50));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Μορφοποίηση γραμμών υψηλού‑χαμηλού και μπαρών άνω/κάτω
#### Επισκόπηση
Ρυθμίστε το οπτικό στυλ των συνδέσμων υψηλού‑χαμηλού και των γεμισμάτων των μπαρών άνω/κάτω.

Ένα `Marker` ορίζει το οπτικό σύμβολο για ένα σημείο δεδομένων.

#### Άμεση απάντηση
Ορίστε `chart.getChartData().getSeries().get(0).getMarker().setSize(10)` και διαμορφώστε `chart.getChartData().getSeries().get(0).getFormat().getLine().setWidth(2)` για να ελέγξετε το πάχος και το χρώμα της γραμμής.

```java
   import com.aspose.slides.FillType;
   import java.awt.Color;

   // Format high-low lines for 'Close' series
   LineFormat highLowLine = chart.getChartData().getSeriesGroups().get_Item(0).getHiLowLinesFormat();
   highLowLine.getFillFormat().setFillType(FillType.Solid);
   highLowLine.getFillFormat().getSolidFillColor().setColor(Color.GRAY);
   ```

#### Εμφάνιση μπαρών άνω/κάτω
Χρησιμοποιήστε τη μέθοδο `setShowUpDownBars(true)` του διαγράμματος για να εμφανίσετε τις μπάρες άνω/κάτω.

```java
   // Display up/down bars for the stock chart series group
   chart.getChartData().getSeriesGroups().get_Item(0).setHasUpDownBars(true);
   ```

### Προσαρμογή ετικετών δεδομένων στις γραμμές υψηλού‑χαμηλού
#### Επισκόπηση
Εμφανίστε αριθμητικές τιμές απευθείας στις γραμμές υψηλού‑χαμηλού για γρήγορη αναφορά.

Ένα `DataLabel` ελέγχει την εμφάνιση των ετικετών που συνδέονται με τα σημεία δεδομένων.

#### Άμεση απάντηση
Ενεργοποιήστε τις ετικέτες δεδομένων με `chart.getChartData().getSeries().get(0).getDataPoints().get(i).getLabel().setShowValue(true)` και μορφοποιήστε τις όπως χρειάζεται.

```java
    // Show values on up/down bars for each series in the chart group
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    ```

### Ορισμός χρώματος γεμίσματος μπαρών άνω/κάτω
#### Επισκόπηση
Δώστε στις μπαρ άνω ένα πράσινο γέμισμα και στις μπαρ κάτω ένα κόκκινο γέμισμα για να μεταφέρετε ενστικτωδώς την κίνηση της αγοράς.

Το αντικείμενο `UpDownBars` παρέχει πρόσβαση στη μορφοποίηση των μπαρ άνω και κάτω.

#### Άμεση απάντηση
Εφαρμόστε `chart.getUpDownBars().getUpBar().getFillFormat().setFillType(FillType.Solid)` και ορίστε το στερεό χρώμα σε `Color.GREEN`; επαναλάβετε για τη μπάρα κάτω με `Color.RED`.

```java
    // Change the up/down bar colors for each series in the chart group
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getFormat().getFill().setFillType(FillType.Solid);
        if (ser == chart.getChartData().getSeries().get_Item(0)) { // 'Open' series
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.CYAN); // Up bars in cyan
        } else if (ser == chart.getChartData().getSeries().get_Item(1)) { // 'High' series
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.DARKSEAGREEN); // Down bars in dark sea green
        }
    }
    ```

### Αποθήκευση του αρχείου PowerPoint
#### Επισκόπηση
Διατηρήστε τις αλλαγές σας σε ένα νέο αρχείο PPTX.

Η μέθοδος `save` γράφει την παρουσίαση στο δίσκο στην καθορισμένη μορφή.

#### Άμεση απάντηση
Καλέστε `presentation.save("DynamicStockChart.pptx", SaveFormat.Pptx)` – αυτό γράφει την τροποποιημένη παρουσίαση στο δίσκο σε τυπική μορφή PowerPoint.

```java
    pres.save("Add_Stock_Chart.pptx", com.aspose.slides.SaveFormat.Pptx);
    ```

## Συχνά προβλήματα και αντιμετώπιση
- **Το διάγραμμα δεν εμφανίζεται** – βεβαιωθείτε ότι οι συντεταγμένες X/Y και οι διαστάσεις του διαγράμματος είναι εντός των ορίων της διαφάνειας.  
- **Λείπουν σημεία δεδομένων** – ελέγξτε ότι οι δείκτες κελιών του workbook δεδομένων ταιριάζουν με τη σειρά/γραμμή που θέλετε να γεμίσετε.  
- **Απόκτηση άδειας** – μια προσωρινή δοκιμαστική άδεια λήγει μετά από 30 ημέρες· αντικαταστήστε την με μόνιμη άδεια για παραγωγικές εκδόσεις.  
- **Μείωση απόδοσης σε μεγάλα αρχεία** – χρησιμοποιήστε `Presentation.setCacheSize(0)` για να απενεργοποιήσετε την προσωρινή αποθήκευση εάν επεξεργάζεστε χιλιάδες διαφάνειες σε batch.

## Συχνές ερωτήσεις

**Ε: Μπορώ να χρησιμοποιήσω αυτόν τον κώδικα σε μια web εφαρμογή;**  
Α: Ναι. Η βιβλιοθήκη είναι καθαρή Java, οπότε μπορείτε να την εκτελέσετε σε οποιοδήποτε servlet container ή υπηρεσία Spring Boot.

**Ε: Υποστηρίζει το Aspose.Slides άλλους τύπους διαγραμμάτων εκτός από Stock;**  
Α: Απόλυτα. Υποστηρίζει πάνω από 70 τύπους διαγραμμάτων, συμπεριλαμβανομένων Line, Bar, Pie και Radar.

**Ε: Πώς προσθέτω τίτλο διαγράμματος προγραμματιστικά;**  
Α: Χρησιμοποιήστε `chart.getTitle().addTextFrameForOverriding("Quarterly Stock Overview")` και στη συνέχεια μορφοποιήστε τον τίτλο όπως χρειάζεται.

**Ε: Υπάρχει όριο στον αριθμό των σημείων δεδομένων ανά σειρά;**  
Α: Πρακτικά, μπορείτε να προσθέσετε δεκάδες χιλιάδες σημεία· η χρήση μνήμης αυξάνεται γραμμικά, και η βιβλιοθήκη ρέει τα δεδομένα για να διατηρεί το αποτύπωμα χαμηλό.

**Ε: Ποιες Maven συντεταγμένες πρέπει να χρησιμοποιήσω για την πιο πρόσφατη έκδοση;**  
Α: Η πιο πρόσφατη έκδοση είναι πάντα διαθέσιμη υπό `com.aspose:aspose-slides:25.4` (ή νεότερη) στο Maven Central.

---
**Τελευταία ενημέρωση:** 2026-09-12  
**Δοκιμή με:** Aspose.Slides for Java 25.4  
**Συγγραφέας:** Aspose

## Σχετικά Μαθήματα

- [aspose slides maven dependency: Προσθήκη και Διαμόρφωση Διαγραμμάτων σε Παρουσιάσεις Χρησιμοποιώντας Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Δημιουργία Διαγράμματος PowerPoint Java – Αποθήκευση Παρουσιάσεων με Διαγράμματα Χρησιμοποιώντας Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)
- [Δημιουργία και Μορφοποίηση Διαγραμμάτων Powerpoint Aspose Slides Java](/slides/java/charts-graphs/create-format-powerpoint-charts-aspose-slides-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}