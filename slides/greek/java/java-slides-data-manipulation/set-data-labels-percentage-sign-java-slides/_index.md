---
"description": "Μάθετε πώς να ορίζετε ετικέτες δεδομένων με ποσοστιαία σύμβολα σε παρουσιάσεις PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Δημιουργήστε ελκυστικά γραφήματα με αναλυτικές οδηγίες και πηγαίο κώδικα."
"linktitle": "Ορισμός ετικετών δεδομένων Ποσοστό Σύνδεση Διαφάνειες Java"
"second_title": "Aspose.Slides API επεξεργασίας Java PowerPoint"
"title": "Ορισμός ετικετών δεδομένων Ποσοστό Σύνδεση Διαφάνειες Java"
"url": "/el/java/data-manipulation/set-data-labels-percentage-sign-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ορισμός ετικετών δεδομένων Ποσοστό Σύνδεση Διαφάνειες Java


## Εισαγωγή στο Ορισμός ετικετών δεδομένων Ποσοστό Σύνδεση Aspose.Slides για Java

Σε αυτόν τον οδηγό, θα σας καθοδηγήσουμε στη διαδικασία ορισμού ετικετών δεδομένων με ένα σύμβολο ποσοστού χρησιμοποιώντας το Aspose.Slides για Java. Θα δημιουργήσουμε μια παρουσίαση PowerPoint με ένα γράφημα στοιβαγμένων στηλών και θα διαμορφώσουμε ετικέτες δεδομένων για την εμφάνιση ποσοστών.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε προσθέσει στο έργο σας τη βιβλιοθήκη Aspose.Slides για Java. Μπορείτε να την κατεβάσετε από [εδώ](https://releases.aspose.com/slides/java/).

## Βήμα 1: Δημιουργία νέας παρουσίασης

Αρχικά, δημιουργούμε μια νέα παρουσίαση PowerPoint χρησιμοποιώντας το Aspose.Slides.

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
// Δημιουργήστε μια παρουσία της κλάσης Presentation
Presentation presentation = new Presentation();
```

## Βήμα 2: Προσθήκη διαφάνειας και γραφήματος

Στη συνέχεια, προσθέτουμε μια διαφάνεια και ένα γράφημα σωρευμένων στηλών στην παρουσίαση.

```java
// Λήψη αναφοράς της διαφάνειας
ISlide slide = presentation.getSlides().get_Item(0);

// Προσθήκη γραφήματος PercentsStackedColumn σε μια διαφάνεια
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

## Βήμα 3: Ρύθμιση παραμέτρων μορφής αριθμού άξονα

Για να εμφανίσουμε ποσοστά, πρέπει να διαμορφώσουμε τη μορφή αριθμών για τον κατακόρυφο άξονα του γραφήματος.

```java
// Ορισμός του NumberFormatLinkedToSource σε false
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
```

## Βήμα 4: Προσθήκη δεδομένων γραφήματος

Προσθέτουμε δεδομένα στο γράφημα δημιουργώντας σειρές και σημεία δεδομένων. Σε αυτό το παράδειγμα, προσθέτουμε δύο σειρές με τα αντίστοιχα σημεία δεδομένων τους.

```java
// Λήψη του φύλλου εργασίας δεδομένων γραφήματος
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// Προσθήκη νέας σειράς
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));

// Προσθήκη νέας σειράς
IChartSeries series2 = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.getType());
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 2, 0.35));
```

## Βήμα 5: Προσαρμογή ετικετών δεδομένων

Τώρα, ας προσαρμόσουμε την εμφάνιση των ετικετών δεδομένων.

```java
// Ορισμός ιδιοτήτων LabelFormat
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);

series2.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
```

## Βήμα 6: Αποθήκευση της παρουσίασης

Τέλος, αποθηκεύουμε την παρουσίαση σε ένα αρχείο PowerPoint.

```java
// Εγγραφή παρουσίασης σε δίσκο
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

Αυτό ήταν! Δημιουργήσατε με επιτυχία μια παρουσίαση PowerPoint με ένα γράφημα στοιβαγμένων στηλών και ρυθμίσατε τις ετικέτες δεδομένων για την εμφάνιση ποσοστών χρησιμοποιώντας το Aspose.Slides για Java.

## Πλήρης πηγαίος κώδικας για το σύνολο ετικετών δεδομένων Ποσοστό Σύνδεση σε διαφάνειες Java

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
// Δημιουργήστε μια παρουσία της κλάσης Presentation
Presentation presentation = new Presentation();
// Λήψη αναφοράς της διαφάνειας
ISlide slide = presentation.getSlides().get_Item(0);
// Προσθήκη γραφήματος PercentsStackedColumn σε μια διαφάνεια
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
// Ορισμός του NumberFormatLinkedToSource σε false
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
chart.getChartData().getSeries().clear();
int defaultWorksheetIndex = 0;
// Λήψη του φύλλου εργασίας δεδομένων γραφήματος
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
// Προσθήκη νέας σειράς
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));
// Ορισμός του χρώματος γεμίσματος της σειράς
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// Ορισμός ιδιοτήτων LabelFormat
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Προσθήκη νέας σειράς
IChartSeries series2 = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.getType());
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 2, 0.35));
// Ρύθμιση τύπου και χρώματος γεμίσματος
series2.getFormat().getFill().setFillType(FillType.Solid);
series2.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE);
series2.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
// Εγγραφή παρουσίασης σε δίσκο
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

## Σύναψη

Ακολουθώντας αυτόν τον οδηγό, μάθατε πώς να δημιουργείτε ελκυστικές παρουσιάσεις με ετικέτες δεδομένων που βασίζονται σε ποσοστά, οι οποίες μπορούν να είναι ιδιαίτερα χρήσιμες για την αποτελεσματική μεταφορά πληροφοριών σε επιχειρηματικές αναφορές, εκπαιδευτικό υλικό και πολλά άλλα.

## Συχνές ερωτήσεις

### Πώς μπορώ να αλλάξω τα χρώματα της σειράς γραφημάτων;

Μπορείτε να αλλάξετε το χρώμα γεμίσματος μιας σειράς γραφημάτων χρησιμοποιώντας το `setFill` μέθοδος όπως φαίνεται στο παράδειγμα.

### Μπορώ να προσαρμόσω το μέγεθος γραμματοσειράς των ετικετών δεδομένων;

Ναι, μπορείτε να προσαρμόσετε το μέγεθος γραμματοσειράς των ετικετών δεδομένων ορίζοντας το `setFontHeight` ιδιοκτησίας όπως αποδεικνύεται στον κώδικα.

### Πώς μπορώ να προσθέσω περισσότερες σειρές στο γράφημα;

Μπορείτε να προσθέσετε επιπλέον σειρές στο γράφημα χρησιμοποιώντας το `add` μέθοδος στο `IChartSeriesCollection` αντικείμενο.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}