---
date: '2026-07-22'
description: Μάθετε το Aspose Slides Maven Dependency για να δημιουργήσετε ένα stacked
  column chart σε Java, να προσθέσετε data labels, να αλλάξετε τη μορφή αριθμού του
  vertical axis και να εξάγετε το αποτέλεσμα ως αρχείο PPTX.
keywords:
- aspose slides maven dependency
- add data labels to chart
- change vertical axis number format
- how to add percentage stacked chart
lastmod: '2026-07-22'
og_description: Το Aspose Slides Maven Dependency σας επιτρέπει να δημιουργήσετε ένα
  stacked column chart σε Java, να προσαρμόσετε data labels, να ρυθμίσετε τη μορφή
  του vertical axis και να αποθηκεύσετε ως PPTX – όλα με σύντομο, production‑ready
  κώδικα.
og_image_alt: 'Developer guide: Build a stacked column chart in Java using Aspose.Slides
  Maven dependency'
og_title: 'Aspose Slides Maven Dependency: Stacked Column Chart σε Java'
schemas:
- author: Aspose
  dateModified: '2026-07-22'
  description: Learn the Aspose Slides Maven Dependency to create a stacked column
    chart in Java, add data labels, change vertical axis number format, and export
    the result as a PPTX file.
  headline: 'Aspose Slides Maven Dependency: Stacked Column Chart in Java'
  type: TechArticle
- questions:
  - answer: Yes. The library supports JDK 8+; just use the appropriate classifier
      (e.g., `jdk16` for JDK 16 or later).
    question: Can I use this code with Java 11 or newer?
  - answer: Use `chart.getImage().save("chart.png", ImageFormat.Png);` after adding
      the chart to the slide.
    question: How do I export the chart as an image instead of a PPTX?
  - answer: Absolutely. Call `chart.getChartTitle().addTextFrameForOverriding("My
      Chart");` and configure `chart.getLegend()` as needed.
    question: Is it possible to add a legend to the stacked column chart?
  - answer: You can modify the `ChartDataWorkbook` cells and then call `chart.refresh();`
      to reflect changes.
    question: What if I need to update data after the presentation is generated?
  - answer: Yes. The library is pure Java and runs on any OS with a compatible JRE.
    question: Does Aspose.Slides work on Linux servers?
  type: FAQPage
tags:
- stacked column chart
- Aspose.Slides
- Java charting
- Maven dependency
- presentation generation
title: 'Aspose Slides Maven Dependency: Stacked Column Chart σε Java'
url: /el/java/charts-graphs/aspose-slides-java-stacked-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose Slides Maven Dependency: Διάγραμμα Στήλης Στοίβας σε Java

## Εισαγωγή

Αναβαθμίστε τις παρουσιάσεις σας ενσωματώνοντας διορατικές οπτικοποιήσεις δεδομένων με τη δύναμη του **Aspose.Slides for Java**. Σε αυτόν τον οδηγό θα **δημιουργήσετε ένα διάγραμμα στήλης στοίβας** που φαίνεται επαγγελματικό, είτε ετοιμάζετε επιχειρηματικές αναφορές είτε παρουσιάζετε στατιστικά έργου. Στο τέλος αυτού του tutorial θα μπορείτε να:

- Ρυθμίστε το περιβάλλον σας με την **Aspose Slides Maven dependency**
- Δημιουργήστε μια παρουσίαση από την αρχή
- **Προσθέστε ένα διάγραμμα στοίβασης ποσοστών** και προσαρμόστε την εμφάνισή του
- **Μορφοποιήστε τις ετικέτες δεδομένων του διαγράμματος** και **αλλάξτε τη μορφή αριθμού του κατακόρυφου άξονα**
- **Αποθηκεύστε την παρουσίαση ως PPTX** με μια μόνο γραμμή κώδικα

## Γρήγορες Απαντήσεις
- **Τι βιβλιοθήκη χρειάζομαι;** Προσθέστε την εξάρτηση Maven/Gradle `aspose-slides` (δείτε το “Aspose Slides Maven Dependency” παρακάτω).  
- **Ποιος τύπος διαγράμματος δημιουργεί στοίβαξη;** Χρησιμοποιήστε το `ChartType.PercentsStackedColumn` για ένα διάγραμμα στήλης στοίβασης ποσοστών.  
- **Πώς μπορώ να αλλάξω τη μορφή αριθμού του άξονα;** Καλέστε το `IAxis.setNumberFormat()` και ορίστε `setNumberFormatLinkedToSource(false)`.  
- **Μπορώ να προσαρμόσω τις ετικέτες δεδομένων;** Ναι – επαναλάβετε για κάθε `IChartDataPoint` και εκχωρήστε ένα προσαρμοσμένο `ITextFrame`.  
- **Πώς αποθηκεύω το αρχείο;** Καλείστε `presentation.save("output.pptx", SaveFormat.Pptx)`.

## Τι είναι ένα διάγραμμα στήλης στοίβας;
Ένα διάγραμμα στήλης στοίβας οπτικοποιεί πολλαπλές σειρές δεδομένων στοίβαγμένες κατακόρυφα σε κάθε στήλη κατηγορίας, με την παραλλαγή **percentage‑stacked** που κανονικοποιεί κάθε στήλη στο 100 % για εύκολη σύγκριση αναλογιών. Αυτό το μορφότυπο επιτρέπει στους θεατές να αξιολογούν γρήγορα πώς κάθε στοιχείο συμβάλλει στο σύνολο σε διαφορετικές κατηγορίες, καθιστώντας τις τάσεις και τα σχετικά μεγέθη άμεσα σαφή.

## Γιατί να χρησιμοποιήσετε Aspose.Slides for Java;
Το Aspose.Slides for Java σας επιτρέπει να δημιουργείτε, επεξεργάζεστε και μετατρέπετε αρχεία PowerPoint **χωρίς να χρειάζεστε το Microsoft Office** και υποστηρίζει **πάνω από 50 μορφές εξόδου** σε Windows, Linux και macOS. Η βιβλιοθήκη εκτελείται εξ ολοκλήρου σε JRE, επιτρέποντας αυτοματοποίηση στο διακομιστή και αναφορές υψηλής απόδοσης. Παρέχει επίσης λεπτομερή έλεγχο πάνω σε αντικείμενα διαγραμμάτων, διατάξεις διαφανειών και ιδιότητες εγγράφου, καθιστώντας την ιδανική για δημιουργία παρουσιάσεων επιχειρηματικού επιπέδου.

## Προαπαιτούμενα
- **Java Development Kit (JDK):** 8 ή νεότερο  
- **IDE:** IntelliJ IDEA, Eclipse ή οποιοσδήποτε επεξεργαστής συμβατός με Java  
- **Build Tool:** Maven ή Gradle (προαιρετικό αλλά συνιστάται)  
- **Βασικές γνώσεις Java** – πρέπει να είστε άνετοι με κλάσεις και μεθόδους  

## Ρύθμιση Aspose.Slides για Java
Για να ξεκινήσετε, προσθέστε τη βιβλιοθήκη Aspose.Slides στο έργο σας.

### Aspose Slides Maven Dependency
Προσθέστε το ακόλουθο στο `pom.xml` (αυτή είναι η **aspose slides maven dependency** που θα χρειαστείτε):

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Εναλλακτική Gradle
Αν προτιμάτε Gradle, συμπεριλάβετε αυτή τη γραμμή στο `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Άμεση Λήψη
Εναλλακτικά, κατεβάστε το πιο πρόσφατο JAR από [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Απόκτηση Άδειας
Μπορείτε να ξεκινήσετε με δωρεάν δοκιμή για να εξερευνήσετε τις δυνατότητες του Aspose.Slides. Για να αφαιρέσετε τους περιορισμούς αξιολόγησης, σκεφτείτε την απόκτηση προσωρινής ή αγορασμένης άδειας.

- **Δωρεάν Δοκιμή:** Πρόσβαση σε περιορισμένες λειτουργίες χωρίς άμεσο κόστος.  
- **Προσωρινή Άδεια:** Αίτηση μέσω [Aspose’s site](https://purchase.aspose.com/temporary-license/).  
- **Αγορά:** Επισκεφθείτε τη σελίδα αγοράς για πλήρη πρόσβαση.

### Βασική Αρχικοποίηση
`Presentation` είναι η βασική κλάση του Aspose.Slides που αντιπροσωπεύει ένα αρχείο PowerPoint στη μνήμη. Το παρακάτω ελάχιστο απόσπασμα δείχνει πώς να δημιουργήσετε ένα αντικείμενο `Presentation`:

```java
import com.aspose.slides.Presentation;

public class InitializeAspose {
    public static void main(String[] args) {
        // Create an instance of Presentation class
        Presentation presentation = new Presentation();
        
        // Perform operations on the presentation object
        System.out.println("Aspose.Slides initialized successfully.");
    }
}
```

## Οδηγός Υλοποίησης

### Δημιουργία Παρουσίασης και Προσθήκη Διαφάνειας
**Επισκόπηση:**  
Πρώτα, θα δημιουργήσουμε μια κενή παρουσίαση και θα επαληθεύσουμε ότι υπάρχει μια διαφάνεια.

#### Βήμα 1: Αρχικοποίηση Αντικειμένου Presentation
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

public class CreatePresentation {
    public static void main(String[] args) throws Exception {
        // Create a new presentation instance
        Presentation presentation = new Presentation();
        
        // Reference to the first slide (auto-created)
        System.out.println("Slide count: " + presentation.getSlides().size());
    }
}
```

#### Βήμα 2: Αποθήκευση της Παρουσίασης
```
// Save the presentation to a file
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### Προσθήκη Διάγραμμα Στοίβας Ποσοστών σε Διαφάνεια
**Επισκόπηση:**  
Τώρα θα τοποθετήσουμε ένα **διάγραμμα στοίβας ποσοστών** στην πρώτη διαφάνεια.

`ChartType.PercentsStackedColumn` καθορίζει τύπο διαγράμματος στήλης στοίβας ποσοστών.

#### Βήμα 1: Αρχικοποίηση και Πρόσβαση στη Διαφάνεια
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.ChartType;

public class AddChartToSlide {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        // Proceed to add chart in the next step
    }
}
```

#### Βήμα 2: Προσθήκη Διαγράμματος στη Διαφάνεια
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### Προσαρμογή Μορφής Αριθμού Άξονα Διαγράμματος
**Επισκόπηση:**  
Για καλύτερη αναγνωσιμότητα, θα **αλλάξουμε τη μορφή του κατακόρυφου άξονα** ώστε να εμφανίζει ποσοστά.

`IAxis` είναι η διεπαφή που αντιπροσωπεύει έναν άξονα διαγράμματος, επιτρέποντας ρυθμίσεις μορφής και κλίμακας.

#### Βήμα 1: Προσθήκη και Πρόσβαση στο Διάγραμμα
```java
public class CustomizeChartAxis {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);
    }
}
```

#### Βήμα 2: Ορισμός Προσαρμοσμένης Μορφής Αριθμού
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### Προσθήκη Σειρών και Σημείων Δεδομένων στο Διάγραμμα
**Επισκόπηση:**  
Θα γεμίσουμε το διάγραμμα με δείγμα σειρών δεδομένων.

#### Βήμα 1: Αρχικοποίηση Παρουσίασης και Διαγράμματος
```java
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ChartDataWorkbook;

public class AddSeriesToChart {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Βήμα 2: Προσθήκη Σειράς Δεδομένων
```java
// Clear existing series and add new ones
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// Add more data points as needed
```

### Μορφοποίηση Χρώματος Γέμισης Σειράς
**Επισκόπηση:**  
Δώστε σε κάθε σειρά ένα ξεχωριστό χρώμα ώστε το διάγραμμα να είναι πιο ευανάγνωστο.

#### Βήμα 1: Αρχικοποίηση και Πρόσβαση στο Διάγραμμα
```java
import java.awt.Color;
import com.aspose.slides.FillType;

public class FormatSeriesFillColor {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
    }
}
```

#### Βήμα 2: Ορισμός Χρωμάτων Γέμισης
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Repeat for other series with different colors
```

### Μορφοποίηση Ετικετών Δεδομένων
**Επισκόπηση:**  
Τώρα θα **μορφοποιήσουμε τις ετικέτες δεδομένων του διαγράμματος** ώστε να εμφανίζουν προσαρμοσμένο κείμενο.

`IChartDataPoint` αντιπροσωπεύει ένα μεμονωμένο σημείο δεδομένων μέσα σε μια σειρά διαγράμματος, και το `ITextFrame` περιέχει το κείμενο της ετικέτας.

#### Βήμα 1: Πρόσβαση στις Σειρές Διαγράμματος και στα Σημεία Δεδομένων
```java
public class FormatDataLabels {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Βήμα 2: Προσαρμογή Ετικετών Δεδομένων
```java
import com.aspose.slides.ITextFrame;
import com.aspose.slides.IChartDataPoint;

for (IChartSeries series : chart.getChartData().getSeries()) {
    for (IChartDataPoint point : series.getDataPoints()) {
        ITextFrame textFrame = point.getLabel().getTextFrameForOverriding();
        if (textFrame != null) {
            textFrame.setText("Custom Label: " + point.getValue());
        }
    }
}
```

## Συχνά Προβλήματα και Λύσεις
- **Το διάγραμμα εμφανίζεται κενό:** Βεβαιωθείτε ότι έχετε προσθέσει τουλάχιστον μία σειρά δεδομένων και σημείο δεδομένων πριν την αποθήκευση.  
- **Οι αριθμοί του άξονα δεν εμφανίζουν ποσοστά:** Θυμηθείτε να ορίσετε `verticalAxis.setNumberFormatLinkedToSource(false)`· διαφορετικά η προσαρμοσμένη μορφή αγνοείται.  
- **Μήνυμα αξιολόγησης άδειας:** Εφαρμόστε ένα έγκυρο αρχείο άδειας πριν δημιουργήσετε το αντικείμενο `Presentation` για να καταστέλετε τη σημαία αξιολόγησης.

## Συχνές Ερωτήσεις

**Q: Μπορώ να χρησιμοποιήσω αυτόν τον κώδικα με Java 11 ή νεότερο;**  
A: Ναι. Η βιβλιοθήκη υποστηρίζει JDK 8+· απλώς χρησιμοποιήστε τον κατάλληλο classifier (π.χ., `jdk16` για JDK 16 ή νεότερο).

**Q: Πώς εξάγω το διάγραμμα ως εικόνα αντί για PPTX;**  
A: Χρησιμοποιήστε `chart.getImage().save("chart.png", ImageFormat.Png);` μετά την προσθήκη του διαγράμματος στη διαφάνεια.

**Q: Είναι δυνατόν να προσθέσω υπόμνημα στο διάγραμμα στήλης στοίβας;**  
A: Απόλυτα. Καλέστε `chart.getChartTitle().addTextFrameForOverriding("My Chart");` και διαμορφώστε το `chart.getLegend()` όπως χρειάζεται.

**Q: Τι γίνεται αν χρειαστεί να ενημερώσω τα δεδομένα μετά τη δημιουργία της παρουσίασης;**  
A: Μπορείτε να τροποποιήσετε τα κελιά του `ChartDataWorkbook` και στη συνέχεια να καλέσετε `chart.refresh();` για να αντικατοπτριστούν οι αλλαγές.

**Q: Λειτουργεί το Aspose.Slides σε διακομιστές Linux;**  
A: Ναι. Η βιβλιοθήκη είναι καθαρά Java και τρέχει σε οποιοδήποτε OS με συμβατό JRE.

## Συμπέρασμα
Ακολουθώντας αυτόν τον οδηγό έχετε μάθει πώς να **δημιουργήσετε ένα διάγραμμα στήλης στοίβας** σε Java χρησιμοποιώντας την **Aspose Slides Maven dependency**, από τη ρύθμιση του περιβάλλοντος έως τη λεπτομερή οπτική διαμόρφωση. Πειραματιστείτε με διαφορετικά σύνολα δεδομένων, χρώματα και μορφές ετικετών για να κάνετε τις αναφορές σας πραγματικά εντυπωσιακές.

---

**Τελευταία Ενημέρωση:** 2026-07-22  
**Δοκιμάστηκε Με:** Aspose.Slides 25.4 (jdk16 classifier)  
**Συγγραφέας:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Σχετικά Μαθήματα

- [Πώς να δημιουργήσετε συγκεντρωτικό διάγραμμα στήλης σε Java με Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-clustered-column-charts/)
- [Πώς να ορίσετε μορφές αριθμών σε σημεία δεδομένων διαγράμματος χρησιμοποιώντας Aspose.Slides for Java](/slides/java/charts-graphs/set-number-format-chart-data-points-aspose-slides-java/)
- [Πώς να προσθέσετε και να διαμορφώσετε διαγράμματα σε παρουσιάσεις χρησιμοποιώντας Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}