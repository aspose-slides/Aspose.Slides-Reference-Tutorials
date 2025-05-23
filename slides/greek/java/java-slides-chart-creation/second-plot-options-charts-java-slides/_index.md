---
"description": "Μάθετε πώς να προσαρμόζετε γραφήματα σε Java Slides χρησιμοποιώντας το Aspose.Slides για Java. Εξερευνήστε τις επιλογές δεύτερου γραφήματος και βελτιώστε τις παρουσιάσεις σας."
"linktitle": "Επιλογές Δεύτερου Σχεδίου για Γραφήματα σε Διαφάνειες Java"
"second_title": "Aspose.Slides API επεξεργασίας Java PowerPoint"
"title": "Επιλογές Δεύτερου Σχεδίου για Γραφήματα σε Διαφάνειες Java"
"url": "/el/java/chart-creation/second-plot-options-charts-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Επιλογές Δεύτερου Σχεδίου για Γραφήματα σε Διαφάνειες Java


## Εισαγωγή στις επιλογές δεύτερου γραφήματος για γραφήματα σε διαφάνειες Java

Σε αυτό το σεμινάριο, θα εξερευνήσουμε πώς να προσθέσετε επιλογές δεύτερου γραφήματος σε γραφήματα χρησιμοποιώντας το Aspose.Slides για Java. Οι επιλογές δεύτερου γραφήματος σάς επιτρέπουν να προσαρμόσετε την εμφάνιση και τη συμπεριφορά των γραφημάτων, ιδιαίτερα σε σενάρια όπως τα γραφήματα πίτας. Θα παρέχουμε οδηγίες βήμα προς βήμα και παραδείγματα πηγαίου κώδικα για να το πετύχουμε αυτό. 

## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε εγκαταστήσει και ρυθμίσει το Aspose.Slides για Java στο έργο σας Java.

## Βήμα 1: Δημιουργήστε μια παρουσίαση
Ας ξεκινήσουμε δημιουργώντας μια νέα παρουσίαση:

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
// Δημιουργήστε μια παρουσία της κλάσης Presentation
Presentation presentation = new Presentation();
```

## Βήμα 2: Προσθήκη γραφήματος σε διαφάνεια
Στη συνέχεια, θα προσθέσουμε ένα γράφημα σε μια διαφάνεια. Σε αυτό το παράδειγμα, θα δημιουργήσουμε ένα γράφημα πίτας:

```java
// Προσθήκη γραφήματος σε διαφάνεια
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
```

## Βήμα 3: Προσαρμογή ιδιοτήτων γραφήματος
Τώρα, ας ορίσουμε διαφορετικές ιδιότητες για το γράφημα, συμπεριλαμβανομένων των επιλογών του δεύτερου γραφήματος:

```java
// Εμφάνιση ετικετών δεδομένων για την πρώτη σειρά
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Ορίστε το μέγεθος της δεύτερης πίτας (σε ποσοστό)
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);

// Χωρίστε την πίτα με βάση το ποσοστό
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);

// Ορίστε τη θέση του διαχωρισμού
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
```

## Βήμα 4: Αποθήκευση της παρουσίασης
Τέλος, αποθηκεύστε την παρουσίαση με τις επιλογές γραφήματος και δεύτερου γραφήματος:

```java
// Εγγραφή παρουσίασης σε δίσκο
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## Πλήρης πηγαίος κώδικας για επιλογές δεύτερου γραφήματος

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
// Δημιουργήστε μια παρουσία της κλάσης Presentation
Presentation presentation = new Presentation();
// Προσθήκη γραφήματος σε διαφάνεια
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
// Ορισμός διαφορετικών ιδιοτήτων
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
// Εγγραφή παρουσίασης σε δίσκο
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## Σύναψη

Σε αυτό το σεμινάριο, μάθαμε πώς να προσθέτουμε επιλογές δεύτερου γραφήματος σε γραφήματα σε Java Slides χρησιμοποιώντας το Aspose.Slides για Java. Μπορείτε να προσαρμόσετε διάφορες ιδιότητες για να βελτιώσετε την εμφάνιση και τη λειτουργικότητα των γραφημάτων σας, κάνοντας τις παρουσιάσεις σας πιο ενημερωτικές και οπτικά ελκυστικές.

## Συχνές ερωτήσεις

### Πώς μπορώ να αλλάξω το μέγεθος της δεύτερης πίτας σε ένα γράφημα πίτας πίτας;

Για να αλλάξετε το μέγεθος της δεύτερης πίτας σε ένα γράφημα πίτας, χρησιμοποιήστε το `setSecondPieSize` μέθοδος όπως φαίνεται στο παραπάνω παράδειγμα κώδικα. Προσαρμόστε την τιμή για να καθορίσετε το μέγεθος σε ποσοστό.

### Τι κάνει `PieSplitBy` έλεγχος σε ένα γράφημα πίτας πίτας;

Ο `PieSplitBy` Η ιδιότητα ελέγχει τον τρόπο διαίρεσης του κυκλικού γραφήματος. Μπορείτε να την ορίσετε είτε σε `PieSplitType.ByPercentage` ή `PieSplitType.ByValue` για να διαιρέσετε το γράφημα κατά ποσοστό ή κατά μια συγκεκριμένη τιμή, αντίστοιχα.

### Πώς μπορώ να ορίσω τη θέση του διαχωρισμού σε ένα γράφημα πίτας πίτας;

Μπορείτε να ορίσετε τη θέση του διαχωρισμού σε ένα γράφημα πίτας χρησιμοποιώντας το `setPieSplitPosition` μέθοδος. Προσαρμόστε την τιμή για να καθορίσετε την επιθυμητή θέση.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}