---
date: '2026-01-24'
description: Οδηγός βήμα‑προς‑βήμα για τη δημιουργία διαγράμματος διασποράς σε Java
  χρησιμοποιώντας το Aspose.Slides, προσθήκη σημείων δεδομένων διασποράς και εργασία
  με πολλαπλές σειρές διαγράμματος διασποράς.
keywords:
- Aspose.Slides for Java
- create scatter charts in Java
- customize Java charts with Aspose
title: Δημιουργία διαγράμματος διασποράς Java με το Aspose.Slides – Προσαρμογή και
  αποθήκευση
url: /el/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Δημιουργία Scatter Chart Java με Aspose.Slides

Σε αυτό το tutorial θα **δημιουργήσετε scatter chart java** έργα από το μηδέν, θα προσθέσετε data points scatter, και θα μάθετε πώς να δουλεύετε με multiple series scatter chart—όλα χρησιμοποιώντας το Aspose.Slides for Java. Θα περάσουμε από τη ρύθμιση του καταλόγου, την αρχικοποίηση της παρουσίασης, τη δημιουργία του διαγράμματος, τη διαχείριση των δεδομένων, την προσαρμογή των markers, και τέλος την αποθήκευση της παρουσίασης.

**Τι θα μάθετε**
- Ρύθμιση καταλόγου για αποθήκευση αρχείων παρουσίασης  
- Αρχικοποίηση και διαχείριση παρουσιάσεων χρησιμοποιώντας Aspose.Slides  
- Δημιουργία scatter chart σε μια διαφάνεια  
- Προσθήκη και διαχείριση data points για κάθε σειρά  
- Προσαρμογή τύπων σειρών, markers και διαχείριση multiple series scatter chart  
- Αποθήκευση της ολοκληρωμένης παρουσίασης  

Ας ξεκινήσουμε με τις προαπαιτήσεις.

## Γρήγορες Απαντήσεις
- **Ποια είναι η κύρια βιβλιοθήκη;** Aspose.Slides for Java  
- **Ποια έκδοση Java απαιτείται;** JDK 8 ή νεότερη (συνιστάται JDK 16)  
- **Μπορώ να προσθέσω περισσότερες από δύο σειρές;** Ναι – μπορείτε να προσθέσετε οποιονδήποτε αριθμό σειρών σε ένα scatter chart  
- **Πώς αλλάζω τα χρώματα των markers;** Χρησιμοποιήστε `series.getMarker().getFillFormat().setFillColor(Color)`  
- **Απαιτείται άδεια για παραγωγή;** Ναι, μια εμπορική άδεια αφαιρεί τους περιορισμούς αξιολόγησης  

## Προαπαιτήσεις

Για να ακολουθήσετε αυτό το tutorial, βεβαιωθείτε ότι έχετε:
- **Aspose.Slides for Java** – έκδοση 25.4 ή νεότερη.  
- **Java Development Kit (JDK)** – JDK 8 ή νεότερη.  
- Βασικές γνώσεις Java και εξοικείωση με Maven ή Gradle.  

## Ρύθμιση Aspose.Slides for Java

Ενσωματώστε το Aspose.Slides στο έργο σας με μία από τις παρακάτω μεθόδους.

### Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Ή κατεβάστε το τελευταίο πακέτο από [Aspose Releases](https://releases.aspose.com/slides/java/).

#### Απόκτηση Άδειας
- **Δωρεάν Δοκιμή** – αξιολόγηση 30 ημερών.  
- **Προσωρινή Άδεια** – εκτεταμένη δοκιμή.  
- **Εμπορική Άδεια** – πλήρης χρήση σε παραγωγή.

Τώρα ας βουτήξουμε στον κώδικα.

## Οδηγός Υλοποίησης

### Βήμα 1: Ρύθμιση Καταλόγου
Πρώτα, βεβαιωθείτε ότι ο φάκελος εξόδου υπάρχει ώστε η παρουσίαση να μπορεί να αποθηκευτεί χωρίς σφάλματα.

```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```

### Βήμα 2: Αρχικοποίηση Παρουσίασης
Δημιουργήστε μια νέα παρουσίαση και πάρτε την πρώτη διαφάνεια.

```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### Βήμα 3: Προσθήκη Scatter Chart
Εισάγετε ένα scatter chart με ομαλές γραμμές στη διαφάνεια.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

### Βήμα 4: Διαχείριση Δεδομένων Διαγράμματος (Καθαρισμός & Προσθήκη Σειρών)
Καθαρίστε τυχόν προεπιλεγμένες σειρές και προσθέστε τις δικές μας σειρές για το **multiple series scatter chart**.

```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Adding new series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```

### Βήμα 5: Προσθήκη Data Points Scatter
Συμπληρώστε κάθε σειρά με τιμές X‑Y χρησιμοποιώντας **add data points scatter**.

```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```

### Βήμα 6: Προσαρμογή Τύπων Σειρών & Markers
Ρυθμίστε το οπτικό στυλ—αλλάξτε σε ευθείες γραμμές με markers και ορίστε διαφορετικά σύμβολα markers.

```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// Modifying second series
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

### Βήμα 7: Αποθήκευση Παρουσίασης
Αποθηκεύστε το αρχείο στο δίσκο.

```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Πρακτικές Εφαρμογές
- **Οικονομική Ανάλυση** – Σχεδιάστε κινήσεις τιμών μετοχών με multiple series scatter chart.  
- **Επιστημονική Έρευνα** – Οπτικοποιήστε πειραματικά μετρήματα χρησιμοποιώντας add data points scatter για ακριβή αναπαράσταση δεδομένων.  
- **Διαχείριση Έργων** – Εμφανίστε τάσεις κατανομής πόρων σε πολλά έργα σε ένα ενιαίο scatter chart.

## Σκέψεις για Απόδοση
- Αποδεσμεύστε το αντικείμενο `Presentation` μετά την αποθήκευση για ελευθέρωση μνήμης.  
- Για μεγάλα σύνολα δεδομένων, γεμίστε το workbook σε παρτίδες αντί για ένα‑προς‑ένα.  
- Αποφύγετε την υπερβολική μορφοποίηση μέσα σε στενά βρόχους· εφαρμόστε στυλ μετά την εισαγωγή των δεδομένων.

## Συνηθισμένα Προβλήματα & Λύσεις
| Πρόβλημα | Λύση |
|----------|------|
| **Το διάγραμμα εμφανίζεται κενό** | Επαληθεύστε ότι τα data points έχουν προστεθεί στη σωστή σειρά και ότι οι δείκτες του workbook ταιριάζουν. |
| **Τα markers δεν είναι ορατά** | Βεβαιωθείτε ότι το `series.getMarker().setSize()` έχει τιμή μεγαλύτερη από 0 και ότι το σύμβολο του marker έχει οριστεί. |
| **OutOfMemoryError σε μεγάλα διαγράμματα** | Χρησιμοποιήστε `pres.dispose()` μετά την αποθήκευση και εξετάστε την αύξηση του μεγέθους heap της JVM (`-Xmx`). |

## Συχνές Ερωτήσεις

### Πώς αλλάζω το χρώμα των markers;
Χρησιμοποιήστε `series.getMarker().getFillFormat().setFillColor(Color)` όπου το `Color` είναι μια παρουσία της `java.awt.Color`.

### Μπορώ να προσθέσω περισσότερες από δύο σειρές σε ένα scatter chart;
Απόλυτα. Επαναλάβετε το μπλοκ δημιουργίας σειράς (Βήμα 4) για κάθε επιπλέον σειρά που χρειάζεστε.

### Είναι δυνατόν να εξάγω το διάγραμμα ως εικόνα;
Ναι. Καλέστε `chart.exportChartImage("chart.png", ImageFormat.Png)` μετά την προσθήκη όλων των δεδομένων.

### Υποστηρίζει το Aspose.Slides διαδραστικά tooltips στα σημεία του scatter;
Αν και το PowerPoint δεν παρέχει runtime tooltips, μπορείτε να ενσωματώσετε ετικέτες δεδομένων χρησιμοποιώντας `series.getDataPoints().get_Item(i).getLabel().setText("Your text")`.

### Πώς μπορώ να ανιματίσω τις σειρές του scatter;
Χρησιμοποιήστε `chart.getChartData().getSeries().get_Item(i).getFormat().getEffectFormat().setPresetEffect(PresetEffectType.Appear)` για να προσθέσετε μια απλή εμφάνιση animation.

---

**Τελευταία Ενημέρωση:** 2026-01-24  
**Δοκιμή Με:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}