---
"description": "Μάθετε πώς να δημιουργείτε γραφήματα διασποράς σε Java χρησιμοποιώντας το Aspose.Slides. Οδηγός βήμα προς βήμα με πηγαίο κώδικα Java για οπτικοποίηση δεδομένων σε παρουσιάσεις."
"linktitle": "Διάσπαρτο γράφημα σε διαφάνειες Java"
"second_title": "Aspose.Slides API επεξεργασίας Java PowerPoint"
"title": "Διάσπαρτο γράφημα σε διαφάνειες Java"
"url": "/el/java/chart-creation/scattered-chart-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Διάσπαρτο γράφημα σε διαφάνειες Java


## Εισαγωγή στο Scattered Chart στο Aspose.Slides για Java

Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία δημιουργίας ενός γραφήματος διασποράς χρησιμοποιώντας το Aspose.Slides για Java. Τα γραφήματα διασποράς είναι χρήσιμα για την οπτικοποίηση σημείων δεδομένων σε ένα δισδιάστατο επίπεδο. Θα παρέχουμε οδηγίες βήμα προς βήμα και θα συμπεριλάβουμε πηγαίο κώδικα Java για την διευκόλυνσή σας.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

1. [Aspose.Slides για Java](https://products.aspose.com/slides/java) εγκατεστημένο.
2. Ρύθμιση ενός περιβάλλοντος ανάπτυξης Java.

## Βήμα 1: Αρχικοποίηση της παρουσίασης

Αρχικά, εισαγάγετε τις απαραίτητες βιβλιοθήκες και δημιουργήστε μια νέα παρουσίαση.

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";

// Δημιουργήστε έναν κατάλογο εάν δεν υπάρχει ήδη.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();

// Δημιουργία νέας παρουσίασης
Presentation pres = new Presentation();
```

## Βήμα 2: Προσθήκη διαφάνειας και δημιουργία γραφήματος διασποράς

Στη συνέχεια, προσθέστε μια διαφάνεια και δημιουργήστε το γράφημα διασποράς σε αυτήν. Θα χρησιμοποιήσουμε το `ScatterWithSmoothLines` τύπος γραφήματος σε αυτό το παράδειγμα.

```java
// Αποκτήστε την πρώτη διαφάνεια
ISlide slide = pres.getSlides().get_Item(0);

// Δημιουργία του γραφήματος διασποράς
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

## Βήμα 3: Προετοιμασία δεδομένων γραφήματος

Τώρα, ας προετοιμάσουμε τα δεδομένα για το διάγραμμα διασποράς μας. Θα προσθέσουμε δύο σειρές, καθεμία με πολλά σημεία δεδομένων.

```java
// Λήψη του προεπιλεγμένου ευρετηρίου φύλλου εργασίας δεδομένων γραφήματος
int defaultWorksheetIndex = 0;

// Λήψη του φύλλου εργασίας δεδομένων γραφήματος
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Διαγραφή σειράς επίδειξης
chart.getChartData().getSeries().clear();

// Προσθήκη της πρώτης σειράς
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());

// Πάρτε την πρώτη σειρά γραφημάτων
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Προσθήκη σημείων δεδομένων στην πρώτη σειρά
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));

// Επεξεργασία του τύπου σειράς
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10); // Αλλαγή μεγέθους δείκτη
series.getMarker().setSymbol(MarkerStyleType.Star); // Αλλαγή συμβόλου δείκτη

// Πάρτε τη δεύτερη σειρά γραφημάτων
series = chart.getChartData().getSeries().get_Item(1);

// Προσθήκη σημείων δεδομένων στη δεύτερη σειρά
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

// Αλλαγή του στυλ δείκτη για τη δεύτερη σειρά
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

## Βήμα 4: Αποθήκευση της παρουσίασης

Τέλος, αποθηκεύστε την παρουσίαση με το γράφημα διασποράς σε ένα αρχείο PPTX.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

Αυτό ήταν! Δημιουργήσατε με επιτυχία ένα διάγραμμα διασποράς χρησιμοποιώντας το Aspose.Slides για Java. Τώρα μπορείτε να προσαρμόσετε περαιτέρω αυτό το παράδειγμα ώστε να ταιριάζει στις συγκεκριμένες απαιτήσεις δεδομένων και σχεδίασης που έχετε.

## Πλήρης πηγαίος κώδικας για διάσπαρτα γραφήματα σε διαφάνειες Java
```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
// Δημιουργήστε έναν κατάλογο εάν δεν υπάρχει ήδη.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
// Δημιουργία του προεπιλεγμένου γραφήματος
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
// Προσθέστε εκεί ένα νέο σημείο (1:3).
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
// Προσθήκη νέου σημείου (2:10)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
// Επεξεργασία του τύπου σειράς
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
// Αλλαγή του δείκτη σειράς γραφήματος
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);
// Πάρτε τη δεύτερη σειρά γραφημάτων
series = chart.getChartData().getSeries().get_Item(1);
// Προσθέστε εκεί ένα νέο σημείο (5:2).
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

## Σύναψη

Σε αυτό το σεμινάριο, σας καθοδηγήσαμε στη διαδικασία δημιουργίας ενός γραφήματος διασποράς χρησιμοποιώντας το Aspose.Slides για Java. Τα γραφήματα διασποράς είναι ισχυρά εργαλεία για την οπτικοποίηση σημείων δεδομένων σε έναν δισδιάστατο χώρο, διευκολύνοντας την ανάλυση και την κατανόηση σύνθετων σχέσεων δεδομένων.

## Συχνές ερωτήσεις

### Πώς μπορώ να αλλάξω τον τύπο γραφήματος;

Για να αλλάξετε τον τύπο γραφήματος, χρησιμοποιήστε το `setType` μέθοδο στη σειρά γραφημάτων και παρέχετε τον επιθυμητό τύπο γραφήματος. Για παράδειγμα, `series.setType(ChartType.Line)` θα άλλαζε τη σειρά σε γραμμικό διάγραμμα.

### Πώς μπορώ να προσαρμόσω το μέγεθος και το στυλ του δείκτη;

Μπορείτε να αλλάξετε το μέγεθος και το στυλ του δείκτη χρησιμοποιώντας το `getMarker` μέθοδο στη σειρά και στη συνέχεια ορίστε τις ιδιότητες μεγέθους και συμβόλου. Για παράδειγμα:

```java
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

Μη διστάσετε να εξερευνήσετε περισσότερες επιλογές προσαρμογής στην τεκμηρίωση του Aspose.Slides για Java.

Θυμηθείτε να αντικαταστήσετε `"Your Document Directory"` με την πραγματική διαδρομή όπου θέλετε να αποθηκεύσετε την παρουσίαση.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}