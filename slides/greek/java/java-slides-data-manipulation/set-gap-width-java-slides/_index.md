---
"description": "Μάθετε πώς να ορίζετε το πλάτος κενού σε διαφάνειες Java με το Aspose.Slides για Java. Βελτιώστε τα γραφήματα για τις παρουσιάσεις PowerPoint."
"linktitle": "Ορισμός πλάτους κενού σε διαφάνειες Java"
"second_title": "Aspose.Slides API επεξεργασίας Java PowerPoint"
"title": "Ορισμός πλάτους κενού σε διαφάνειες Java"
"url": "/el/java/data-manipulation/set-gap-width-java-slides/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ορισμός πλάτους κενού σε διαφάνειες Java


## Εισαγωγή στον ορισμό πλάτους κενού στο Aspose.Slides για Java

Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία ορισμού του πλάτους κενού για ένα γράφημα σε μια παρουσίαση PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Το πλάτος κενού καθορίζει την απόσταση μεταξύ των στηλών ή των γραμμών σε ένα γράφημα, επιτρέποντάς σας να ελέγχετε την οπτική εμφάνιση του γραφήματος.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε εγκαταστήσει τη βιβλιοθήκη Aspose.Slides για Java. Μπορείτε να την κατεβάσετε από τον ιστότοπο της Aspose. [εδώ](https://releases.aspose.com/slides/java/).

## Οδηγός βήμα προς βήμα

Ακολουθήστε αυτά τα βήματα για να ορίσετε το πλάτος κενού σε ένα γράφημα χρησιμοποιώντας το Aspose.Slides για Java:

### 1. Δημιουργήστε μια κενή παρουσίαση

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";

// Δημιουργία μιας κενής παρουσίασης 
Presentation presentation = new Presentation();
```

### 2. Πρόσβαση στην πρώτη διαφάνεια

```java
// Πρόσβαση στην πρώτη διαφάνεια
ISlide slide = presentation.getSlides().get_Item(0);
```

### 3. Προσθήκη γραφήματος με προεπιλεγμένα δεδομένα

```java
// Προσθήκη γραφήματος με προεπιλεγμένα δεδομένα
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
```

### 4. Ορίστε τον Δείκτη του Φύλλου Δεδομένων Γραφήματος

```java
// Ρύθμιση του ευρετηρίου του φύλλου δεδομένων γραφήματος
int defaultWorksheetIndex = 0;
```

### 5. Αποκτήστε το Βιβλίο Εργασίας Δεδομένων Γραφήματος

```java
// Λήψη του φύλλου εργασίας δεδομένων γραφήματος
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

### 6. Προσθήκη Σειράς στο Διάγραμμα

```java
// Προσθήκη σειράς στο γράφημα
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

### 7. Προσθήκη κατηγοριών στο γράφημα

```java
// Προσθήκη κατηγοριών στο γράφημα
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

### 8. Συμπλήρωση δεδομένων σειράς

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

### 9. Ορίστε το πλάτος του κενού

```java
// Ορίστε την τιμή Πλάτος κενού
series.getParentSeriesGroup().setGapWidth(50);
```

### 10. Αποθήκευση της παρουσίασης

```java
// Αποθήκευση της παρουσίασης με το γράφημα
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## Πλήρης πηγαίος κώδικας για το σύνολο πλάτους κενού σε διαφάνειες Java

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
// Προσθήκη κατηγοριών
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Πάρτε τη δεύτερη σειρά γραφημάτων
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// Συμπληρώνονται τώρα τα δεδομένα σειράς
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Ορισμός τιμής GapWidth
series.getParentSeriesGroup().setGapWidth(50);
// Αποθήκευση παρουσίασης με γράφημα
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## Σύναψη

Σε αυτό το σεμινάριο, μάθατε πώς να ορίσετε το πλάτος κενού για ένα γράφημα σε μια παρουσίαση PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Η ρύθμιση του πλάτους κενού σάς επιτρέπει να ελέγχετε την απόσταση μεταξύ στηλών ή γραμμών στο γράφημά σας, βελτιώνοντας την οπτική αναπαράσταση των δεδομένων σας.

## Συχνές ερωτήσεις

### Πώς μπορώ να αλλάξω την τιμή του πλάτους κενού;

Για να αλλάξετε το πλάτος του κενού, χρησιμοποιήστε το `setGapWidth` μέθοδος στο `ParentSeriesGroup` της σειράς γραφημάτων. Στο παράδειγμα που παρέχεται, ορίσαμε το πλάτος κενού σε 50, αλλά μπορείτε να προσαρμόσετε αυτήν την τιμή στην επιθυμητή απόσταση.

### Μπορώ να προσαρμόσω άλλες ιδιότητες γραφήματος;

Ναι, το Aspose.Slides για Java παρέχει εκτεταμένες δυνατότητες για προσαρμογή γραφημάτων. Μπορείτε να τροποποιήσετε διάφορες ιδιότητες γραφήματος, όπως χρώματα, ετικέτες, τίτλους και άλλα. Ελέγξτε την Αναφορά API για λεπτομερείς πληροφορίες σχετικά με τις επιλογές προσαρμογής γραφημάτων.

### Πού μπορώ να βρω περισσότερους πόρους και τεκμηρίωση;

Μπορείτε να βρείτε ολοκληρωμένη τεκμηρίωση και πρόσθετους πόρους στο Aspose.Slides για Java στο [Ιστότοπος Aspose](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}