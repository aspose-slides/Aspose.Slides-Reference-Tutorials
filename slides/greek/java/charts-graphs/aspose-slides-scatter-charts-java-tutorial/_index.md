---
date: '2026-02-24'
description: Μάθετε πώς να προσαρμόζετε το διάγραμμα διασποράς Aspose χρησιμοποιώντας
  το Aspose.Slides for Java. Αυτός ο οδηγός σας καθοδηγεί στη δημιουργία, το στυλ
  και την αποθήκευση δυναμικών διαγραμμάτων διασποράς στις παρουσιάσεις σας.
keywords:
- Aspose.Slides for Java
- create scatter charts in Java
- customize Java charts with Aspose
title: Προσαρμογή διαγράμματος διασποράς Aspose σε Java
url: /el/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Προσαρμογή Scatter Chart Aspose σε Java

Σε αυτό το tutorial θα μάθετε πώς να **προσαρμογή scatter chart aspose** με τη δυνατή βιβλιοθήκη Aspose.Slides for Java. Θα περάσουμε από τη ρύθμιση του έργου σας, τη δημιουργία ενός scatter chart, την προσαρμογή τύπων σειρών και δεικτών, και τελικά την αποθήκευση της παρουσίασης. Στο τέλος, θα μπορείτε να δημιουργείτε επαγγελματικά διαγράμματα διασποράς προγραμματιστικά και να προσαρμόζετε κάθε οπτική λεπτομέρεια ώστε να ταιριάζει με το brand ή τις ανάγκες αναφοράς σας.

## Γρήγορες Απαντήσεις
- **Ποια βιβλιοθήκη χρειάζομαι;** Aspose.Slides for Java (v25.4+).  
- **Ποια έκδοση Java υποστηρίζεται;** JDK 8 ή νεότερη.  
- **Μπορώ να αλλάξω τα σχήματα των δεικτών;** Ναι – χρησιμοποιήστε `MarkerStyleType` για να επιλέξετε αστέρια, κύκλους κ.λπ.  
- **Πώς αποθηκεύω το αρχείο;** Καλέστε `pres.save("output.pptx", SaveFormat.Pptx)`.  
- **Απαιτείται άδεια;** Η δωρεάν δοκιμή λειτουργεί για ανάπτυξη· απαιτείται εμπορική άδεια για παραγωγή.

## Τι είναι το “customize scatter chart aspose”;
Η προσαρμογή ενός scatter chart με Aspose σημαίνει ορισμός προγραμματιστικά των δεδομένων, της εμφάνισης και της συμπεριφοράς του διαγράμματος—όλα από τις συντεταγμένες των σημείων μέχρι τα σύμβολα των δεικτών—χωρίς να ανοίγετε το PowerPoint χειροκίνητα. Αυτή η προσέγγιση είναι ιδανική για αυτοματοποιημένες αναφορές, παρουσιάσεις βασισμένες σε δεδομένα ή οποιοδήποτε σενάριο όπου χρειάζεστε επαναλαμβανόμενες, υψηλής ποιότητας οπτικοποιήσεις.

## Γιατί να προσαρμόζετε scatter charts με Aspose.Slides;
- **Πλήρης έλεγχος** – τροποποίηση τύπων σειρών, στυλ δεικτών, χρωμάτων και άλλων μέσω κώδικα Java.  
- **Αυτοματοποίηση** – δημιουργία δεκάδων διαγραμμάτων άμεσα για πίνακες ελέγχου ή μαζικές αναφορές.  
- **Διαπλατφόρμα** – λειτουργεί σε οποιοδήποτε OS που υποστηρίζει Java, χωρίς ανάγκη εγκατάστασης Office.  
- **Απόδοση** – ελαφρύ API που διαχειρίζεται μεγάλα σύνολα δεδομένων αποδοτικά.

## Προαπαιτούμενα

Για να ακολουθήσετε, βεβαιωθείτε ότι έχετε:

- **Aspose.Slides for Java** (v25.4 ή νεότερη).  
- **Java Development Kit (JDK)** 8 + εγκατεστημένο.  
- Maven ή Gradle για διαχείριση εξαρτήσεων (ή μπορείτε να κατεβάσετε το JAR χειροκίνητα).  
- Βασικές γνώσεις Java και εξοικείωση με το εργαλείο κατασκευής της επιλογής σας.

## Ρύθμιση Aspose.Slides για Java

Ενσωματώστε τη βιβλιοθήκη στο έργο σας χρησιμοποιώντας μία από τις παρακάτω μεθόδους.

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

Ή κατεβάστε την τελευταία έκδοση από [Aspose Releases](https://releases.aspose.com/slides/java/).

#### Απόκτηση Άδειας
- **Δωρεάν Δοκιμή** – αξιολόγηση 30 ημερών.  
- **Προσωρινή Άδεια** – παρατεταμένη περίοδος δοκιμής.  
- **Πλήρης Άδεια** – χρήση σε παραγωγή με premium υποστήριξη.

## Οδηγός βήμα‑βήμα για την προσαρμογή Scatter Chart Aspose

### 1️⃣ Προετοιμάστε έναν φάκελο για τα αρχεία παρουσίασης
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```
*Γιατί είναι σημαντικό:* Η εξασφάλιση ότι ο φάκελος εξόδου υπάρχει αποτρέπει το `FileNotFoundException` όταν αποθηκεύετε αργότερα το PPTX.

### 2️⃣ Δημιουργήστε μια νέα παρουσίαση και πάρτε την πρώτη διαφάνεια
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```
Ένα νέο `Presentation` σας παρέχει έναν καθαρό καμβά· η πρώτη διαφάνεια είναι όπου θα τοποθετήσουμε το διάγραμμα.

### 3️⃣ Προσθέστε ένα scatter chart με ομαλές γραμμές
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
Το `ChartType.ScatterWithSmoothLines` δημιουργεί ένα scatter chart με ομαλές γραμμές, ιδανικό για οπτικοποίηση τάσεων.

### 4️⃣ Καθαρίστε τυχόν προεπιλεγμένες σειρές και προσθέστε τις δικές σας
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
Η αφαίρεση των προεπιλεγμένων σειρών σας δίνει πλήρη έλεγχο στα δεδομένα που εμφανίζετε.

### 5️⃣ Συμπληρώστε την πρώτη σειρά με σημεία δεδομένων
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```
`addDataPointForScatterSeries` παίρνει ένα κελί τιμής X και ένα κελί τιμής Y, δημιουργώντας το scatter plot σημείο‑με‑σημείο.

### 6️⃣ Προσαρμόστε τον τύπο σειράς και την εμφάνιση των δεικτών
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
Εδώ **προσαρμόζουμε το scatter chart aspose** αλλάζοντας σε ευθείες γραμμές, μεγενθυνοντας τους δείκτες και επιλέγοντας διακριτικά σύμβολα (αστέρι vs. κύκλο) για οπτική σαφήνεια.

### 7️⃣ Αποθηκεύστε την παρουσίαση
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```
Η αποθήκευση ως `Pptx` διατηρεί όλες τις προσαρμογές του διαγράμματος και κάνει το αρχείο έτοιμο για κοινή χρήση ή περαιτέρω επεξεργασία.

## Συνηθισμένες Περιπτώσεις Χρήσης για Προσαρμοσμένα Scatter Charts
- **Οικονομικοί πίνακες ελέγχου** – απεικόνιση τιμής μετοχής vs. όγκος.  
- **Επιστημονική έρευνα** – εμφάνιση πειραματικών μετρήσεων με δείκτες σφάλματος.  
- **Διαχείριση έργου** – σύγκριση προγραμματισμένης vs. πραγματικής προσπάθειας ανά εργασία.  

## Συμβουλές Απόδοσης
- Αποδεσμεύστε το αντικείμενο `Presentation` (`pres.dispose()`) μετά την αποθήκευση για να ελευθερώσετε τους εγγενείς πόρους.  
- Για μεγάλα σύνολα δεδομένων, γεμίστε πρώτα το workbook και στη συνέχεια συνδέστε τις σειρές για να αποφύγετε επαναλαμβανόμενες ανανεώσεις UI.  
- Επαναχρησιμοποιήστε ένα μόνο αντικείμενο `IChartDataWorkbook` όταν προσθέτετε πολλές σειρές.

## Συχνές Ερωτήσεις

### Πώς αλλάζω το χρώμα των δεικτών;
Χρησιμοποιήστε `series.getMarker().getFillFormat().setFillColor(Color)` όπου το `Color` είναι μια παρουσία του `java.awt.Color` (π.χ., `Color.RED`).

### Μπορώ να προσθέσω περισσότερες από δύο σειρές σε ένα scatter chart;
Απολύτως. Επαναλάβετε την κλήση `chart.getChartData().getSeries().add(...)` για κάθε επιπλέον σειρά και συμπληρώστε τα σημεία δεδομένων της ανάλογα.

### Είναι δυνατόν να ορίσετε προσαρμοσμένο υπόμνημα για κάθε σειρά;
Ναι. Μετά τη δημιουργία μιας σειράς, καλέστε `series.getLegend().setText("Your Legend Text")` για να αντικαταστήσετε το προεπιλεγμένο όνομα.

### Πώς μπορώ να εξάγω το διάγραμμα ως εικόνα αντί για PPTX;
Καλέστε `chart.getImage().save("chart.png", ImageFormat.Png)` μετά τη διαμόρφωση του διαγράμματος. Αυτό σας δίνει ένα αυτόνομο αρχείο PNG.

### Τι γίνεται αν χρειαστεί να ανιματίσω τα σημεία του scatter;
Το Aspose.Slides υποστηρίζει εφέ κίνησης. Χρησιμοποιήστε `chart.getTimeline().getMainSequence().addEffect(...)` για να προσθέσετε εφέ εισόδου ή έμφασης στο διάγραμμα ή σε μεμονωμένες σειρές.

---

**Τελευταία ενημέρωση:** 2026-02-24  
**Δοκιμή με:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}