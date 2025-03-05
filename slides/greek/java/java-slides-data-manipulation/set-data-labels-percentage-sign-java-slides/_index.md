---
title: Ορισμός ποσοστού ετικετών δεδομένων Σύνδεση σε διαφάνειες Java
linktitle: Ορισμός ποσοστού ετικετών δεδομένων Σύνδεση σε διαφάνειες Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Μάθετε πώς να ορίζετε ετικέτες δεδομένων με σύμβολα ποσοστού σε παρουσιάσεις PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Δημιουργήστε ελκυστικά γραφήματα με καθοδήγηση βήμα προς βήμα και πηγαίο κώδικα.
type: docs
weight: 17
url: /el/java/data-manipulation/set-data-labels-percentage-sign-java-slides/
---

## Εισαγωγή στο Set Data Labels Percentage Sign in Aspose.Slides for Java

Σε αυτόν τον οδηγό, θα σας καθοδηγήσουμε στη διαδικασία ορισμού ετικετών δεδομένων με σύμβολο ποσοστού χρησιμοποιώντας το Aspose.Slides για Java. Θα δημιουργήσουμε μια παρουσίαση PowerPoint με ένα γράφημα στηλών σε στοίβα και θα διαμορφώσουμε τις ετικέτες δεδομένων για να εμφανίζουν ποσοστά.

## Προαπαιτούμενα

 Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε προσθέσει τη βιβλιοθήκη Aspose.Slides for Java στο έργο σας. Μπορείτε να το κατεβάσετε από[εδώ](https://releases.aspose.com/slides/java/).

## Βήμα 1: Δημιουργία νέας παρουσίασης

Αρχικά, δημιουργούμε μια νέα παρουσίαση PowerPoint χρησιμοποιώντας το Aspose.Slides.

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
// Δημιουργήστε μια παρουσία της κλάσης παρουσίασης
Presentation presentation = new Presentation();
```

## Βήμα 2: Προσθέστε μια διαφάνεια και ένα γράφημα

Στη συνέχεια, προσθέτουμε μια διαφάνεια και ένα γράφημα στηλών σε στοίβα στην παρουσίαση.

```java
// Λάβετε αναφορά για τη διαφάνεια
ISlide slide = presentation.getSlides().get_Item(0);

// Προσθήκη γραφήματος PercentsStackedColumn σε μια διαφάνεια
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

## Βήμα 3: Διαμορφώστε τη μορφή αριθμού άξονα

Για να εμφανίσουμε ποσοστά, πρέπει να διαμορφώσουμε τη μορφή αριθμών για τον κατακόρυφο άξονα του γραφήματος.

```java
// Ορίστε το NumberFormatLinkedToSource σε false
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
// Ρύθμιση ιδιοτήτων LabelFormat
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

## Βήμα 6: Αποθηκεύστε την παρουσίαση

Τέλος, αποθηκεύουμε την παρουσίαση σε αρχείο PowerPoint.

```java
// Γράψτε την παρουσίαση στο δίσκο
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

Αυτό είναι! Δημιουργήσατε επιτυχώς μια παρουσίαση PowerPoint με ένα γράφημα στηλών στοιβαγμένων και διαμορφώσατε ετικέτες δεδομένων για εμφάνιση ποσοστών χρησιμοποιώντας το Aspose.Slides για Java.

## Ολοκληρώστε τον πηγαίο κώδικα για το σύνολο ετικετών δεδομένων Ποσοστό Είσοδος στις διαφάνειες Java

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
// Δημιουργήστε μια παρουσία της κλάσης παρουσίασης
Presentation presentation = new Presentation();
// Λάβετε αναφορά για τη διαφάνεια
ISlide slide = presentation.getSlides().get_Item(0);
// Προσθήκη γραφήματος PercentsStackedColumn σε μια διαφάνεια
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
// Ορίστε το NumberFormatLinkedToSource σε false
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
// Ρύθμιση του χρώματος πλήρωσης της σειράς
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// Ρύθμιση ιδιοτήτων LabelFormat
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
// Ρύθμιση τύπου γεμίσματος και χρώματος
series2.getFormat().getFill().setFillType(FillType.Solid);
series2.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE);
series2.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
// Γράψτε την παρουσίαση στο δίσκο
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

## συμπέρασμα

Ακολουθώντας αυτόν τον οδηγό, έχετε μάθει πώς να δημιουργείτε ελκυστικές παρουσιάσεις με ετικέτες δεδομένων βάσει ποσοστών, οι οποίες μπορούν να είναι ιδιαίτερα χρήσιμες για την αποτελεσματική μετάδοση πληροφοριών σε επαγγελματικές αναφορές, εκπαιδευτικό υλικό και άλλα.

## Συχνές ερωτήσεις

### Πώς μπορώ να αλλάξω τα χρώματα της σειράς γραφημάτων;

 Μπορείτε να αλλάξετε το χρώμα πλήρωσης των σειρών γραφημάτων χρησιμοποιώντας το`setFill` μέθοδο όπως φαίνεται στο παράδειγμα.

### Μπορώ να προσαρμόσω το μέγεθος γραμματοσειράς των ετικετών δεδομένων;

Ναι, μπορείτε να προσαρμόσετε το μέγεθος γραμματοσειράς των ετικετών δεδομένων ορίζοντας το`setFontHeight` ιδιοκτησία όπως φαίνεται στον κώδικα.

### Πώς μπορώ να προσθέσω περισσότερες σειρές στο γράφημα;

 Μπορείτε να προσθέσετε επιπλέον σειρές στο γράφημα χρησιμοποιώντας το`add` μέθοδος στο`IChartSeriesCollection` αντικείμενο.
