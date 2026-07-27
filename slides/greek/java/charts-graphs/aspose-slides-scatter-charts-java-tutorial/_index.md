---
date: '2026-07-27'
description: Πώς να προσαρμόσετε το chart χρησιμοποιώντας το Aspose.Slides για Java.
  Μάθετε πώς να δημιουργήσετε chart PowerPoint, να μορφοποιήσετε τη σειρά scatter
  και να αποθηκεύετε παρουσιάσεις αποδοτικά.
keywords:
- how to customize chart
- java create powerpoint chart
- Aspose.Slides scatter chart
lastmod: '2026-07-27'
og_description: Πώς να προσαρμόσετε το chart με το Aspose.Slides για Java. Αυτός ο
  οδηγός δείχνει πώς να δημιουργήσετε chart PowerPoint, να μορφοποιήσετε σημεία scatter
  και να εξάγετε παρουσιάσεις.
og_image_alt: 'Guide: Customize scatter chart in Java using Aspose.Slides'
og_title: 'Πώς να προσαρμόσετε το chart: Scatter Chart Aspose σε Java'
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: How to customize chart using Aspose.Slides for Java. Learn to create
    PowerPoint chart, style scatter series, and save presentations efficiently.
  headline: 'How to Customize Chart: Scatter Chart Aspose in Java'
  type: TechArticle
- questions:
  - answer: Use `series.getMarker().getFillFormat().setFillColor(Color)` where `Color`
      is a `java.awt.Color` instance such as `Color.RED`.
    question: How do I change the color of the markers?
  - answer: Yes. Call `chart.getChartData().getSeries().add(...)` for each additional
      series and populate its points accordingly.
    question: Can I add more than two series to a scatter chart?
  - answer: Absolutely. After creating a series, invoke `series.getLegend().setText("Your
      Legend Text")` to override the default name.
    question: Is it possible to set a custom legend for each series?
  - answer: Call `chart.getImage().save("chart.png", ImageFormat.Png)` after configuring
      the chart. This produces a standalone PNG file.
    question: How can I export the chart as an image instead of a PPTX?
  - answer: Aspose.Slides supports animation effects. Use `chart.getTimeline().getMainSequence().addEffect(...)`
      to add entrance or emphasis animations to the chart or individual series.
    question: What if I need to animate the scatter points?
  type: FAQPage
tags:
- customize chart
- Aspose.Slides
- Java charting
title: 'Πώς να προσαρμόσετε το chart: Scatter Chart Aspose σε Java'
url: /el/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Προσαρμογή Scatter Chart Aspose σε Java

Σε αυτό το tutorial θα ανακαλύψετε **πώς να προσαρμόσετε ένα διάγραμμα** — συγκεκριμένα ένα scatter chart — χρησιμοποιώντας τη δυναμική βιβλιοθήκη Aspose.Slides for Java. Θα περάσουμε από τη ρύθμιση του έργου, τη δημιουργία ενός scatter chart, την προσαρμογή τύπων σειρών και σημείων, και τέλος την αποθήκευση της παρουσίασης. Στο τέλος, θα μπορείτε να δημιουργήσετε επαγγελματικά scatter charts προγραμματιστικά και να προσαρμόσετε κάθε οπτικό στοιχείο ώστε να ταιριάζει με το brand ή τις ανάγκες αναφοράς σας.

## Γρήγορες Απαντήσεις
- **Τι βιβλιοθήκη χρειάζομαι;** Aspose.Slides for Java (v25.4+).  
- **Ποια έκδοση Java υποστηρίζεται;** JDK 8 ή νεότερη.  
- **Μπορώ να αλλάξω τα σχήματα των σημείων;** Ναι – χρησιμοποιήστε `MarkerStyleType` για να επιλέξετε αστέρια, κύκλους κ.λπ.  
- **Πώς αποθηκεύεται το αρχείο;** Κλήση `pres.save("output.pptx", SaveFormat.Pptx)`.  
- **Απαιτείται άδεια;** Δωρεάν δοκιμή λειτουργεί για ανάπτυξη· εμπορική άδεια απαιτείται για παραγωγή.

## Πώς να Προσαρμόσετε το Διάγραμμα σε Java με Aspose.Slides;
`Presentation` είναι η κλάση Aspose.Slides που αντιπροσωπεύει ολόκληρο το αρχείο PowerPoint στη μνήμη. Φορτώστε ένα νέο `Presentation`, προσθέστε ένα scatter chart στην πρώτη διαφάνεια, ρυθμίστε τις σειρές και τα στυλ των σημείων, και στη συνέχεια καλέστε `save`. Αυτή η ενιαία ροή εργασίας δημιουργεί ένα πλήρως μορφοποιημένο διάγραμμα σε λίγες γραμμές κώδικα Java, έτοιμο για ενσωμάτωση σε οποιαδήποτε παρουσίαση PowerPoint.

## Τι είναι το “customize scatter chart aspose”;
Η προσαρμογή ενός scatter chart με το Aspose σημαίνει ορισμός προγραμματιστικά των δεδομένων, της εμφάνισης και της συμπεριφοράς του διαγράμματος — από τις συντεταγμένες των σημείων μέχρι τα σύμβολα των σημείων — χωρίς να ανοίξετε το PowerPoint χειροκίνητα. Αυτή η προσέγγιση είναι ιδανική για αυτοματοποιημένες αναφορές, παρουσιάσεις βάσει δεδομένων ή οποιοδήποτε σενάριο που απαιτεί επαναλαμβανόμενες, υψηλής ποιότητας οπτικοποιήσεις.

## Γιατί να προσαρμόζετε scatter charts με Aspose.Slides;
Aspose.Slides παρέχει στους προγραμματιστές πλήρη προγραμματιστικό έλεγχο της εμφάνισης των διαγραμμάτων, επιτρέποντας την αυτόματη δημιουργία υψηλής ποιότητας οπτικοποιήσεων, την απρόσκοπτη ενσωμάτωση σε pipelines αναφορών, και τη δυνατότητα προσαρμογής κάθε οπτικού στοιχείου χωρίς το άνοιγμα του PowerPoint, κάτι που εξοικονομεί χρόνο και εξασφαλίζει συνέπεια σε όλες τις παρουσιάσεις.

- **Πλήρης έλεγχος** – τροποποίηση τύπων σειρών, στυλ σημείων, χρωμάτων και άλλων μέσω κώδικα Java.  
- **Αυτοματοποίηση** – δημιουργία δεκάδων διαγραμμάτων άμεσα για dashboards ή μαζικές αναφορές.  
- **Διαπλατφόρμα** – λειτουργεί σε οποιοδήποτε OS που υποστηρίζει Java, χωρίς ανάγκη εγκατάστασης Office.  
- **Απόδοση** – ελαφρύ API που επεξεργάζεται **150+ τύπους διαγραμμάτων** και διαχειρίζεται παρουσιάσεις εκατοντάδων σελίδων χωρίς φόρτωση ολόκληρου του αρχείου στη μνήμη.

## Προαπαιτούμενα

Για να ακολουθήσετε το tutorial, βεβαιωθείτε ότι έχετε:

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
- **Δωρεάν Δοκιμή** – 30‑ήμερη αξιολόγηση.  
- **Προσωρινή Άδεια** – παρατεταμένη δοκιμαστική περίοδος.  
- **Πλήρης Άδεια** – χρήση σε παραγωγή με premium υποστήριξη.

## Οδηγός Βήμα‑βήμα για την Προσαρμογή Scatter Chart Aspose

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
*Γιατί είναι σημαντικό:* Η διασφάλιση ότι ο φάκελος εξόδου υπάρχει αποτρέπει `FileNotFoundException` όταν αποθηκεύσετε το PPTX.

### 2️⃣ Δημιουργήστε μια νέα παρουσίαση και πάρτε την πρώτη διαφάνεια
`Presentation` αντιπροσωπεύει ένα έγγραφο PowerPoint και παρέχει πρόσβαση σε διαφάνειες και σχήματα. Η κλάση `Presentation` αντιπροσωπεύει ολόκληρο το αρχείο PowerPoint στη μνήμη.  
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### 3️⃣ Προσθέστε ένα scatter chart με ομαλές γραμμές
`ChartType.ScatterWithSmoothLines` δημιουργεί ένα scatter chart όπου τα σημεία συνδέονται με ομαλές γραμμές.  
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

### 4️⃣ Καθαρίστε τυχόν προεπιλεγμένες σειρές και προσθέστε τις δικές σας
`IChartSeries` αντιπροσωπεύει μια σειρά δεδομένων μέσα σε ένα διάγραμμα.  
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

### 5️⃣ Συμπληρώστε την πρώτη σειρά με σημεία δεδομένων
`addDataPointForScatterSeries` προσθέτει ένα μοναδικό σημείο X‑Y σε μια σειρά scatter.  
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```

### 6️⃣ Προσαρμόστε τον τύπο σειράς και την εμφάνιση των σημείων
`Marker` ελέγχει το οπτικό σύμβολο που χρησιμοποιείται για κάθε σημείο δεδομένων σε μια σειρά διαγράμματος.  
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

### 7️⃣ Αποθηκεύστε την παρουσίαση
`save` γράφει την παρουσίαση σε αρχείο με τη συγκεκριμένη μορφή.  
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Συνηθισμένες Περιπτώσεις Χρήσης για Προσαρμοσμένα Scatter Charts
- **Οικονομικά dashboards** – απεικόνιση τιμής μετοχής έναντι όγκου.  
- **Επιστημονική έρευνα** – παρουσίαση πειραματικών μετρήσεων με σημεία σφάλματος.  
- **Διαχείριση έργων** – σύγκριση προγραμματισμένου vs. πραγματικού κόστους σε εργασίες.  

## Συμβουλές Απόδοσης
- Κλήση `pres.dispose()` μετά την αποθήκευση για απελευθέρωση εγγενούς μνήμης.  
- Για μεγάλα σύνολα δεδομένων, συμπληρώστε πρώτα το workbook και στη συνέχεια συνδέστε τη σειρά για αποφυγή επαναλαμβανόμενων ανανεώσεων UI.  
- Επαναχρησιμοποίηση ενός μοναδικού αντικειμένου `IChartDataWorkbook` όταν προσθέτετε πολλές σειρές ώστε η χρήση μνήμης να παραμένει χαμηλή.

## Συχνές Ερωτήσεις

**Ε: Πώς αλλάζω το χρώμα των σημείων;**  
Α: Χρησιμοποιήστε `series.getMarker().getFillFormat().setFillColor(Color)` όπου `Color` είναι μια παρουσία `java.awt.Color` όπως `Color.RED`.

**Ε: Μπορώ να προσθέσω περισσότερες από δύο σειρές σε ένα scatter chart;**  
Α: Ναι. Κλήση `chart.getChartData().getSeries().add(...)` για κάθε επιπλέον σειρά και συμπλήρωση των σημείων της.

**Ε: Είναι δυνατόν να ορίσω προσαρμοσμένο υπόμνημα για κάθε σειρά;**  
Α: Απόλυτα. Μετά τη δημιουργία μιας σειράς, καλέστε `series.getLegend().setText("Your Legend Text")` για να αντικαταστήσετε το προεπιλεγμένο όνομα.

**Ε: Πώς μπορώ να εξάγω το διάγραμμα ως εικόνα αντί για PPTX;**  
Α: Κλήση `chart.getImage().save("chart.png", ImageFormat.Png)` μετά τη διαμόρφωση του διαγράμματος. Αυτό παράγει ένα αυτόνομο αρχείο PNG.

**Ε: Τι γίνεται αν θέλω να ανιματοποιήσω τα σημεία scatter;**  
Α: Το Aspose.Slides υποστηρίζει εφέ animation. Χρησιμοποιήστε `chart.getTimeline().getMainSequence().addEffect(...)` για να προσθέσετε εφέ εισόδου ή έμφασης στο διάγραμμα ή σε μεμονωμένες σειρές.

---

**Τελευταία Ενημέρωση:** 2026-07-27  
**Δοκιμάστηκε με:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Συγγραφέας:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Σχετικά Μαθήματα

- [Δημιουργία και Προσαρμογή Διαγραμμάτων PowerPoint σε Java με χρήση Aspose.Slides](/slides/java/charts-graphs/java-aspose-slides-powerpoint-charts-automation/)
- [Πώς να Δημιουργήσετε Bubble Chart στο PowerPoint Χρησιμοποιώντας Aspose.Slides for Java (Tutorial)](/slides/java/charts-graphs/create-bubble-charts-powerpoint-aspose-slides-java/)
- [Δημιουργία και Προσαρμογή Διαγραμμάτων με Γραμμές Τάσης σε Aspose.Slides for Java](/slides/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}