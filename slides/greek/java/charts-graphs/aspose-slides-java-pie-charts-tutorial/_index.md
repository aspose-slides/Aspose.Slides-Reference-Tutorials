---
date: '2026-07-17'
description: Μάθετε πώς να περιστρέψετε το διάγραμμα πίτας, να προσαρμόσετε τα χρώματα
  του διαγράμματος πίτας και να εξάγετε τη διαφάνεια σε PDF χρησιμοποιώντας το Aspose.Slides
  για Java – έναν πλήρη οδηγό data visualization.
keywords:
- rotate pie chart
- customize pie chart colors
- export slide to pdf
- chart data worksheet
- java data visualization
lastmod: '2026-07-17'
og_description: Περιστρέψτε το διάγραμμα πίτας και προσαρμόστε τα χρώματα του διαγράμματος
  πίτας χρησιμοποιώντας το Aspose.Slides για Java. Μάθετε πώς να εξάγετε τη διαφάνεια
  σε PDF και να εργαστείτε με το chart data worksheet.
og_image_alt: Guide showing how to rotate a pie chart and set custom colors in Java
  with Aspose.Slides
og_title: Περιστροφή διαγράμματος πίτας και προσαρμογή χρωμάτων σε Java – Οδηγός Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to rotate pie chart, customize pie chart colors, and export
    slide to PDF using Aspose.Slides for Java – a full data visualization guide.
  headline: How to Rotate Pie Chart and Customize Colors in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Request a free trial from the Aspose website, then purchase a permanent
      license. Load it at runtime as shown in the Common Issues table.
    question: How do I obtain an Aspose.Slides license for Java?
  - answer: The API requires JDK 16 or higher; older versions are not supported.
    question: Can I use this code with older JDK versions?
  - answer: Yes—after rendering, call `chart.getChartData().getChartDataWorkbook().save("chart.png",
      ImageFormat.Png);`.
    question: Is it possible to export the chart as an image instead of PPTX?
  - answer: Pie charts are designed for a single data series; for multiple series,
      consider using a doughnut chart.
    question: What if I need more than one series in a pie chart?
  - answer: Absolutely—Aspose.Slides for Java is platform‑independent and works on
      any OS with a compatible JDK.
    question: Does Aspose.Slides run on Linux servers?
  type: FAQPage
tags:
- rotate pie chart
- Aspose.Slides
- Java charting
- data visualization
title: Πώς να περιστρέψετε το διάγραμμα πίτας και να προσαρμόσετε τα χρώματα σε Java
  με Aspose.Slides
url: /el/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Δημιουργία Διαγραμμάτων Πίτας με το Aspose.Slides για Java: Ένα Πλήρες Εγχειρίδιο

## Εισαγωγή
Σε αυτόν τον οδηγό θα μάθετε πώς να **περιστρέφετε διαγράμματα πίτας**, να προσαρμόζετε το χρώμα κάθε φέτας και να εξάγετε την τελική διαφάνεια σε PDF — όλα με το Aspose.Slides για Java. Είτε δημιουργείτε έναν πίνακα ελέγχου πωλήσεων, μια οικονομική αναφορά ή οποιαδήποτε παρουσίαση βασισμένη σε δεδομένα, η εξοικείωση με αυτές τις τεχνικές σας επιτρέπει να παρέχετε σαφή, εντυπωσιακά οπτικά στοιχεία χωρίς να βασίζεστε στο Microsoft Office. Ας ετοιμάσουμε τα εργαλεία και ας ξεκινήσουμε.

## Γρήγορες Απαντήσεις
- **Ποια κλάση ξεκινά μια νέα παρουσίαση;** `Presentation` from `com.aspose.slides`.
- **Ποια κλήση API προσθέτει ένα διάγραμμα πίτας;** `slide.addChart(ChartType.Pie, …)`.
- **Πώς μπορείτε να δώσετε σε κάθε φέτα ένα μοναδικό χρώμα;** Call `series.setColorVaried(true)` and set solid fills per data point.
- **Ποια μέθοδος περιστρέφει το διάγραμμα;** `chart.setRotationAngle(double)` – use degrees from 0 to 360.
- **Μπορεί η διαφάνεια να εξαχθεί σε PDF;** Yes, invoke `presentation.save("output.pdf", SaveFormat.Pdf)`.

## Τι σημαίνει «προσαρμογή χρωμάτων διαγράμματος πίτας»;
Η προσαρμογή χρωμάτων διαγράμματος πίτας σημαίνει την ανάθεση διαφορετικών χρωμάτων γεμίσματος σε κάθε φέτα της πίτας, βελτιώνοντας την αναγνωσιμότητα και την οπτική επίδραση. Στο Aspose.Slides το επιτυγχάνετε ενεργοποιώντας τα διαφορετικά χρώματα και στη συνέχεια ορίζοντας στερεά χρώματα γεμίσματος για μεμονωμένα σημεία δεδομένων. Αυτή η προσέγγιση διασφαλίζει ότι κάθε τμήμα δεδομένων ξεχωρίζει καθαρά στην παρουσίαση.

## Γιατί να χρησιμοποιήσετε το Aspose.Slides για Java για τη δημιουργία διαγραμμάτων πίτας;
Το Aspose.Slides υποστηρίζει **150+ τύπους διαγραμμάτων** και μπορεί να αποδώσει μια παρουσίαση 300 σελίδων σε λιγότερο από **5 δευτερόλεπτα** σε έναν τυπικό διακομιστή, χωρίς να απαιτείται εγκατάσταση του Microsoft Office. Η βιβλιοθήκη λειτουργεί σε Windows, Linux και macOS, προσφέροντας διασταυρούμενη πλατφόρμα ευελιξία για οποιοδήποτε έργο οπτικοποίησης δεδομένων σε Java.

## Προαπαιτούμενα
- **Aspose.Slides for Java** ≥ 25.4
- **JDK** 16 ή νεότερο
- IDE όπως IntelliJ IDEA, Eclipse ή NetBeans
- Βασικές γνώσεις Java και εξοικείωση με Maven ή Gradle

## Ρύθμιση του Aspose.Slides για Java
Προσθέστε τη βιβλιοθήκη στη διαμόρφωση του build σας.

**Maven**  
Προσθέστε αυτό το απόσπασμα στο αρχείο `pom.xml` σας:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
Συμπεριλάβετε το ακόλουθο στο αρχείο `build.gradle` σας:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direct Download**  
Αν προτιμάτε χειροκίνητη προσέγγιση, κατεβάστε το τελευταίο JAR από [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Βήματα Απόκτησης Άδειας
- **Δωρεάν Δοκιμή** – εξερευνήστε όλες τις λειτουργίες χωρίς κόστος.  
- **Προσωρινή Άδεια** – επεκτείνετε τα όρια της δοκιμής για σύντομο χρονικό διάστημα.  
- **Αγορά** – αποκτήστε μόνιμη άδεια για παραγωγική χρήση.

**Βασική Αρχικοποίηση και Ρύθμιση**  
Η κλάση `Presentation` αντιπροσωπεύει ένα αρχείο PowerPoint στη μνήμη και παρέχει μεθόδους για τη διαχείριση των διαφανειών.  
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Οδηγός Υλοποίησης
Παρακάτω ακολουθεί ένας βήμα‑βήμα οδηγός που καλύπτει όλα, από τη δημιουργία μιας διαφάνειας μέχρι την περιστροφή του τελικού διαγράμματος πίτας.

### Αρχικοποίηση Παρουσίασης και Διαφάνειας
Δημιουργήστε ένα νέο αντικείμενο `Presentation` και ανακτήστε την πρώτη διαφάνεια ώστε να λειτουργήσει ως καμβάς του διαγράμματος.  
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
ISlide slide = presentation.getSlides().get_Item(0);
```

### Προσθήκη Διαγράμματος Πίτας στη Διαφάνεια
`addChart` προσθέτει ένα σχήμα διαγράμματος του καθορισμένου τύπου στη διαφάνεια στις δοσμένες συντεταγμένες.  
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Ορισμός Τίτλου Διαγράμματος
`setTitle` αναθέτει έναν τίτλο κειμένου στο διάγραμμα και τον τοποθετεί κεντρικά.  
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Διαμόρφωση Ετικετών Δεδομένων για τη Σειρά
`setShowValue(true)` ενεργοποιεί τις ετικέτες αριθμητικών τιμών σε κάθε σημείο δεδομένων της σειράς.  
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Προετοιμασία Φύλλου Δεδομένων Διαγράμματος
`ChartDataWorkbook` αποθηκεύει τον υποκείμενο πίνακα δεδομένων που τροφοδοτεί τις σειρές και τις κατηγορίες του διαγράμματος.  
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Προσθήκη Κατηγοριών στο Διάγραμμα
`addCategory` δημιουργεί μια νέα ετικέτα κατηγορίας για τις σειρές δεδομένων του διαγράμματος.  
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Προσθήκη Σειράς και Συμπλήρωση Σημείων Δεδομένων
`addSeries` δημιουργεί μια σειρά δεδομένων, και `addDataPointForBarSeries` εισάγει αριθμητικές τιμές για κάθε κατηγορία.  
```java
import com.aspose.slides.*;

// Add a new series and set its name.
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Προσαρμογή Χρωμάτων και Περιγραμμάτων Σειράς
`setColorVaried(true)` ενεργοποιεί διαφορετικά χρώματα ανά φέτα, και `setFillFormat` ορίζει στερεό γέμισμα για κάθε σημείο δεδομένων.  
```java
import com.aspose.slides.*;

// Set varied colors for the series sectors.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Repeat for other data points with different colors and styles.
```

### Διαμόρφωση Προσαρμοσμένων Ετικετών Δεδομένων
`setDataLabelFormat` προσαρμόζει την εμφάνιση, τη θέση και τη γραμματοσειρά της ετικέτας για πιο καθαρές σημειώσεις στο διάγραμμα.  
```java
import com.aspose.slides.*;

// Configure custom labels.
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Enable leader lines for labels.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### Ορισμός Γωνίας Περιστροφής και Αποθήκευση Παρουσίασης
`setRotationAngle` περιστρέφει ολόκληρο το διάγραμμα πίτας, και `save` γράφει την παρουσίαση σε αρχείο.  
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## Πώς να περιστρέψετε το διάγραμμα πίτας;
Φορτώστε το αντικείμενο διαγράμματος, καλέστε `chart.setRotationAngle(45.0)` (ή οποιαδήποτε τιμή σε μοίρες), και στη συνέχεια αποθηκεύστε την παρουσίαση. Η περιστροφή ενός διαγράμματος πίτας μετατοπίζει τη γωνία εκκίνησης, επιτρέποντάς σας να τονίσετε ένα συγκεκριμένο τμήμα χωρίς να αλλάξετε τα δεδομένα. Αυτή η ενιαία κλήση μεθόδου λειτουργεί για οποιοδήποτε αντικείμενο `Chart` στο Aspose.Slides. Μπορείτε επίσης να συνδυάσετε την περιστροφή με διαφορετικά χρώματα φετών για να εστιάσετε στο πιο σημαντικό δεδομένο.

## Συχνά Προβλήματα και Λύσεις
| Πρόβλημα | Αιτία | Λύση |
|----------|-------|------|
| **Οι φέτες εμφανίζονται όλες το ίδιο χρώμα** | `setColorVaried(true)` δεν κλήθηκε | Βεβαιωθείτε ότι έχετε ενεργοποιήσει τα διαφορετικά χρώματα στην ομάδα σειρών. |
| **Οι ετικέτες δεδομένων δεν εμφανίζονται** | `showValue` σημαία απενεργοποιημένη | Καλέστε `setShowValue(true)` στη μορφή ετικέτας. |
| **Η περιστροφή δεν έχει αποτέλεσμα** | Χρήση παλαιότερης έκδοσης Aspose.Slides | Αναβαθμίστε στην έκδοση 25.4 ή νεότερη. |
| **Εξαίρεση άδειας κατά την εκτέλεση** | Απουσία ή μη έγκυρο αρχείο άδειας | Φορτώστε την άδειά σας με `License license = new License(); license.setLicense("Aspose.Slides.lic");` πριν δημιουργήσετε το `Presentation`. |

## Συχνές Ερωτήσεις

**Π: Πώς μπορώ να αποκτήσω άδεια Aspose.Slides για Java;**  
Α: Ζητήστε μια δωρεάν δοκιμή από τον ιστότοπο Aspose, στη συνέχεια αγοράστε μόνιμη άδεια. Φορτώστε την κατά την εκτέλεση όπως φαίνεται στον πίνακα Συχνών Προβλημάτων.

**Π: Μπορώ να χρησιμοποιήσω αυτόν τον κώδικα με παλαιότερες εκδόσεις JDK;**  
Α: Το API απαιτεί JDK 16 ή νεότερο· οι παλαιότερες εκδόσεις δεν υποστηρίζονται.

**Π: Είναι δυνατόν να εξαχθεί το διάγραμμα ως εικόνα αντί για PPTX;**  
Α: Ναι—μετά την απόδοση, καλέστε `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);`.

**Π: Τι γίνεται αν χρειάζομαι περισσότερες από μία σειρές σε ένα διάγραμμα πίτας;**  
Α: Τα διαγράμματα πίτας σχεδιάζονται για μία μόνο σειρά δεδομένων· για πολλαπλές σειρές, εξετάστε τη χρήση διαγράμματος δακτυλίου.

**Π: Εκτελείται το Aspose.Slides σε διακομιστές Linux;**  
Α: Απόλυτα—το Aspose.Slides για Java είναι ανεξάρτητο από πλατφόρμα και λειτουργεί σε οποιοδήποτε OS με συμβατό JDK.

**Τελευταία Ενημέρωση:** 2026-07-17  
**Δοκιμή Με:** Aspose.Slides for Java 25.4 (JDK 16)  
**Συγγραφέας:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Σχετικά Μαθήματα

- [Πώς να Δημιουργήσετε Διαγράμματα Πίτας σε Παρουσιάσεις Java Χρησιμοποιώντας το Aspose.Slides: Ένας Πλήρης Οδηγός](/slides/java/charts-graphs/creating-pie-charts-java-presentations-aspose-slides/)
- [Κατακτήστε τα Διαγράμματα Πίτας σε Java Χρησιμοποιώντας το Aspose.Slides: Ένας Πλήρης Οδηγός](/slides/java/charts-graphs/master-pie-charts-aspose-slides-java/)
- [Περιστροφή Κειμένων Διαγράμματος σε Java με το Aspose.Slides: Ένας Πλήρης Οδηγός](/slides/java/charts-graphs/rotate-chart-texts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}