---
title: Ορισμός πλάτους κενού στις διαφάνειες Java
linktitle: Ορισμός πλάτους κενού στις διαφάνειες Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Μάθετε πώς να ορίζετε το Gap Width σε Java Slides με το Aspose.Slides for Java. Βελτιώστε τα γραφικά για τις παρουσιάσεις σας στο PowerPoint.
weight: 21
url: /el/java/data-manipulation/set-gap-width-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Εισαγωγή στη ρύθμιση του πλάτους χάσματος στο Aspose.Slides για Java

Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία ρύθμισης του Gap Width για ένα γράφημα σε μια παρουσίαση PowerPoint χρησιμοποιώντας Aspose.Slides για Java. Το πλάτος κενού καθορίζει την απόσταση μεταξύ των στηλών ή των ράβδων σε ένα γράφημα, επιτρέποντάς σας να ελέγχετε την οπτική εμφάνιση του γραφήματος.

## Προαπαιτούμενα

 Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε εγκαταστήσει τη βιβλιοθήκη Aspose.Slides for Java. Μπορείτε να το κατεβάσετε από τον ιστότοπο Aspose[εδώ](https://releases.aspose.com/slides/java/).

## Οδηγός βήμα προς βήμα

Ακολουθήστε αυτά τα βήματα για να ορίσετε το πλάτος κενού σε ένα γράφημα χρησιμοποιώντας το Aspose.Slides για Java:

### 1. Δημιουργήστε μια κενή παρουσίαση

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";

// Δημιουργία κενής παρουσίασης
Presentation presentation = new Presentation();
```

### 2. Πρόσβαση στην Πρώτη Διαφάνεια

```java
// Πρόσβαση στην πρώτη διαφάνεια
ISlide slide = presentation.getSlides().get_Item(0);
```

### 3. Προσθέστε ένα γράφημα με προεπιλεγμένα δεδομένα

```java
// Προσθέστε ένα γράφημα με προεπιλεγμένα δεδομένα
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
```

### 4. Ορίστε το Ευρετήριο του φύλλου δεδομένων γραφήματος

```java
// Ρύθμιση του ευρετηρίου του φύλλου δεδομένων γραφήματος
int defaultWorksheetIndex = 0;
```

### 5. Λάβετε το Βιβλίο Εργασίας Δεδομένων Διαγράμματος

```java
// Λήψη του φύλλου εργασίας δεδομένων γραφήματος
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

### 6. Προσθήκη σειράς στο γράφημα

```java
// Προσθήκη σειράς στο γράφημα
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

### 7. Προσθέστε Κατηγορίες στο Διάγραμμα

```java
// Προσθέστε κατηγορίες στο γράφημα
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

### 8. Συμπληρώστε τα δεδομένα της σειράς

```java
// Συμπλήρωση δεδομένων σειράς
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Συμπλήρωση σημείων δεδομένων σειράς
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

### 9. Ρυθμίστε το πλάτος διάκενου

```java
// Ορίστε την τιμή Gap Width
series.getParentSeriesGroup().setGapWidth(50);
```

### 10. Αποθηκεύστε την Παρουσίαση

```java
// Αποθηκεύστε την παρουσίαση με το γράφημα
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## Ολοκληρωμένος πηγαίος κώδικας για ορισμό πλάτους χάσματος σε διαφάνειες Java

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
// Δημιουργία κενής παρουσίασης
Presentation presentation = new Presentation();
// Πρόσβαση στην πρώτη διαφάνεια
ISlide slide = presentation.getSlides().get_Item(0);
// Προσθήκη γραφήματος με προεπιλεγμένα δεδομένα
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
// Ρύθμιση του ευρετηρίου του φύλλου δεδομένων γραφήματος
int defaultWorksheetIndex = 0;
// Λήψη του φύλλου εργασίας δεδομένων γραφήματος
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Προσθήκη σειράς
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Προσθήκη Κατηγοριών
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Πάρτε τη δεύτερη σειρά γραφημάτων
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// Τώρα συμπληρώνονται δεδομένα σειράς
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Ορίστε την τιμή GapWidth
series.getParentSeriesGroup().setGapWidth(50);
// Αποθήκευση παρουσίασης με γράφημα
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## συμπέρασμα

Σε αυτό το σεμινάριο, μάθατε πώς να ορίζετε το πλάτος κενού για ένα γράφημα σε μια παρουσίαση του PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Η προσαρμογή του πλάτους χάσματος σάς επιτρέπει να ελέγχετε την απόσταση μεταξύ στηλών ή ράβδων στο γράφημά σας, βελτιώνοντας την οπτική αναπαράσταση των δεδομένων σας.

## Συχνές ερωτήσεις

### Πώς μπορώ να αλλάξω την τιμή Gap Width;

 Για να αλλάξετε το Gap Width, χρησιμοποιήστε το`setGapWidth` μέθοδος στο`ParentSeriesGroup`της σειράς γραφημάτων. Στο παρεχόμενο παράδειγμα, ορίσαμε το Gap Width σε 50, αλλά μπορείτε να προσαρμόσετε αυτήν την τιμή στο επιθυμητό διάστημα.

### Μπορώ να προσαρμόσω άλλες ιδιότητες γραφήματος;

Ναι, το Aspose.Slides για Java παρέχει εκτεταμένες δυνατότητες για προσαρμογή γραφημάτων. Μπορείτε να τροποποιήσετε διάφορες ιδιότητες γραφήματος, όπως χρώματα, ετικέτες, τίτλους και άλλα. Ελέγξτε την Αναφορά API για λεπτομερείς πληροφορίες σχετικά με τις επιλογές προσαρμογής γραφήματος.

### Πού μπορώ να βρω περισσότερους πόρους και τεκμηρίωση;

 Μπορείτε να βρείτε ολοκληρωμένη τεκμηρίωση και πρόσθετους πόρους στο Aspose.Slides for Java στο[Aspose website](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
