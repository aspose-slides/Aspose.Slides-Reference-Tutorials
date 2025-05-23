---
"description": "Δημιουργήστε κανονικά γραφήματα σε διαφάνειες Java με το Aspose.Slides για Java. Οδηγός βήμα προς βήμα και πηγαίος κώδικας για τη δημιουργία, την προσαρμογή και την αποθήκευση γραφημάτων σε παρουσιάσεις PowerPoint."
"linktitle": "Κανονικά Γραφήματα σε Διαφάνειες Java"
"second_title": "Aspose.Slides API επεξεργασίας Java PowerPoint"
"title": "Κανονικά Γραφήματα σε Διαφάνειες Java"
"url": "/el/java/chart-data-manipulation/normal-charts-java-slides/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Κανονικά Γραφήματα σε Διαφάνειες Java


## Εισαγωγή στα Κανονικά Γραφήματα σε Διαφάνειες Java

Σε αυτό το σεμινάριο, θα περιηγηθούμε στη διαδικασία δημιουργίας κανονικών γραφημάτων σε Java Slides χρησιμοποιώντας το Aspose.Slides για Java API. Θα χρησιμοποιήσουμε οδηγίες βήμα προς βήμα μαζί με τον πηγαίο κώδικα για να δείξουμε πώς να δημιουργήσετε ένα γράφημα ομαδοποιημένων στηλών σε μια παρουσίαση PowerPoint.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

1. Εγκατεστημένο το Aspose.Slides για το Java API.
2. Ρύθμιση ενός περιβάλλοντος ανάπτυξης Java.
3. Βασικές γνώσεις προγραμματισμού Java.

## Βήμα 1: Ρύθμιση του Έργου

Βεβαιωθείτε ότι έχετε έναν κατάλογο για το έργο σας. Ας τον ονομάσουμε "Ο Κατάλογος Εγγράφων σας" όπως αναφέρεται στον κώδικα. Μπορείτε να τον αντικαταστήσετε με την πραγματική διαδρομή προς τον κατάλογο του έργου σας.

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
// Δημιουργήστε έναν κατάλογο εάν δεν υπάρχει ήδη.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```

## Βήμα 2: Δημιουργία παρουσίασης

Τώρα, ας δημιουργήσουμε μια παρουσίαση PowerPoint και ας αποκτήσουμε πρόσβαση στην πρώτη της διαφάνεια.

```java
// Δημιουργία κλάσης παρουσίασης που αντιπροσωπεύει αρχείο PPTX
Presentation pres = new Presentation();
// Πρόσβαση στην πρώτη διαφάνεια
ISlide sld = pres.getSlides().get_Item(0);
```

## Βήμα 3: Προσθήκη γραφήματος

Θα προσθέσουμε ένα γράφημα ομαδοποιημένων στηλών στη διαφάνεια και θα ορίσουμε τον τίτλο του.

```java
// Προσθήκη γραφήματος με προεπιλεγμένα δεδομένα
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Τίτλος γραφήματος ρύθμισης
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## Βήμα 4: Ορισμός δεδομένων γραφήματος

Στη συνέχεια, θα ορίσουμε τα δεδομένα του γραφήματος ορίζοντας σειρές και κατηγορίες.

```java
// Ορισμός της πρώτης σειράς σε Εμφάνιση τιμών
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Ρύθμιση του ευρετηρίου του φύλλου δεδομένων γραφήματος
int defaultWorksheetIndex = 0;

// Λήψη του φύλλου εργασίας δεδομένων γραφήματος
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Διαγραφή προεπιλεγμένων σειρών και κατηγοριών
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

// Ορισμός χρώματος γεμίσματος για σειρά
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Πάρτε τη δεύτερη σειρά γραφημάτων
series = chart.getChartData().getSeries().get_Item(1);

// Συμπλήρωση δεδομένων σειράς
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));

// Ορισμός χρώματος γεμίσματος για σειρά
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## Βήμα 6: Προσαρμογή ετικετών

Ας προσαρμόσουμε τις ετικέτες δεδομένων για τη σειρά γραφημάτων.

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

Αυτό ήταν! Δημιουργήσατε με επιτυχία ένα γράφημα ομαδοποιημένων στηλών σε μια παρουσίαση PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Μπορείτε να προσαρμόσετε αυτό το γράφημα περαιτέρω σύμφωνα με τις απαιτήσεις σας.

## Πλήρης πηγαίος κώδικας για κανονικά γραφήματα σε διαφάνειες Java

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
// Δημιουργήστε έναν κατάλογο εάν δεν υπάρχει ήδη.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Δημιουργία κλάσης παρουσίασης που αντιπροσωπεύει αρχείο PPTX
Presentation pres = new Presentation();
// Πρόσβαση στην πρώτη διαφάνεια
ISlide sld = pres.getSlides().get_Item(0);
// Προσθήκη γραφήματος με προεπιλεγμένα δεδομένα
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Τίτλος γραφήματος ρύθμισης
// Chart.getChartTitle().getTextFrameForOverriding().setText("Δείγμα Τίτλου");
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
// Ορισμός της πρώτης σειράς σε Εμφάνιση τιμών
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Ρύθμιση του ευρετηρίου του φύλλου δεδομένων γραφήματος
int defaultWorksheetIndex = 0;
// Λήψη του φύλλου εργασίας δεδομένων γραφήματος
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Διαγραφή προεπιλεγμένων σειρών και κατηγοριών
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
// Συμπληρώνονται τώρα τα δεδομένα σειράς
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// Ορισμός χρώματος γεμίσματος για σειρά
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// Πάρτε τη δεύτερη σειρά γραφημάτων
series = chart.getChartData().getSeries().get_Item(1);
// Συμπληρώνονται τώρα τα δεδομένα σειράς
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Ορισμός χρώματος γεμίσματος για σειρά
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
// Η πρώτη ετικέτα θα εμφανίζει το όνομα της κατηγορίας
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);
lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);
// Εμφάνιση τιμής για την τρίτη ετικέτα
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
// Αποθήκευση παρουσίασης με γράφημα
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```
# Σύναψη

Σε αυτό το σεμινάριο, μάθαμε πώς να δημιουργούμε κανονικά γραφήματα σε Java Slides χρησιμοποιώντας το Aspose.Slides για Java API. Παρακολουθήσαμε έναν αναλυτικό οδηγό με πηγαίο κώδικα για να δημιουργήσουμε ένα γράφημα ομαδοποιημένων στηλών σε μια παρουσίαση PowerPoint.

## Συχνές ερωτήσεις

### Πώς μπορώ να αλλάξω τον τύπο γραφήματος;

Για να αλλάξετε τον τύπο γραφήματος, τροποποιήστε το `ChartType` παράμετρος κατά την προσθήκη του γραφήματος χρησιμοποιώντας `sld.getShapes().addChart()`Μπορείτε να επιλέξετε από διάφορους τύπους γραφημάτων που είναι διαθέσιμοι στο Aspose.Slides.

### Μπορώ να αλλάξω τα χρώματα της σειράς γραφημάτων;

Ναι, μπορείτε να αλλάξετε τα χρώματα της σειράς γραφημάτων ορίζοντας το χρώμα γεμίσματος για κάθε σειρά χρησιμοποιώντας `series.getFormat().getFill().getSolidFillColor().setColor(Color.YOUR_COLOR)`.

### Πώς μπορώ να προσθέσω περισσότερες κατηγορίες ή σειρές στο γράφημα;

Μπορείτε να προσθέσετε περισσότερες κατηγορίες ή σειρές στο γράφημα προσθέτοντας νέα σημεία δεδομένων και ετικέτες χρησιμοποιώντας το `chart.getChartData().getCategories().add()` και `chart.getChartData().getSeries().add()` μεθόδους.

### Πώς μπορώ να προσαρμόσω περαιτέρω τον τίτλο του γραφήματος;

Μπορείτε να προσαρμόσετε περαιτέρω τον τίτλο του γραφήματος τροποποιώντας τις ιδιότητες του `chart.getChartTitle()` όπως η ευθυγράμμιση κειμένου, το μέγεθος γραμματοσειράς και το χρώμα.

### Πώς μπορώ να αποθηκεύσω το γράφημα σε διαφορετική μορφή αρχείου;

Για να αποθηκεύσετε το γράφημα σε διαφορετική μορφή αρχείου, αλλάξτε την `SaveFormat` παράμετρος στο `pres.save()` μέθοδο στην επιθυμητή μορφή (π.χ. PDF, PNG, JPEG).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}