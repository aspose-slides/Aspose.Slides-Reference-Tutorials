---
date: '2026-03-20'
description: Μάθετε πώς να προσθέτετε διαγράμματα σε παρουσιάσεις Java χρησιμοποιώντας
  το Aspose.Slides και να δημιουργείτε αρχεία διαγραμμάτων παρουσίασης γρήγορα.
keywords:
- Java Presentations with Aspose.Slides
- Create Charts in Java
- Configure Presentation Data
title: Πώς να προσθέσετε διάγραμμα σε παρουσιάσεις Java με το Aspose.Slides
url: /el/java/charts-graphs/create-java-presentations-charts-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Πώς να Προσθέσετε Chart σε Παρουσίαση Χρησιμοποιώντας το Aspose.Slides για Java

## Εισαγωγή

Η δημιουργία δυναμικών παρουσιάσεων που μεταδίδουν αποτελεσματικά δεδομένα είναι απαραίτητη στο σημερινό γρήγορα εξελισσόμενο επιχειρηματικό περιβάλλον. Είτε ετοιμάζετε μια οικονομική αναφορά, ένα marketing deck, είτε μια ενημέρωση κατάστασης έργου, **γνωρίζοντας πώς να προσθέσετε chart** στις διαφάνειές σας μπορεί να βελτιώσει δραστικά την αφοσίωση του κοινού. Σε αυτό το tutorial θα μάθετε βήμα‑βήμα πώς να προσθέσετε ένα 3D stacked column chart, να διαμορφώσετε τα δεδομένα του και να αποθηκεύσετε το τελικό αρχείο—όλα με το Aspose.Slides για Java.

### Γρήγορες Απαντήσεις
- **Ποια είναι η κύρια βιβλιοθήκη;** Aspose.Slides for Java  
- **Ποιος τύπος γραφήματος παρουσιάζεται;** 3D Stacked Column  
- **Μπορώ να δημιουργήσω αρχεία γραφήματος παρουσίασης προγραμματιστικά;** Ναι, χρησιμοποιώντας τις μεθόδους API που φαίνονται παρακάτω  
- **Ποια έκδοση Java συνιστάται;** JDK 16 ή νεότερη  
- **Χρειάζομαι άδεια για παραγωγή;** Απαιτείται έγκυρη άδεια Aspose.Slides για εμπορική χρήση  

## Τι είναι το “how to add chart” στο Aspose.Slides;

Το Aspose.Slides για Java παρέχει ένα πλούσιο σύνολο αντικειμένων που σας επιτρέπουν να δημιουργείτε, να επεξεργάζεστε και να εξάγετε αρχεία PowerPoint χωρίς το Microsoft Office. Η προσθήκη ενός chart είναι τόσο απλή όσο η δημιουργία ενός αντικειμένου `Presentation`, η εισαγωγή ενός chart shape και η τροφοδοσία του με δεδομένα μέσω του ενσωματωμένου workbook.

## Γιατί να προσθέσετε chart σε παρουσιάσεις Java;

- **Οπτική επίδραση:** Τα charts μετατρέπουν ακατέργαστους αριθμούς σε άμεσα κατανοητές εικόνες.  
- **Αυτοματοποίηση:** Δημιουργήστε αναφορές εν κινήσει—ιδανικό για προγραμματισμένα email digests ή dashboards.  
- **Συνέπεια:** Χρησιμοποιήστε το ίδιο στυλ και branding σε όλες τις παραγόμενες παρουσιάσεις.  
- **Φορητότητα:** Εξαγωγή σε PPTX, PDF ή εικόνες με μία μόνο κλήση μεθόδου.

## Προαπαιτούμενα

- **Βιβλιοθήκες και Εξαρτήσεις:** Πρέπει να είναι εγκατεστημένο το Aspose.Slides για Java.  
- **Ρύθμιση Περιβάλλοντος:** Εργαστείτε σε περιβάλλον Java (συνιστάται JDK 16 ή νεότερο).  
- **Βάση Γνώσεων:** Η εξοικείωση με βασικές έννοιες προγραμματισμού Java θα είναι επωφελής.

## Ρύθμιση του Aspose.Slides για Java

### Εγκατάσταση

Για να ενσωματώσετε το Aspose.Slides στο έργο σας, ακολουθήστε μία από τις παρακάτω επιλογές.

**Maven**

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direct Download**: Εναλλακτικά, κατεβάστε την τελευταία έκδοση από [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Απόκτηση Άδειας
- **Δωρεάν Δοκιμή:** Ξεκινήστε με μια δωρεάν δοκιμή για να εξερευνήσετε τις δυνατότητες.  
- **Προσωρινή Άδεια:** Αποκτήστε μια προσωρινή άδεια για εκτεταμένη δοκιμή.  
- **Αγορά:** Αποκτήστε πλήρη άδεια για εμπορική χρήση.

Μόλις εγκατασταθεί, μπορείτε να δημιουργήσετε μια παρουσίαση με την κλάση `Presentation`, η οποία λειτουργεί ως σημείο εισόδου για όλες τις λειτουργίες που σχετίζονται με charts.

## Οδηγός Υλοποίησης

### Πώς να προσθέσετε chart σε παρουσίαση με 3D stacked column

#### Επισκόπηση
Η δημιουργία μιας παρουσίασης από το μηδέν είναι απλή με το Aspose.Slides. Σε αυτήν την ενότητα, θα προσθέσουμε ένα 3D stacked column chart στην πρώτη διαφάνεια της παρουσίασής μας.

**Steps:**

1. **Αρχικοποίηση αντικειμένου Presentation**

   ```java
   import com.aspose.slides.*;

   public class ChartPresentation {
       public static void main(String[] args) {
           // Initialize a new Presentation object
           Presentation presentation = new Presentation();
           
           // Access the first slide in the presentation
           ISlide slide = presentation.getSlides().get_Item(0);
           
           // Add a 3D stacked column chart to the slide at position (0,0)
           IChart chart = slide.getShapes().addChart(
               ChartType.StackedColumn3D, 0, 0, 500, 500
           );
           
           configureChartData(chart);
           setRotation3D(chart);
           populateSeriesData(chart);
           setSeriesOverlap(chart);
           savePresentation(presentation);
       }
   }
   ```

2. **Επεξήγηση Παραμέτρων**  
   - `ChartType.StackedColumn3D`: Καθορίζει τον τύπο του γραφήματος.  
   - Θέση και μέγεθος `(0, 0, 500, 500)`: Καθορίζει πού εμφανίζεται το chart στη διαφάνεια.

### Διαμόρφωση Δεδομένων Γραφήματος

#### Επισκόπηση
Για να είναι το chart σας ουσιαστικό, διαμορφώστε τις σειρές δεδομένων και τις κατηγορίες. Αυτή η ενότητα δείχνει πώς να προσθέσετε συγκεκριμένα σημεία δεδομένων στο chart σας.

**Steps:**

1. **Πρόσβαση στο Data Workbook του Chart**

   ```java
   public static void configureChartData(IChart chart) {
       // Set the index of the worksheet that contains chart data
       int defaultWorksheetIndex = 0;
       
       // Access the chart's data workbook
       IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
       
       // Add two series with names
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), 
           chart.getType()
       );
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), 
           chart.getType()
       );
       
       // Add three categories
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
   }
   ```

### Ορισμός Ιδιοτήτων Rotation3D για το Chart

#### Επισκόπηση
Βελτιώστε την οπτική ελκυστικότητα του chart σας με ιδιότητες 3D περιστροφής. Αυτή η προσαρμογή σας επιτρέπει να ρυθμίσετε την προοπτική και το βάθος.

**Steps:**

1. **Διαμόρφωση 3D Περιστροφών**

   ```java
   public static void setRotation3D(IChart chart) {
       // Enable right angle axes and configure rotations in X, Y directions, and depth percent
       chart.getRotation3D().setRightAngleAxes(true);
       chart.getRotation3D().setRotationX((byte) 40);
       chart.getRotation3D().setRotationY(270);
       chart.getRotation3D().setDepthPercents(150);
   }
   ```

2. **Επεξήγηση Παραμέτρων**  
   - `setRightAngleAxes(true)`: Διασφαλίζει ότι οι άξονες είναι κάθετοι.  
   - Τιμές περιστροφής: Ρυθμίστε τη γωνία και το βάθος της 3D προβολής.

### Συμπλήρωση Δεδομένων Σειράς στο Chart

#### Επισκόπηση
Η συμπλήρωση του chart σας με σημεία δεδομένων είναι κρίσιμη για την ανάλυση. Εδώ, θα προσθέσουμε συγκεκριμένες τιμές σε μια σειρά του chart.

**Steps:**

1. **Προσθήκη Σημείων Δεδομένων**

   ```java
   public static void populateSeriesData(IChart chart) {
       // Access the second chart series
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       // Add data points for bar series with specified values
       int defaultWorksheetIndex = 0;
       IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
       
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
   }
   ```

### Προσαρμογή Επικάλυψης Σειράς στο Chart

#### Επισκόπηση
Η λεπτομερής ρύθμιση της εμφάνισης του chart μπορεί να βελτιώσει την αναγνωσιμότητα. Αυτή η ενότητα καλύπτει πώς να ρυθμίσετε την ιδιότητα επικάλυψης για καλύτερη οπτικοποίηση των δεδομένων.

**Steps:**

1. **Ορισμός Επικάλυψης Σειράς**

   ```java
   public static void setSeriesOverlap(IChart chart) {
       // Get the second series from the chart and set its overlap to 100
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       series.getParentSeriesGroup().setOverlap((byte) 100);
   }
   ```

### Αποθήκευση Παρουσίασης

#### Επισκόπηση
Μόλις η παρουσίασή σας είναι διαμορφωμένη, αποθηκεύστε την στο δίσκο στη μορφή που επιθυμείτε. Αυτό το βήμα εξασφαλίζει ότι όλες οι αλλαγές διατηρούνται.

**Steps:**

1. **Αποθήκευση της Παρουσίασης**

   ```java
   public static void savePresentation(Presentation presentation) {
       // Save the modified presentation to a file
       String outputFilePath = "output_presentation.pptx";
       presentation.save(outputFilePath, SaveFormat.Pptx);
   }
   ```

## Συνηθισμένα Προβλήματα και Λύσεις

| Πρόβλημα | Αιτία | Λύση |
|----------|-------|------|
| **Chart appears flat** | 3D rotation not set | Call `setRotation3D` with appropriate X/Y values. |
| **Data not showing** | Workbook cells not linked | Ensure `fact.getCell` references correct row/column indices. |
| **File not saved** | Incorrect path or missing permissions | Verify `outputFilePath` is writable and folder exists. |

## Συχνές Ερωτήσεις

**Q: Μπορώ να δημιουργήσω αρχεία γραφήματος παρουσίασης σε μορφές διαφορετικές από PPTX;**  
A: Ναι, το Aspose.Slides υποστηρίζει PDF, ODP και μορφές εικόνας μέσω του enum `SaveFormat`.

**Q: Χρειάζομαι άδεια για να εκτελέσω τον κώδικα σε ανάπτυξη;**  
A: Μια προσωρινή ή δοκιμαστική άδεια λειτουργεί για ανάπτυξη, αλλά απαιτείται πλήρης άδεια για παραγωγικές εγκαταστάσεις.

**Q: Είναι δυνατόν να προσθέσω πολλαπλά charts στην ίδια διαφάνεια;**  
A: Απόλυτα. Καλέστε `slide.getShapes().addChart` πολλές φορές με διαφορετικές θέσεις ή μεγέθη.

**Q: Πώς μπορώ να αλλάξω την παλέτα χρωμάτων του chart;**  
A: Χρησιμοποιήστε το `chart.getChartData().getSeries().get_Item(i).getFormat().getFill().setFillType(FillType.Solid)` και ορίστε ένα `SolidFillColor`.

**Q: Μπορώ να συνδέσω το chart με εξωτερική πηγή δεδομένων όπως μια βάση δεδομένων;**  
A: Ναι. Ανακτήστε δεδομένα με JDBC, στη συνέχεια συμπληρώστε τα κελιά του workbook προγραμματιστικά πριν αποθηκεύσετε.

## Συμπέρασμα

Τώρα έχετε μάθει **πώς να προσθέσετε chart** σε μια παρουσίαση Java, να διαμορφώσετε τα δεδομένα του, να προσαρμόσετε την 3D περιστροφή, να ρυθμίσετε την επικάλυψη σειρών και να αποθηκεύσετε το τελικό αρχείο. Αυτή η γνώση σας επιτρέπει να αυτοματοποιήσετε τη δημιουργία αναφορών, να δημιουργήσετε συνεπές branding και να παραδώσετε παρουσιάσεις βασισμένες σε δεδομένα χωρίς χειροκίνητη προσπάθεια. Για πιο προχωρημένη προσαρμογή—όπως το στυλ των υπομνημάτων, των αξόνων ή την εφαρμογή θεμάτων—εξερευνήστε τις πλήρεις δυνατότητες στην επίσημη τεκμηρίωση.

Για πιο προχωρημένα χαρακτηριστικά και επιλογές προσαρμογής, ανατρέξτε στην [Aspose.Slides for Java documentation](https://docs.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Τελευταία Ενημέρωση:** 2026-03-20  
**Δοκιμή Με:** Aspose.Slides for Java 25.4 (JDK 16)  
**Συγγραφέας:** Aspose