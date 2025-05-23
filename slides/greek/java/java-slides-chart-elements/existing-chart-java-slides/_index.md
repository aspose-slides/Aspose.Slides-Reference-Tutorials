---
"description": "Βελτιώστε τις παρουσιάσεις PowerPoint σας με το Aspose.Slides για Java. Μάθετε να τροποποιείτε υπάρχοντα γραφήματα μέσω προγραμματισμού. Οδηγός βήμα προς βήμα με πηγαίο κώδικα για την προσαρμογή γραφημάτων."
"linktitle": "Υπάρχον γράφημα σε διαφάνειες Java"
"second_title": "Aspose.Slides API επεξεργασίας Java PowerPoint"
"title": "Υπάρχον γράφημα σε διαφάνειες Java"
"url": "/el/java/chart-elements/existing-chart-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Υπάρχον γράφημα σε διαφάνειες Java


## Εισαγωγή σε υπάρχοντα γραφήματα σε διαφάνειες Java χρησιμοποιώντας το Aspose.Slides για Java

Σε αυτό το σεμινάριο, θα δείξουμε πώς να τροποποιήσετε ένα υπάρχον γράφημα σε μια παρουσίαση PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Θα δούμε τα βήματα για να αλλάξετε δεδομένα γραφήματος, ονόματα κατηγοριών, ονόματα σειρών και να προσθέσετε μια νέα σειρά στο γράφημα. Βεβαιωθείτε ότι έχετε ρυθμίσει το Aspose.Slides για Java στο έργο σας.

## Προαπαιτούμενα

Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

1. Aspose.Slides για τη βιβλιοθήκη Java που περιλαμβάνεται στο έργο σας.
2. Μια υπάρχουσα παρουσίαση PowerPoint με ένα γράφημα που θέλετε να τροποποιήσετε.
3. Ρύθμιση περιβάλλοντος ανάπτυξης Java.

## Βήμα 1: Φόρτωση της παρουσίασης

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";

// Δημιουργία κλάσης παρουσίασης που αντιπροσωπεύει αρχείο PPTX
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
```

## Βήμα 2: Πρόσβαση στη διαφάνεια και το γράφημα

```java
// Πρόσβαση στην πρώτη διαφάνεια
ISlide sld = pres.getSlides().get_Item(0);

// Πρόσβαση στο γράφημα στη διαφάνεια
IChart chart = (IChart) sld.getShapes().get_Item(0);
```

## Βήμα 3: Αλλαγή δεδομένων γραφήματος και ονομάτων κατηγοριών

```java
// Ορισμός του ευρετηρίου του φύλλου δεδομένων γραφήματος
int defaultWorksheetIndex = 0;

// Λήψη του φύλλου εργασίας δεδομένων γραφήματος
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Αλλαγή ονομάτων κατηγοριών γραφημάτων
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
```

## Βήμα 4: Ενημέρωση Πρώτης Σειράς Γραφημάτων

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

## Βήμα 5: Ενημέρωση δεύτερης σειράς γραφημάτων

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

## Βήμα 6: Προσθήκη νέας σειράς στο διάγραμμα

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

## Βήμα 7: Αλλαγή τύπου γραφήματος

```java
// Αλλάξτε τον τύπο γραφήματος σε Κύλινδρος σε Ομαδοποιημένο
chart.setType(ChartType.ClusteredCylinder);
```

## Βήμα 8: Αποθήκευση της τροποποιημένης παρουσίασης

```java
// Αποθήκευση της παρουσίασης με το τροποποιημένο γράφημα
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```

Συγχαρητήρια! Τροποποιήσατε με επιτυχία ένα υπάρχον γράφημα σε μια παρουσίαση PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Μπορείτε πλέον να χρησιμοποιήσετε αυτόν τον κώδικα για να προσαρμόσετε τα γραφήματα στις παρουσιάσεις PowerPoint σας μέσω προγραμματισμού.

## Πλήρης πηγαίος κώδικας για υπάρχοντα γραφήματα σε διαφάνειες Java

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
// Δημιουργία κλάσης παρουσίασης που αντιπροσωπεύει το αρχείο PPTX// Δημιουργία κλάσης παρουσίασης που αντιπροσωπεύει το αρχείο PPTX
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
// Πρόσβαση στην πρώτη διαφάνεια Δείκτης
ISlide sld = pres.getSlides().get_Item(0);
// Προσθήκη γραφήματος με προεπιλεγμένα δεδομένα
IChart chart = (IChart) sld.getShapes().get_Item(0);
// Ρύθμιση του ευρετηρίου του φύλλου δεδομένων γραφήματος
int defaultWorksheetIndex = 0;
// Λήψη του φύλλου εργασίας δεδομένων γραφήματος
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Αλλαγή ονόματος κατηγορίας γραφήματος
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
// Πάρτε την πρώτη σειρά γραφημάτων
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Ενημερώνονται τώρα τα δεδομένα της σειράς.
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");// Τροποποίηση ονόματος σειράς
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
// Σειρά γραφημάτων Take Second
series = chart.getChartData().getSeries().get_Item(1);
// Ενημερώνονται τώρα τα δεδομένα της σειράς.
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");// Τροποποίηση ονόματος σειράς
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
// Τώρα, προσθέτοντας μια νέα σειρά
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());
// Πάρτε την 3η σειρά γραφημάτων
series = chart.getChartData().getSeries().get_Item(2);
// Συμπληρώνονται τώρα τα δεδομένα σειράς
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
chart.setType(ChartType.ClusteredCylinder);
// Αποθήκευση παρουσίασης με γράφημα
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```
## Σύναψη

Σε αυτό το ολοκληρωμένο σεμινάριο, μάθαμε πώς να τροποποιήσουμε ένα υπάρχον γράφημα σε μια παρουσίαση PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Ακολουθώντας τον οδηγό βήμα προς βήμα και αξιοποιώντας παραδείγματα πηγαίου κώδικα, μπορείτε εύκολα να προσαρμόσετε και να ενημερώσετε τα γραφήματα ώστε να ανταποκρίνονται στις συγκεκριμένες απαιτήσεις σας. Ακολουθεί μια ανακεφαλαίωση των όσων καλύψαμε:

## Συχνές ερωτήσεις

### Πώς μπορώ να αλλάξω τον τύπο γραφήματος;

Μπορείτε να αλλάξετε τον τύπο γραφήματος χρησιμοποιώντας το `chart.setType(ChartType.ChartTypeHere)` μέθοδος. Αντικατάσταση `ChartTypeHere` με τον επιθυμητό τύπο γραφήματος, όπως π.χ. `ChartType.ClusteredCylinder` στο παράδειγμά μας.

### Μπορώ να προσθέσω περισσότερα σημεία δεδομένων σε μια σειρά;

Ναι, μπορείτε να προσθέσετε περισσότερα σημεία δεδομένων σε μια σειρά χρησιμοποιώντας το `series.getDataPoints().addDataPointForBarSeries(cell)` μέθοδος. Βεβαιωθείτε ότι έχετε παράσχει τα κατάλληλα δεδομένα κελιού.

### Πώς μπορώ να ενημερώσω τα ονόματα των κατηγοριών;

Μπορείτε να ενημερώσετε τα ονόματα κατηγοριών χρησιμοποιώντας `fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` για να ορίσετε τα νέα ονόματα κατηγοριών.

### Πώς μπορώ να τροποποιήσω τα ονόματα των σειρών;

Για να τροποποιήσετε τα ονόματα των σειρών, χρησιμοποιήστε `fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` για να ορίσετε τα νέα ονόματα σειρών.

### Υπάρχει τρόπος να αφαιρέσω μια σειρά από το διάγραμμα;

Ναι, μπορείτε να αφαιρέσετε μια σειρά από το γράφημα χρησιμοποιώντας το `chart.getChartData().getSeries().removeAt(index)` μέθοδος, όπου `index` είναι ο δείκτης της σειράς που θέλετε να καταργήσετε.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}