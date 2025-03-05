---
title: Κανονικά γραφήματα σε διαφάνειες Java
linktitle: Κανονικά γραφήματα σε διαφάνειες Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Δημιουργήστε κανονικά γραφήματα σε διαφάνειες Java με το Aspose.Slides για Java. Οδηγός βήμα προς βήμα και πηγαίος κώδικας για τη δημιουργία, την προσαρμογή και την αποθήκευση γραφημάτων σε παρουσιάσεις PowerPoint.
type: docs
weight: 21
url: /el/java/chart-data-manipulation/normal-charts-java-slides/
---

## Εισαγωγή στα κανονικά γραφήματα σε διαφάνειες Java

Σε αυτό το σεμινάριο, θα ακολουθήσουμε τη διαδικασία δημιουργίας κανονικών γραφημάτων σε διαφάνειες Java χρησιμοποιώντας το Aspose.Slides for Java API. Θα χρησιμοποιήσουμε οδηγίες βήμα προς βήμα μαζί με τον πηγαίο κώδικα για να δείξουμε πώς να δημιουργήσετε ένα γράφημα ομαδοποιημένων στηλών σε μια παρουσίαση PowerPoint.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

1. Το Aspose.Slides for Java API έχει εγκατασταθεί.
2. Δημιουργήθηκε ένα περιβάλλον ανάπτυξης Java.
3. Βασικές γνώσεις προγραμματισμού Java.

## Βήμα 1: Ρύθμιση του έργου

Βεβαιωθείτε ότι έχετε έναν κατάλογο για το έργο σας. Ας το ονομάσουμε "Ο Κατάλογος Εγγράφων σας" όπως αναφέρεται στον κώδικα. Μπορείτε να το αντικαταστήσετε με την πραγματική διαδρομή προς τον κατάλογο του έργου σας.

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
// Δημιουργήστε κατάλογο εάν δεν υπάρχει ήδη.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```

## Βήμα 2: Δημιουργία παρουσίασης

Τώρα, ας δημιουργήσουμε μια παρουσίαση PowerPoint και ας αποκτήσουμε πρόσβαση στην πρώτη της διαφάνεια.

```java
// Κλάση Instantiation Presentation που αντιπροσωπεύει το αρχείο PPTX
Presentation pres = new Presentation();
// Πρόσβαση στην πρώτη διαφάνεια
ISlide sld = pres.getSlides().get_Item(0);
```

## Βήμα 3: Προσθήκη γραφήματος

Θα προσθέσουμε ένα γράφημα στήλης ομαδοποίησης στη διαφάνεια και θα ορίσουμε τον τίτλο του.

```java
// Προσθήκη γραφήματος με προεπιλεγμένα δεδομένα
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Ρύθμιση τίτλου γραφήματος
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## Βήμα 4: Ρύθμιση δεδομένων γραφήματος

Στη συνέχεια, θα ορίσουμε τα δεδομένα του γραφήματος ορίζοντας σειρές και κατηγορίες.

```java
// Ορίστε την πρώτη σειρά σε Εμφάνιση τιμών
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Ρύθμιση του ευρετηρίου του φύλλου δεδομένων γραφήματος
int defaultWorksheetIndex = 0;

// Λήψη του φύλλου εργασίας δεδομένων γραφήματος
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Διαγραφή προεπιλεγμένων σειρών και κατηγοριών που δημιουργούνται
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Προσθήκη νέας σειράς
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Προσθήκη νέων κατηγοριών
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## Βήμα 5: Συμπλήρωση δεδομένων σειράς

Τώρα, ας συμπληρώσουμε τα σημεία δεδομένων σειράς για το γράφημα.

```java
// Πάρτε την πρώτη σειρά γραφημάτων
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Συμπλήρωση δεδομένων σειράς
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Ρύθμιση χρώματος γεμίσματος για τη σειρά
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Πάρτε τη δεύτερη σειρά γραφημάτων
series = chart.getChartData().getSeries().get_Item(1);

// Συμπλήρωση δεδομένων σειράς
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));

// Ρύθμιση χρώματος γεμίσματος για τη σειρά
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## Βήμα 6: Προσαρμογή ετικετών

Ας προσαρμόσουμε τις ετικέτες δεδομένων για τις σειρές γραφημάτων.

```java
// Η πρώτη ετικέτα θα εμφανίζει το όνομα της κατηγορίας
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);

lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);

// Εμφάνιση τιμής για την τρίτη ετικέτα με όνομα σειράς και διαχωριστικό
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
```

## Βήμα 7: Αποθήκευση της παρουσίασης

Τέλος, αποθηκεύστε την παρουσίαση με το γράφημα στον κατάλογο του έργου σας.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

Αυτό είναι! Έχετε δημιουργήσει με επιτυχία ένα γράφημα στηλών συμπλέγματος σε μια παρουσίαση του PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Μπορείτε να προσαρμόσετε περαιτέρω αυτό το γράφημα σύμφωνα με τις απαιτήσεις σας.

## Ολοκληρωμένος πηγαίος κώδικας για κανονικά γραφήματα σε διαφάνειες Java

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
// Δημιουργήστε κατάλογο εάν δεν υπάρχει ήδη.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Κλάση Instantiation Presentation που αντιπροσωπεύει το αρχείο PPTX
Presentation pres = new Presentation();
// Πρόσβαση στην πρώτη διαφάνεια
ISlide sld = pres.getSlides().get_Item(0);
// Προσθήκη γραφήματος με προεπιλεγμένα δεδομένα
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Ρύθμιση τίτλου γραφήματος
// Chart.getChartTitle().getTextFrameForOverriding().setText("Sample Title");
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
// Ορίστε την πρώτη σειρά σε Εμφάνιση τιμών
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Ρύθμιση του ευρετηρίου του φύλλου δεδομένων γραφήματος
int defaultWorksheetIndex = 0;
// Λήψη του φύλλου εργασίας δεδομένων γραφήματος
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Διαγραφή προεπιλεγμένων σειρών και κατηγοριών που δημιουργούνται
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
int s = chart.getChartData().getSeries().size();
s = chart.getChartData().getCategories().size();
// Προσθήκη νέας σειράς
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Προσθήκη νέων κατηγοριών
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Πάρτε την πρώτη σειρά γραφημάτων
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Τώρα συμπληρώνονται δεδομένα σειράς
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// Ρύθμιση χρώματος γεμίσματος για τη σειρά
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// Πάρτε τη δεύτερη σειρά γραφημάτων
series = chart.getChartData().getSeries().get_Item(1);
// Τώρα συμπληρώνονται δεδομένα σειράς
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Ρύθμιση χρώματος γεμίσματος για τη σειρά
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
// Η πρώτη ετικέτα θα εμφανίζεται στο όνομα της κατηγορίας
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);
lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);
// Εμφάνιση τιμής για τρίτη ετικέτα
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
// Αποθήκευση παρουσίασης με γράφημα
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```
# συμπέρασμα

Σε αυτό το σεμινάριο, μάθαμε πώς να δημιουργήσουμε κανονικά γραφήματα σε διαφάνειες Java χρησιμοποιώντας το Aspose.Slides for Java API. Περπατήσαμε σε έναν οδηγό βήμα προς βήμα με πηγαίο κώδικα για τη δημιουργία ενός γραφήματος στηλών ομαδοποίησης σε μια παρουσίαση του PowerPoint.

## Συχνές ερωτήσεις

### Πώς μπορώ να αλλάξω τον τύπο του γραφήματος;

 Για να αλλάξετε τον τύπο γραφήματος, τροποποιήστε το`ChartType`παράμετρος κατά την προσθήκη του γραφήματος χρησιμοποιώντας`sld.getShapes().addChart()`. Μπορείτε να επιλέξετε από διάφορους τύπους γραφημάτων που είναι διαθέσιμοι στο Aspose.Slides.

### Μπορώ να αλλάξω τα χρώματα της σειράς γραφημάτων;

 Ναι, μπορείτε να αλλάξετε τα χρώματα της σειράς γραφημάτων ορίζοντας το χρώμα πλήρωσης για κάθε σειρά χρησιμοποιώντας`series.getFormat().getFill().getSolidFillColor().setColor(Color.YOUR_COLOR)`.

### Πώς μπορώ να προσθέσω περισσότερες κατηγορίες ή σειρές στο γράφημα;

 Μπορείτε να προσθέσετε περισσότερες κατηγορίες ή σειρές στο γράφημα προσθέτοντας νέα σημεία δεδομένων και ετικέτες χρησιμοποιώντας το`chart.getChartData().getCategories().add()` και`chart.getChartData().getSeries().add()` μεθόδους.

### Πώς μπορώ να προσαρμόσω περαιτέρω τον τίτλο του γραφήματος;

 Μπορείτε να προσαρμόσετε περαιτέρω τον τίτλο του γραφήματος τροποποιώντας τις ιδιότητες του`chart.getChartTitle()` όπως στοίχιση κειμένου, μέγεθος γραμματοσειράς και χρώμα.

### Πώς μπορώ να αποθηκεύσω το γράφημα σε διαφορετική μορφή αρχείου;

 Για να αποθηκεύσετε το γράφημα σε διαφορετική μορφή αρχείου, αλλάξτε το`SaveFormat` παράμετρος στο`pres.save()` μέθοδο στην επιθυμητή μορφή (π.χ. PDF, PNG, JPEG).