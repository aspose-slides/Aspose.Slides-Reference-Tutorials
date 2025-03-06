---
title: Αυτόματο χρώμα σειράς γραφήματος σε διαφάνειες Java
linktitle: Αυτόματο χρώμα σειράς γραφήματος σε διαφάνειες Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Μάθετε πώς να δημιουργείτε δυναμικά γραφήματα με αυτόματο χρώμα σειρών σε παρουσιάσεις PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Βελτιώστε τις οπτικοποιήσεις δεδομένων σας χωρίς κόπο.
weight: 14
url: /el/java/chart-data-manipulation/automatic-chart-series-color-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Αυτόματο χρώμα σειράς γραφήματος σε διαφάνειες Java


## Εισαγωγή στο Automatic Chart Series Color στο Aspose.Slides για Java

Σε αυτό το σεμινάριο, θα διερευνήσουμε πώς να δημιουργήσετε μια παρουσίαση PowerPoint με ένα γράφημα χρησιμοποιώντας το Aspose.Slides για Java και να ορίσετε αυτόματα χρώματα γεμίσματος για σειρές γραφημάτων. Τα χρώματα αυτόματης πλήρωσης μπορούν να κάνουν τα γραφήματα σας πιο ελκυστικά οπτικά και να σας εξοικονομήσουν χρόνο αφήνοντας τη βιβλιοθήκη να επιλέξει χρώματα για εσάς.

## Προαπαιτούμενα

 Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε εγκαταστήσει τη βιβλιοθήκη Aspose.Slides for Java στο έργο σας. Μπορείτε να το κατεβάσετε από[εδώ](https://releases.aspose.com/slides/java/).

## Βήμα 1: Δημιουργία νέας παρουσίασης

Αρχικά, θα δημιουργήσουμε μια νέα παρουσίαση PowerPoint και θα προσθέσουμε μια διαφάνεια σε αυτήν.

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
// Δημιουργήστε μια παρουσία της κλάσης παρουσίασης
Presentation presentation = new Presentation();
```

## Βήμα 2: Προσθέστε ένα γράφημα στη διαφάνεια

Στη συνέχεια, θα προσθέσουμε ένα γράφημα ομαδοποιημένης στήλης στη διαφάνεια. Θα ρυθμίσουμε επίσης την πρώτη σειρά να εμφανίζει τιμές.

```java
// Πρόσβαση στην πρώτη διαφάνεια
ISlide slide = presentation.getSlides().get_Item(0);
// Προσθήκη γραφήματος με προεπιλεγμένα δεδομένα
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Ορίστε την πρώτη σειρά σε Εμφάνιση τιμών
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

## Βήμα 3: Συμπλήρωση δεδομένων γραφήματος

Τώρα, θα συμπληρώσουμε το γράφημα με δεδομένα. Θα ξεκινήσουμε διαγράφοντας τις προεπιλεγμένες σειρές και κατηγορίες που δημιουργούνται και, στη συνέχεια, θα προσθέσουμε νέες σειρές και κατηγορίες.

```java
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

## Βήμα 4: Συμπλήρωση δεδομένων σειράς

Θα συμπληρώσουμε τα δεδομένα της σειράς τόσο για τη Σειρά 1 όσο και για τη Σειρά 2.

```java
// Πάρτε την πρώτη σειρά γραφημάτων
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Τώρα συμπληρώνονται δεδομένα σειράς
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Πάρτε τη δεύτερη σειρά γραφημάτων
series = chart.getChartData().getSeries().get_Item(1);
// Τώρα συμπληρώνονται δεδομένα σειράς
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## Βήμα 5: Ορίστε το Automatic Fill Color για τη σειρά

Τώρα, ας ορίσουμε τα χρώματα αυτόματης πλήρωσης για τη σειρά γραφημάτων. Αυτό θα κάνει τη βιβλιοθήκη να επιλέξει χρώματα για εμάς.

```java
// Ρύθμιση αυτόματου χρώματος πλήρωσης για σειρές
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

## Βήμα 6: Αποθηκεύστε την παρουσίαση

Τέλος, θα αποθηκεύσουμε την παρουσίαση με το γράφημα σε ένα αρχείο PowerPoint.

```java
// Αποθήκευση παρουσίασης με γράφημα
presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
```

## Ολοκληρωμένος πηγαίος κώδικας για αυτόματο χρώμα σειράς γραφήματος σε διαφάνειες Java

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
// Δημιουργήστε μια παρουσία της κλάσης παρουσίασης
Presentation presentation = new Presentation();
try
{
	// Πρόσβαση στην πρώτη διαφάνεια
	ISlide slide = presentation.getSlides().get_Item(0);
	// Προσθήκη γραφήματος με προεπιλεγμένα δεδομένα
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
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
	// Ρύθμιση αυτόματου χρώματος πλήρωσης για σειρές
	series.getFormat().getFill().setFillType(FillType.NotDefined);
	// Πάρτε τη δεύτερη σειρά γραφημάτων
	series = chart.getChartData().getSeries().get_Item(1);
	// Τώρα συμπληρώνονται δεδομένα σειράς
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
	// Ρύθμιση χρώματος γεμίσματος για τη σειρά
	series.getFormat().getFill().setFillType(FillType.Solid);
	series.getFormat().getFill().getSolidFillColor().setColor(Color.GRAY);
	// Αποθήκευση παρουσίασης με γράφημα
	presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## συμπέρασμα

Σε αυτό το σεμινάριο, μάθαμε πώς να δημιουργήσουμε μια παρουσίαση PowerPoint με ένα γράφημα χρησιμοποιώντας το Aspose.Slides για Java και να ορίσουμε αυτόματα χρώματα γεμίσματος για σειρές γραφημάτων. Τα αυτόματα χρώματα μπορούν να ενισχύσουν την οπτική ελκυστικότητα των γραφημάτων σας και να κάνουν τις παρουσιάσεις σας πιο ελκυστικές. Μπορείτε να προσαρμόσετε περαιτέρω το γράφημα ανάλογα με τις ανάγκες σας.

## Συχνές ερωτήσεις

### Πώς μπορώ να ορίσω τα χρώματα αυτόματης πλήρωσης για σειρές γραφημάτων στο Aspose.Slides για Java;

Για να ορίσετε χρώματα αυτόματης πλήρωσης για σειρές γραφημάτων στο Aspose.Slides για Java, χρησιμοποιήστε τον ακόλουθο κώδικα:

```java
// Ρύθμιση αυτόματου χρώματος πλήρωσης για σειρές
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

Αυτός ο κωδικός θα επιτρέψει στη βιβλιοθήκη να επιλέξει αυτόματα χρώματα για τη σειρά γραφημάτων.

### Μπορώ να προσαρμόσω τα χρώματα του γραφήματος εάν χρειάζεται;

 Ναι, μπορείτε να προσαρμόσετε τα χρώματα του γραφήματος όπως απαιτείται. Στο παράδειγμα που παρέχεται, χρησιμοποιήσαμε χρώματα αυτόματης πλήρωσης, αλλά μπορείτε να ορίσετε συγκεκριμένα χρώματα τροποποιώντας το`FillType` και`SolidFillColor` ιδιότητες της μορφής της σειράς.

### Πώς μπορώ να προσθέσω επιπλέον σειρές ή κατηγορίες στο γράφημα;

 Για να προσθέσετε επιπλέον σειρές ή κατηγορίες στο γράφημα, χρησιμοποιήστε το`getSeries()` και`getCategories()` μεθόδους του διαγράμματος`ChartData` αντικείμενο. Μπορείτε να προσθέσετε νέες σειρές και κατηγορίες καθορίζοντας τα δεδομένα και τις ετικέτες τους.

### Είναι δυνατή η περαιτέρω μορφοποίηση του γραφήματος και των ετικετών;

Ναι, μπορείτε να μορφοποιήσετε περαιτέρω το γράφημα, τις σειρές και τις ετικέτες όπως απαιτείται. Το Aspose.Slides για Java παρέχει εκτενείς επιλογές μορφοποίησης για γραφήματα, συμπεριλαμβανομένων γραμματοσειρών, χρωμάτων, στυλ και άλλων. Μπορείτε να εξερευνήσετε την τεκμηρίωση για περισσότερες λεπτομέρειες σχετικά με τις επιλογές μορφοποίησης.

### Πού μπορώ να βρω περισσότερες πληροφορίες σχετικά με την εργασία με το Aspose.Slides για Java;

 Για περισσότερες πληροφορίες και λεπτομερή τεκμηρίωση σχετικά με το Aspose.Slides για Java, μπορείτε να επισκεφτείτε την τεκμηρίωση αναφοράς[εδώ](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
