---
title: Διάσπαρτο γράφημα σε διαφάνειες Java
linktitle: Διάσπαρτο γράφημα σε διαφάνειες Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Μάθετε πώς να δημιουργείτε Διαγράμματα Scatter σε Java χρησιμοποιώντας το Aspose.Slides. Οδηγός βήμα προς βήμα με πηγαίο κώδικα Java για οπτικοποίηση δεδομένων σε παρουσιάσεις.
weight: 11
url: /el/java/chart-creation/scattered-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Διάσπαρτο γράφημα σε διαφάνειες Java


## Εισαγωγή στο διάσπαρτο γράφημα στο Aspose.Slides για Java

Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία δημιουργίας ενός Διαγράμματος Scatter χρησιμοποιώντας το Aspose.Slides για Java. Τα διαγράμματα διασποράς είναι χρήσιμα για την οπτικοποίηση σημείων δεδομένων σε ένα δισδιάστατο επίπεδο. Θα παρέχουμε οδηγίες βήμα προς βήμα και θα συμπεριλάβουμε τον πηγαίο κώδικα Java για τη διευκόλυνσή σας.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

1. [Aspose.Slides για Java](https://products.aspose.com/slides/java) εγκατασταθεί.
2. Δημιουργήθηκε ένα περιβάλλον ανάπτυξης Java.

## Βήμα 1: Αρχικοποιήστε την Παρουσίαση

Πρώτα, εισάγετε τις απαραίτητες βιβλιοθήκες και δημιουργήστε μια νέα παρουσίαση.

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";

// Δημιουργήστε κατάλογο εάν δεν υπάρχει ήδη.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();

// Δημιουργήστε μια νέα παρουσίαση
Presentation pres = new Presentation();
```

## Βήμα 2: Προσθέστε μια διαφάνεια και δημιουργήστε το διάγραμμα διασποράς

 Στη συνέχεια, προσθέστε μια διαφάνεια και δημιουργήστε το διάγραμμα διασποράς σε αυτήν. Θα χρησιμοποιήσουμε το`ScatterWithSmoothLines`τύπο γραφήματος σε αυτό το παράδειγμα.

```java
// Αποκτήστε την πρώτη διαφάνεια
ISlide slide = pres.getSlides().get_Item(0);

// Δημιουργία του διαγράμματος scatter
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

## Βήμα 3: Προετοιμάστε δεδομένα γραφήματος

Τώρα, ας προετοιμάσουμε τα δεδομένα για το διάγραμμα διασποράς μας. Θα προσθέσουμε δύο σειρές, η καθεμία με πολλά σημεία δεδομένων.

```java
// Λήψη του προεπιλεγμένου ευρετηρίου φύλλου εργασίας δεδομένων γραφήματος
int defaultWorksheetIndex = 0;

// Λήψη του φύλλου εργασίας δεδομένων γραφήματος
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Διαγραφή σειράς επίδειξης
chart.getChartData().getSeries().clear();

// Προσθέστε την πρώτη σειρά
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());

// Πάρτε την πρώτη σειρά γραφημάτων
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Προσθέστε σημεία δεδομένων στην πρώτη σειρά
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));

// Επεξεργαστείτε τον τύπο της σειράς
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10); // Αλλαγή μεγέθους δείκτη
series.getMarker().setSymbol(MarkerStyleType.Star); // Αλλαγή συμβόλου δείκτη

// Πάρτε τη δεύτερη σειρά γραφημάτων
series = chart.getChartData().getSeries().get_Item(1);

// Προσθέστε σημεία δεδομένων στη δεύτερη σειρά
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

// Αλλάξτε το στυλ του δείκτη για τη δεύτερη σειρά
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

## Βήμα 4: Αποθηκεύστε την Παρουσίαση

Τέλος, αποθηκεύστε την παρουσίαση με το διάγραμμα scatter σε ένα αρχείο PPTX.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

Αυτό είναι! Δημιουργήσατε με επιτυχία ένα διάγραμμα Scatter χρησιμοποιώντας το Aspose.Slides για Java. Τώρα μπορείτε να προσαρμόσετε περαιτέρω αυτό το παράδειγμα για να ταιριάζει στα συγκεκριμένα δεδομένα και τις απαιτήσεις σχεδίασής σας.

## Ολοκληρωμένος πηγαίος κώδικας για διάσπαρτα γραφήματα σε διαφάνειες Java
```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
// Δημιουργήστε κατάλογο εάν δεν υπάρχει ήδη.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
//Δημιουργία του προεπιλεγμένου γραφήματος
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
// Λήψη του προεπιλεγμένου ευρετηρίου φύλλου εργασίας δεδομένων γραφήματος
int defaultWorksheetIndex = 0;
// Λήψη του φύλλου εργασίας δεδομένων γραφήματος
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Διαγραφή σειράς επίδειξης
chart.getChartData().getSeries().clear();
// Προσθήκη νέας σειράς
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
// Πάρτε την πρώτη σειρά γραφημάτων
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Προσθέστε νέο σημείο (1:3) εκεί.
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
// Προσθήκη νέου σημείου (2:10)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
// Επεξεργαστείτε τον τύπο της σειράς
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
// Αλλαγή του δείκτη σειράς γραφήματος
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);
// Πάρτε τη δεύτερη σειρά γραφημάτων
series = chart.getChartData().getSeries().get_Item(1);
// Προσθέστε νέο σημείο (5:2) εκεί.
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
// Προσθήκη νέου σημείου (3:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
// Προσθήκη νέου σημείου (2:2)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
// Προσθήκη νέου σημείου (5:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));
// Αλλαγή του δείκτη σειράς γραφήματος
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## συμπέρασμα

Σε αυτό το σεμινάριο, σας καθοδηγήσαμε στη διαδικασία δημιουργίας ενός γραφήματος Scatter χρησιμοποιώντας το Aspose.Slides για Java. Τα διαγράμματα διασποράς είναι ισχυρά εργαλεία για την οπτικοποίηση σημείων δεδομένων σε έναν δισδιάστατο χώρο, διευκολύνοντας την ανάλυση και την κατανόηση πολύπλοκων σχέσεων δεδομένων.

## Συχνές ερωτήσεις

### Πώς μπορώ να αλλάξω τον τύπο του γραφήματος;

 Για να αλλάξετε τον τύπο γραφήματος, χρησιμοποιήστε το`setType` μέθοδο στη σειρά γραφημάτων και παρέχετε τον επιθυμητό τύπο γραφήματος. Για παράδειγμα,`series.setType(ChartType.Line)` θα άλλαζε τη σειρά σε γραμμικό γράφημα.

### Πώς μπορώ να προσαρμόσω το μέγεθος και το στυλ του δείκτη;

 Μπορείτε να αλλάξετε το μέγεθος και το στυλ του δείκτη χρησιμοποιώντας το`getMarker` μέθοδο στη σειρά και, στη συνέχεια, ορίστε τις ιδιότητες μεγέθους και συμβόλων. Για παράδειγμα:

```java
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

Μη διστάσετε να εξερευνήσετε περισσότερες επιλογές προσαρμογής στην τεκμηρίωση Aspose.Slides for Java.

 Θυμηθείτε να αντικαταστήσετε`"Your Document Directory"` με την πραγματική διαδρομή όπου θέλετε να αποθηκεύσετε την παρουσίαση.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
