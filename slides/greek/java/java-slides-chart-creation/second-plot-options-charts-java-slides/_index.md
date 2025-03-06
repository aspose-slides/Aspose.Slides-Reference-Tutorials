---
title: Επιλογές δεύτερης γραφικής παράστασης για γραφήματα σε διαφάνειες Java
linktitle: Επιλογές δεύτερης γραφικής παράστασης για γραφήματα σε διαφάνειες Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Μάθετε πώς να προσαρμόζετε γραφήματα σε Java Slides χρησιμοποιώντας το Aspose.Slides για Java. Εξερευνήστε τις επιλογές δεύτερης πλοκής και βελτιώστε τις παρουσιάσεις σας.
weight: 12
url: /el/java/chart-creation/second-plot-options-charts-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Εισαγωγή στις Επιλογές δεύτερης γραφικής παράστασης για γραφήματα σε διαφάνειες Java

Σε αυτό το σεμινάριο, θα διερευνήσουμε πώς να προσθέσετε επιλογές δεύτερης γραφικής παράστασης σε γραφήματα χρησιμοποιώντας το Aspose.Slides για Java. Οι επιλογές δεύτερης πλοκής σάς επιτρέπουν να προσαρμόσετε την εμφάνιση και τη συμπεριφορά των γραφημάτων, ιδιαίτερα σε σενάρια όπως τα γραφήματα Pie of Pie. Θα παρέχουμε οδηγίες βήμα προς βήμα και παραδείγματα πηγαίου κώδικα για να το πετύχουμε αυτό. 

## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε εγκαταστήσει και ρυθμίσει το Aspose.Slides για Java στο έργο σας Java.

## Βήμα 1: Δημιουργήστε μια παρουσίαση
Ας ξεκινήσουμε δημιουργώντας μια νέα παρουσίαση:

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
// Δημιουργήστε μια παρουσία της κλάσης παρουσίασης
Presentation presentation = new Presentation();
```

## Βήμα 2: Προσθέστε ένα γράφημα σε μια διαφάνεια
Στη συνέχεια, θα προσθέσουμε ένα γράφημα σε μια διαφάνεια. Σε αυτό το παράδειγμα, θα δημιουργήσουμε ένα γράφημα Pie of Pie:

```java
// Προσθήκη γραφήματος στη διαφάνεια
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
```

## Βήμα 3: Προσαρμόστε τις ιδιότητες γραφήματος
Τώρα, ας ορίσουμε διαφορετικές ιδιότητες για το γράφημα, συμπεριλαμβανομένων των επιλογών δεύτερης γραφικής παράστασης:

```java
// Εμφάνιση ετικετών δεδομένων για την πρώτη σειρά
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Ορίστε το μέγεθος της δεύτερης πίτας (σε ποσοστό)
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);

// Χωρίζουμε την πίτα κατά ποσοστό
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);

// Ρυθμίστε τη θέση του διαχωρισμού
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
```

## Βήμα 4: Αποθηκεύστε την Παρουσίαση
Τέλος, αποθηκεύστε την παρουσίαση με τις επιλογές του γραφήματος και της δεύτερης πλοκής:

```java
// Γράψτε την παρουσίαση στο δίσκο
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## Ολοκληρώστε τον πηγαίο κώδικα για τις επιλογές δεύτερης πλοκής

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
// Δημιουργήστε μια παρουσία της κλάσης παρουσίασης
Presentation presentation = new Presentation();
// Προσθήκη γραφήματος στη διαφάνεια
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
// Ορίστε διαφορετικές ιδιότητες
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
// Γράψτε την παρουσίαση στο δίσκο
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## συμπέρασμα

Σε αυτό το σεμινάριο, μάθαμε πώς να προσθέτουμε επιλογές δεύτερης γραφικής παράστασης σε γραφήματα σε διαφάνειες Java χρησιμοποιώντας το Aspose.Slides για Java. Μπορείτε να προσαρμόσετε διάφορες ιδιότητες για να βελτιώσετε την εμφάνιση και τη λειτουργικότητα των γραφημάτων σας, κάνοντας τις παρουσιάσεις σας πιο ενημερωτικές και οπτικά ελκυστικές.

## Συχνές ερωτήσεις

### Πώς μπορώ να αλλάξω το μέγεθος της δεύτερης πίτας σε ένα γράφημα Pie of Pie;

Για να αλλάξετε το μέγεθος της δεύτερης πίτας σε ένα γράφημα Pie of Pie, χρησιμοποιήστε το`setSecondPieSize` μέθοδο όπως φαίνεται στο παραπάνω παράδειγμα κώδικα. Προσαρμόστε την τιμή για να καθορίσετε το μέγεθος σε ποσοστό.

###  Τι κάνει`PieSplitBy` control in a Pie of Pie chart?

 ο`PieSplitBy` Η ιδιότητα ελέγχει τον τρόπο με τον οποίο χωρίζεται το γράφημα πίτας. Μπορείτε να το ρυθμίσετε σε οποιοδήποτε από τα δύο`PieSplitType.ByPercentage` ή`PieSplitType.ByValue` για να χωρίσετε το γράφημα κατά ποσοστό ή κατά μια συγκεκριμένη τιμή, αντίστοιχα.

### Πώς ορίζω τη θέση του διαχωρισμού σε ένα γράφημα Pie of Pie;

 Μπορείτε να ορίσετε τη θέση του διαχωρισμού σε ένα γράφημα Pie of Pie χρησιμοποιώντας το`setPieSplitPosition` μέθοδος. Προσαρμόστε την τιμή για να καθορίσετε την επιθυμητή θέση.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
