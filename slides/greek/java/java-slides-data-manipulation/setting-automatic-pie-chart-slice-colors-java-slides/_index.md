---
title: Ρύθμιση αυτόματων χρωμάτων φέτας γραφήματος πίτας σε διαφάνειες Java
linktitle: Ρύθμιση αυτόματων χρωμάτων φέτας γραφήματος πίτας σε διαφάνειες Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Μάθετε πώς να δημιουργείτε δυναμικά γραφήματα πίτας με αυτόματα χρώματα τμημάτων σε παρουσιάσεις Java PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Οδηγός βήμα προς βήμα με τον πηγαίο κώδικα.
weight: 24
url: /el/java/data-manipulation/setting-automatic-pie-chart-slice-colors-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Εισαγωγή στη ρύθμιση των αυτόματων χρωμάτων φέτας γραφήματος πίτας σε διαφάνειες Java

Σε αυτό το σεμινάριο, θα διερευνήσουμε πώς να δημιουργήσουμε ένα γράφημα πίτας σε μια παρουσίαση του PowerPoint χρησιμοποιώντας το Aspose.Slides για Java και να ορίσουμε αυτόματα χρώματα τομής για το γράφημα. Θα παρέχουμε οδηγίες βήμα προς βήμα μαζί με τον πηγαίο κώδικα.

## Προαπαιτούμενα

 Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε εγκαταστήσει και ρυθμίσει τη βιβλιοθήκη Aspose.Slides for Java στο έργο σας Java. Μπορείτε να κατεβάσετε τη βιβλιοθήκη από τον ιστότοπο Aspose:[Κατεβάστε το Aspose.Slides για Java](https://releases.aspose.com/slides/java/).

## Βήμα 1: Εισαγάγετε τα απαιτούμενα πακέτα

Πρώτα, πρέπει να εισαγάγετε τα απαραίτητα πακέτα από το Aspose.Slides για Java:

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.NullableBool;
import com.aspose.slides.charts.IChartDataWorkbook;
```

## Βήμα 2: Δημιουργήστε μια παρουσίαση PowerPoint

 Στιγμιότυπο το`Presentation` τάξη για να δημιουργήσετε μια νέα παρουσίαση PowerPoint:

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## Βήμα 3: Προσθέστε μια Διαφάνεια

Αποκτήστε πρόσβαση στην πρώτη διαφάνεια της παρουσίασης και προσθέστε ένα γράφημα σε αυτήν με προεπιλεγμένα δεδομένα:

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

## Βήμα 4: Ορισμός τίτλου γραφήματος

Ορίστε έναν τίτλο για το γράφημα:

```java
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## Βήμα 5: Διαμόρφωση δεδομένων γραφήματος

Ρυθμίστε το γράφημα ώστε να εμφανίζει τιμές για την πρώτη σειρά και διαμορφώστε τα δεδομένα του γραφήματος:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## Βήμα 6: Προσθέστε κατηγορίες και σειρές

Προσθέστε νέες κατηγορίες και σειρές στο γράφημα:

```java
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));

IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
```

## Βήμα 7: Συμπλήρωση δεδομένων σειράς

Συμπληρώστε τα δεδομένα σειράς για το γράφημα πίτας:

```java
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

## Βήμα 8: Ενεργοποίηση ποικίλων χρωμάτων τομέων

Ενεργοποίηση ποικίλων χρωμάτων φέτας για το γράφημα πίτας:

```java
series.getParentSeriesGroup().setColorVaried(true);
```

## Βήμα 9: Αποθηκεύστε την παρουσίαση

Τέλος, αποθηκεύστε την παρουσίαση σε αρχείο PowerPoint:

```java
presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
```

## Πλήρης πηγαίος κώδικας για τη ρύθμιση των αυτόματων χρωμάτων φέτας γραφήματος πίτας σε διαφάνειες Java

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
// Κλάση Instantiation Presentation που αντιπροσωπεύει το αρχείο PPTX
Presentation presentation = new Presentation();
try
{
	// Πρόσβαση στην πρώτη διαφάνεια
	ISlide slides = presentation.getSlides().get_Item(0);
	// Προσθήκη γραφήματος με προεπιλεγμένα δεδομένα
	IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
	// Ρύθμιση τίτλου γραφήματος
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
	// Προσθήκη νέων κατηγοριών
	chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
	// Προσθήκη νέας σειράς
	IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
	// Τώρα συμπληρώνονται δεδομένα σειράς
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	series.getParentSeriesGroup().setColorVaried(true);
	presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## συμπέρασμα

Έχετε δημιουργήσει με επιτυχία ένα γράφημα πίτας σε μια παρουσίαση του PowerPoint χρησιμοποιώντας το Aspose.Slides για Java και το ρυθμίσατε ώστε να έχει αυτόματα χρώματα τομής. Αυτός ο οδηγός βήμα προς βήμα σάς παρέχει τον απαραίτητο πηγαίο κώδικα για να το πετύχετε. Μπορείτε να προσαρμόσετε περαιτέρω το γράφημα και την παρουσίαση όπως απαιτείται.

## Συχνές ερωτήσεις

### Πώς μπορώ να προσαρμόσω τα χρώματα μεμονωμένων τμημάτων στο γράφημα πίτας;

 Για να προσαρμόσετε τα χρώματα των μεμονωμένων τμημάτων στο γράφημα πίτας, μπορείτε να χρησιμοποιήσετε το`getAutomaticSeriesColors` μέθοδο για να ανακτήσετε τον προεπιλεγμένο συνδυασμό χρωμάτων και στη συνέχεια να τροποποιήσετε τα χρώματα όπως απαιτείται. Εδώ είναι ένα παράδειγμα:

```java
//Λάβετε τον προεπιλεγμένο συνδυασμό χρωμάτων
IColorFormatCollection colors = chart.getChartData().getSeries().get_Item(0).getAutomaticSeriesColors();

// Τροποποιήστε τα χρώματα όπως απαιτείται
colors.get_Item(0).setColor(Color.RED); // Ρυθμίστε το χρώμα της πρώτης φέτας σε κόκκινο
colors.get_Item(1).setColor(Color.BLUE); // Ρυθμίστε το χρώμα της δεύτερης φέτας σε μπλε
// Προσθέστε περισσότερες χρωματικές τροποποιήσεις όπως απαιτείται
```

### Πώς μπορώ να προσθέσω ένα υπόμνημα στο γράφημα πίτας;

 Για να προσθέσετε ένα υπόμνημα στο γράφημα πίτας, μπορείτε να χρησιμοποιήσετε το`getLegend` μέθοδο και ρυθμίστε την ως εξής:

```java
ILegend legend = chart.getLegend();
legend.setPosition(LegendPositionType.Right); // Ρυθμίστε τη θέση του υπομνήματος
legend.setOverlay(true); // Εμφανίστε το υπόμνημα πάνω από το γράφημα
```

### Μπορώ να αλλάξω τη γραμματοσειρά και το στυλ του τίτλου;

Ναι, μπορείτε να αλλάξετε τη γραμματοσειρά και το στυλ του τίτλου. Χρησιμοποιήστε τον ακόλουθο κώδικα για να ορίσετε τη γραμματοσειρά και το στυλ του τίτλου:

```java
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(20); // Ορισμός μεγέθους γραμματοσειράς
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontBold(NullableBool.True); // Κάντε τον τίτλο με έντονους χαρακτήρες
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontItalic(NullableBool.True); // Κάντε τον τίτλο πλάγιο
```

Μπορείτε να προσαρμόσετε το μέγεθος της γραμματοσειράς, την τόλμη και το πλάγιο στυλ όπως απαιτείται.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
