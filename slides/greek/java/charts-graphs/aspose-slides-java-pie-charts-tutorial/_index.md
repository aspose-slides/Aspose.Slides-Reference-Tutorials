---
date: '2026-02-19'
description: Μάθετε πώς να δημιουργήσετε ένα διάγραμμα πίτας σε Java με το Aspose.Slides,
  να προσαρμόσετε τα χρώματα του διαγράμματος, να προσθέσετε σειρές διαγράμματος,
  να εργαστείτε με το φύλλο δεδομένων του διαγράμματος και να ορίσετε τη γωνία περιστροφής.
keywords:
- Aspose.Slides Java
- Java pie charts
- data visualization in Java
title: Πώς να προσαρμόσετε τα χρώματα του διαγράμματος πίτας σε Java με το Aspose.Slides
  – Ένας πλήρης οδηγός
url: /el/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Δημιουργία Διαγραμμάτων Πίτας με το Aspose.Slides for Java: Ένα Πλήρες Εγχειρίδιο

## Εισαγωγή
Η δημιουργία δυναμικών και οπτικά ελκυστικών παρουσιάσεων είναι κρίσιμη για τη μετάδοση ισχυρών πληροφοριών. Με το Aspose.Slides for Java, μπορείτε να ενσωματώσετε άψογα σύνθετα διαγράμματα όπως τα διαγράμματα πίτας στις διαφάνειές σας, **να προσαρμόσετε τα χρώματα του διαγράμματος πίτας** και να ενισχύσετε την οπτικοποίηση δεδομένων χωρίς κόπο. Αυτός ο ολοκληρωμένος οδηγός θα σας καθοδηγήσει στη διαδικασία δημιουργίας και προσαρμογής ενός διαγράμματος πίτας χρησιμοποιώντας το Aspose.Slides Java, λύνοντας κοινά προβλήματα παρουσιάσεων με ευκολία.

**Τι θα μάθετε:**
- Αρχικοποίηση παρουσίασης και προσθήκη διαφανειών.
- Δημιουργία και διαμόρφωση διαγράμματος πίτας στη διαφάνεια.
- Ορισμός τίτλων διαγράμματος, ετικετών δεδομένων και **προσαρμογή χρωμάτων διαγράμματος πίτας**.
- Βελτιστοποίηση απόδοσης και αποτελεσματική διαχείριση πόρων.
- Ενσωμάτωση Aspose.Slides σε έργα Java χρησιμοποιώντας Maven ή Gradle.

Ας ξεκινήσουμε διασφαλίζοντας ότι έχετε όλα τα απαραίτητα εργαλεία και γνώσεις για να ακολουθήσετε!

## Γρήγορες Απαντήσεις
- **Ποια είναι η κύρια κλάση για την έναρξη μιας παρουσίασης;** `Presentation` από `com.aspose.slides`.
- **Ποια μέθοδος προσθέτει διάγραμμα πίτας σε μια διαφάνεια;** `addChart(ChartType.Pie, …)`.
- **Πώς ενεργοποιείτε διαφορετικά χρώματα για κάθε φέτα;** Ορίστε `setColorVaried(true)` στην ομάδα σειράς.
- **Μπορείτε να περιστρέψετε το διάγραμμα πίτας;** Ναι, χρησιμοποιήστε `setRotationAngle(double)` στο αντικείμενο διαγράμματος.
- **Χρειάζομαι άδεια για χρήση σε παραγωγή;** Απαιτείται άδεια Aspose.Slides για εμπορικές αναπτύξεις.

## Τι σημαίνει “προσαρμογή χρωμάτων διαγράμματος πίτας”;
Η προσαρμογή χρωμάτων διαγράμματος πίτας σημαίνει η ανάθεση διαφορετικών χρωμάτων γεμίσματος σε κάθε φέτα της πίτας, βελτιώνοντας την αναγνωσιμότητα και την οπτική επίδραση. Στο Aspose.Slides το επιτυγχάνετε ενεργοποιώντας διαφορετικά χρώματα και στη συνέχεια ορίζοντας χρώματα γεμίσματος για μεμονωμένα σημεία δεδομένων.

## Γιατί να χρησιμοποιήσετε Aspose.Slides for Java για τη δημιουργία διαγραμμάτων πίτας;
- **Πλήρης έλεγχος** της εμφάνισης του διαγράμματος χωρίς ανάγκη Microsoft Office.
- **Διασυστημική** συμβατότητα – λειτουργεί σε Windows, Linux και macOS.
- **Πλούσιο API** για σύνδεση δεδομένων, στυλιζάρισμα και εξαγωγή σε PPTX, PDF ή εικόνες.
- **Ευελιξία αδειών** – ξεκινήστε με δωρεάν δοκιμή και αναβαθμίστε όταν χρειάζεστε το πλήρες σύνολο λειτουργιών.

## Προαπαιτούμενα
Πριν βυθιστείτε σε αυτό το εγχειρίδιο, βεβαιωθείτε ότι έχετε την παρακάτω διαμόρφωση έτοιμη:

### Απαιτούμενες Βιβλιοθήκες, Εκδόσεις και Εξαρτήσεις
- **Aspose.Slides for Java**: έκδοση 25.4 ή νεότερη.
- **Java Development Kit (JDK)**: έκδοση 16 ή υψηλότερη.

### Απαιτήσεις Περιβάλλοντος
- Περιβάλλον ανάπτυξης με εγκατεστημένη και ρυθμισμένη Java.
- Ένα ολοκληρωμένο περιβάλλον ανάπτυξης (IDE) όπως IntelliJ IDEA, Eclipse ή NetBeans.

### Προαπαιτούμενες Γνώσεις
- Βασική κατανόηση του προγραμματισμού Java.
- Εξοικείωση με Maven ή Gradle για διαχείριση εξαρτήσεων.

## Ρύθμιση Aspose.Slides for Java
Για να αρχίσετε να χρησιμοποιείτε το Aspose.Slides στα έργα Java, πρέπει να προσθέσετε τη βιβλιοθήκη ως εξάρτηση. Δείτε πώς μπορείτε να το κάνετε με διαφορετικά εργαλεία κατασκευής:

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

**Άμεση Λήψη**  
Αν προτιμάτε να μην χρησιμοποιήσετε εργαλείο κατασκευής, κατεβάστε την τελευταία έκδοση από [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Βήματα Απόκτησης Άδειας
- **Δωρεάν Δοκιμή**: Ξεκινήστε με δωρεάν δοκιμή για να εξερευνήσετε τις δυνατότητες του Aspose.Slides.  
- **Προσωρινή Άδεια**: Αποκτήστε προσωρινή άδεια για παρατεταμένη χρήση χωρίς περιορισμούς.  
- **Αγορά**: Σκεφτείτε την αγορά εάν χρειάζεστε μακροπρόθεσμη πρόσβαση.

**Βασική Αρχικοποίηση και Ρύθμιση**  
Για να αρχίσετε να χρησιμοποιείτε το Aspose.Slides, αρχικοποιήστε το έργο σας δημιουργώντας ένα νέο αντικείμενο παρουσίασης:
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Οδηγός Υλοποίησης
Τώρα ας διασπάσουμε τη διαδικασία προσθήκης και προσαρμογής ενός διαγράμματος πίτας σε διαχειρίσιμα βήματα.

### Αρχικοποίηση Παρουσίασης και Διαφάνειας
Ξεκινήστε δημιουργώντας μια νέα παρουσίαση και αποκτώντας πρόσβαση στην πρώτη διαφάνεια. Αυτό είναι το καμβάς σας για τη δημιουργία διαγραμμάτων:
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
ISlide slide = presentation.getSlides().get_Item(0);
```

### Προσθήκη Διαγράμματος Πίτας στη Διαφάνεια
Εισάγετε ένα διάγραμμα πίτας στη συγκεκριμένη θέση με ένα προεπιλεγμένο σύνολο δεδομένων:
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Ορισμός Τίτλου Διαγράμματος
Προσαρμόστε το διάγραμμά σας ορίζοντας και κεντρώνοντας τον τίτλο:
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Διαμόρφωση Ετικετών Δεδομένων για τη Σειρά
Βεβαιωθείτε ότι οι ετικέτες δεδομένων εμφανίζουν τιμές για σαφήνεια:
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Προετοιμασία Φύλλου Δεδομένων Διαγράμματος
Διαμορφώστε το φύλλο δεδομένων του διαγράμματος καθαρίζοντας υπάρχουσες σειρές και κατηγορίες:
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Προσθήκη Κατηγοριών στο Διάγραμμα
Ορίστε τις κατηγορίες για το διάγραμμα πίτας:
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Προσθήκη Σειράς και Συμπλήρωση Σημείων Δεδομένων
Δημιουργήστε μια σειρά και συμπληρώστε την με σημεία δεδομένων – εδώ **προσθέτουμε σειρά διαγράμματος**:
```java
import com.aspose.slides.*;

// Add a new series and set its name.
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Προσαρμογή Χρωμάτων Σειράς και Περιγραμμάτων
Βελτιώστε την οπτική εμφάνιση ορίζοντας χρώματα και προσαρμόζοντας τα περιγράμματα – αυτό **προσαρμόζει τα χρώματα του διαγράμματος πίτας**:
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
Ρυθμίστε με ακρίβεια τις ετικέτες για κάθε σημείο δεδομένων:
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
Ολοκληρώστε το διάγραμμα πίτας **ορίζοντας γωνία περιστροφής** και αποθηκεύοντας το αρχείο:
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## Συχνά Προβλήματα και Λύσεις
| Πρόβλημα | Αιτία | Διόρθωση |
|----------|-------|----------|
| **Οι φέτες εμφανίζονται όλες με το ίδιο χρώμα** | `setColorVaried(true)` δεν κλήθηκε | Βεβαιωθείτε ότι έχετε ενεργοποιήσει διαφορετικά χρώματα στην ομάδα σειράς. |
| **Οι ετικέτες δεδομένων δεν εμφανίζονται** | Η σημαία `showValue` είναι απενεργοποιημένη | Κλήστε `setShowValue(true)` στη σχετική μορφή ετικέτας. |
| **Η περιστροφή δεν έχει αποτέλεσμα** | Χρήση παλαιότερης έκδοσης Aspose.Slides | Αναβαθμίστε στην έκδοση 25.4 ή νεότερη. |
| **Εξαίρεση άδειας κατά την εκτέλεση** | Απουσία ή μη έγκυρο αρχείο άδειας | Φορτώστε την άδειά σας με `License license = new License(); license.setLicense("Aspose.Slides.lic");` πριν δημιουργήσετε το `Presentation`. |

## Συχνές Ερωτήσεις

**Ε: Πώς αποκτώ άδεια Aspose.Slides για Java;**  
Α: Μπορείτε να ζητήσετε δωρεάν δοκιμή από τον ιστότοπο Aspose, στη συνέχεια να αγοράσετε μόνιμη άδεια. Φορτώστε την κατά το χρόνο εκτέλεσης όπως φαίνεται στον πίνακα Συχνών Προβλημάτων.

**Ε: Μπορώ να χρησιμοποιήσω αυτόν τον κώδικα με παλαιότερες εκδόσεις JDK;**  
Α: Το API απαιτεί JDK 16 ή υψηλότερη· οι παλαιότερες εκδόσεις δεν υποστηρίζονται.

**Ε: Είναι δυνατόν να εξάγω το διάγραμμα ως εικόνα αντί για PPTX;**  
Α: Ναι, καλέστε `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);` μετά την απόδοση.

**Ε: Τι γίνεται αν χρειαστεί να προσθέσω περισσότερες από μία σειρές σε διάγραμμα πίτας;**  
Α: Τα διαγράμματα πίτας συνήθως εμφανίζουν μία σειρά· για πολλαπλές σειρές χρησιμοποιήστε διάγραμμα δακτυλίου (doughnut) αντί αυτού.

**Ε: Λειτουργεί η βιβλιοθήκη σε διακομιστές Linux;**  
Α: Απόλυτα – το Aspose.Slides for Java είναι ανεξάρτητο από πλατφόρμα και τρέχει σε οποιοδήποτε OS με συμβατό JDK.

---

**Τελευταία ενημέρωση:** 2026-02-19  
**Δοκιμασμένο με:** Aspose.Slides for Java 25.4 (jdk16)  
**Συγγραφέας:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}