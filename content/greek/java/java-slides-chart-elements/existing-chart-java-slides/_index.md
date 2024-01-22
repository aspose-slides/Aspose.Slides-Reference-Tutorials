---
title: Υπάρχον γράφημα σε διαφάνειες Java
linktitle: Υπάρχον γράφημα σε διαφάνειες Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Βελτιώστε τις παρουσιάσεις σας στο PowerPoint με το Aspose.Slides για Java. Μάθετε να τροποποιείτε τα υπάρχοντα γραφήματα μέσω προγραμματισμού. Οδηγός βήμα προς βήμα με πηγαίο κώδικα για προσαρμογή γραφήματος.
type: docs
weight: 12
url: /el/java/chart-elements/existing-chart-java-slides/
---

## Εισαγωγή στο υπάρχον γράφημα σε διαφάνειες Java χρησιμοποιώντας το Aspose.Slides για Java

Σε αυτό το σεμινάριο, θα δείξουμε πώς να τροποποιήσετε ένα υπάρχον γράφημα σε μια παρουσίαση του PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Θα ακολουθήσουμε τα βήματα για να αλλάξουμε δεδομένα γραφήματος, ονόματα κατηγοριών, ονόματα σειρών και να προσθέσουμε μια νέα σειρά στο γράφημα. Βεβαιωθείτε ότι έχετε ρυθμίσει το Aspose.Slides για Java στο έργο σας.

## Προαπαιτούμενα

Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

1. Η βιβλιοθήκη Aspose.Slides for Java περιλαμβάνονται στο έργο σας.
2. Μια υπάρχουσα παρουσίαση PowerPoint με ένα γράφημα που θέλετε να τροποποιήσετε.
3. Ρύθμιση περιβάλλοντος ανάπτυξης Java.

## Βήμα 1: Φορτώστε την παρουσίαση

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";

// Κλάση Instantiation Presentation που αντιπροσωπεύει το αρχείο PPTX
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
```

## Βήμα 2: Πρόσβαση στη διαφάνεια και στο γράφημα

```java
// Πρόσβαση στην πρώτη διαφάνεια
ISlide sld = pres.getSlides().get_Item(0);

// Πρόσβαση στο γράφημα στη διαφάνεια
IChart chart = (IChart) sld.getShapes().get_Item(0);
```

## Βήμα 3: Αλλαγή δεδομένων γραφήματος και ονομάτων κατηγοριών

```java
// Ρύθμιση του ευρετηρίου του φύλλου δεδομένων γραφήματος
int defaultWorksheetIndex = 0;

//Λήψη του φύλλου εργασίας δεδομένων γραφήματος
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Αλλαγή ονομάτων κατηγοριών γραφημάτων
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
```

## Βήμα 4: Ενημερώστε την πρώτη σειρά γραφημάτων

```java
// Πάρτε την πρώτη σειρά γραφημάτων
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Ενημέρωση ονόματος σειράς
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");

// Ενημέρωση δεδομένων σειράς
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
```

## Βήμα 5: Ενημερώστε τη δεύτερη σειρά γραφημάτων

```java
// Πάρτε τη δεύτερη σειρά γραφημάτων
series = chart.getChartData().getSeries().get_Item(1);

// Ενημέρωση ονόματος σειράς
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");

// Ενημέρωση δεδομένων σειράς
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
```

## Βήμα 6: Προσθέστε μια νέα σειρά στο γράφημα

```java
// Προσθήκη νέας σειράς
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());

// Πάρτε την τρίτη σειρά γραφημάτων
series = chart.getChartData().getSeries().get_Item(2);

// Συμπλήρωση δεδομένων σειράς
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
```

## Βήμα 7: Αλλάξτε τον τύπο γραφήματος

```java
//Αλλάξτε τον τύπο γραφήματος σε Clustered Cylinder
chart.setType(ChartType.ClusteredCylinder);
```

## Βήμα 8: Αποθηκεύστε την Τροποποιημένη Παρουσίαση

```java
// Αποθηκεύστε την παρουσίαση με το τροποποιημένο γράφημα
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```

Συγχαρητήρια! Τροποποιήσατε επιτυχώς ένα υπάρχον γράφημα σε μια παρουσίαση PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Τώρα μπορείτε να χρησιμοποιήσετε αυτόν τον κώδικα για να προσαρμόσετε γραφήματα στις παρουσιάσεις σας στο PowerPoint μέσω προγραμματισμού.

## Πλήρης κώδικας πηγής για υπάρχον γράφημα σε διαφάνειες Java

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
// Κλάση Instantiate Presentation που αντιπροσωπεύει αρχείο PPTX// Instantiate Presentation class που αντιπροσωπεύει αρχείο PPTX
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
// Πρόσβαση στο πρώτο slideMarker
ISlide sld = pres.getSlides().get_Item(0);
// Προσθήκη γραφήματος με προεπιλεγμένα δεδομένα
IChart chart = (IChart) sld.getShapes().get_Item(0);
// Ρύθμιση του ευρετηρίου του φύλλου δεδομένων γραφήματος
int defaultWorksheetIndex = 0;
//Λήψη του φύλλου εργασίας δεδομένων γραφήματος
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Αλλαγή γραφήματος Όνομα κατηγορίας
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
// Πάρτε την πρώτη σειρά γραφημάτων
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Τώρα γίνεται ενημέρωση δεδομένων σειράς
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");// Τροποποίηση ονόματος σειράς
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
// Πάρτε τη δεύτερη σειρά γραφημάτων
series = chart.getChartData().getSeries().get_Item(1);
// Τώρα γίνεται ενημέρωση δεδομένων σειράς
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");// Τροποποίηση ονόματος σειράς
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
// Τώρα, Προσθήκη νέας σειράς
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());
// Πάρτε την 3η σειρά γραφημάτων
series = chart.getChartData().getSeries().get_Item(2);
// Τώρα συμπληρώνονται δεδομένα σειράς
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
chart.setType(ChartType.ClusteredCylinder);
// Αποθήκευση παρουσίασης με γράφημα
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```
## συμπέρασμα

Σε αυτό το ολοκληρωμένο σεμινάριο, μάθαμε πώς να τροποποιούμε ένα υπάρχον γράφημα σε μια παρουσίαση του PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Ακολουθώντας τον οδηγό βήμα προς βήμα και χρησιμοποιώντας παραδείγματα πηγαίου κώδικα, μπορείτε εύκολα να προσαρμόσετε και να ενημερώσετε γραφήματα για να ανταποκρίνονται στις συγκεκριμένες απαιτήσεις σας. Ακολουθεί μια ανακεφαλαίωση όσων καλύψαμε:

## Συχνές ερωτήσεις

### Πώς μπορώ να αλλάξω τον τύπο του γραφήματος;

 Μπορείτε να αλλάξετε τον τύπο γραφήματος χρησιμοποιώντας το`chart.setType(ChartType.ChartTypeHere)` μέθοδος. Αντικαθιστώ`ChartTypeHere` με τον επιθυμητό τύπο γραφήματος, όπως`ChartType.ClusteredCylinder` στο παράδειγμά μας.

### Μπορώ να προσθέσω περισσότερα σημεία δεδομένων σε μια σειρά;

 Ναι, μπορείτε να προσθέσετε περισσότερα σημεία δεδομένων σε μια σειρά χρησιμοποιώντας το`series.getDataPoints().addDataPointForBarSeries(cell)` μέθοδος. Φροντίστε να παρέχετε τα κατάλληλα δεδομένα κυψέλης.

### Πώς μπορώ να ενημερώσω τα ονόματα των κατηγοριών;

 Μπορείτε να ενημερώσετε τα ονόματα των κατηγοριών χρησιμοποιώντας`fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` για να ορίσετε τα ονόματα των νέων κατηγοριών.

### Πώς μπορώ να τροποποιήσω τα ονόματα των σειρών;

 Για να τροποποιήσετε τα ονόματα των σειρών, χρησιμοποιήστε`fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` για να ορίσετε τα ονόματα των νέων σειρών.

### Υπάρχει τρόπος να αφαιρέσετε μια σειρά από το γράφημα;

 Ναι, μπορείτε να αφαιρέσετε μια σειρά από το γράφημα χρησιμοποιώντας το`chart.getChartData().getSeries().removeAt(index)` μέθοδος, όπου`index`είναι το ευρετήριο της σειράς που θέλετε να καταργήσετε.