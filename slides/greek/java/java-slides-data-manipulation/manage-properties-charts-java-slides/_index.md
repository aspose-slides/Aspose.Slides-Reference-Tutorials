---
"description": "Μάθετε να δημιουργείτε εκπληκτικά γραφήματα και να διαχειρίζεστε ιδιότητες σε διαφάνειες Java με το Aspose.Slides. Οδηγός βήμα προς βήμα με πηγαίο κώδικα για ισχυρές παρουσιάσεις."
"linktitle": "Διαχείριση γραφημάτων ιδιοτήτων σε διαφάνειες Java"
"second_title": "Aspose.Slides API επεξεργασίας Java PowerPoint"
"title": "Διαχείριση γραφημάτων ιδιοτήτων σε διαφάνειες Java"
"url": "/el/java/data-manipulation/manage-properties-charts-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Διαχείριση γραφημάτων ιδιοτήτων σε διαφάνειες Java


## Εισαγωγή στη Διαχείριση Ιδιοτήτων και Γραφημάτων σε Διαφάνειες Java χρησιμοποιώντας το Aspose.Slides

Σε αυτό το σεμινάριο, θα εξερευνήσουμε πώς να διαχειριζόμαστε ιδιότητες και να δημιουργούμε γραφήματα σε διαφάνειες Java χρησιμοποιώντας το Aspose.Slides. Το Aspose.Slides είναι ένα ισχυρό API Java για εργασία με παρουσιάσεις PowerPoint. Θα σας παρουσιάσουμε βήμα προς βήμα τη διαδικασία, συμπεριλαμβανομένων παραδειγμάτων πηγαίου κώδικα.

## Προαπαιτούμενα

Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε εγκαταστήσει και ρυθμίσει στο έργο σας τη βιβλιοθήκη Aspose.Slides για Java. Μπορείτε να την κατεβάσετε από [εδώ](https://releases.aspose.com/slides/java/).

## Προσθήκη γραφήματος σε διαφάνεια

Για να προσθέσετε ένα γράφημα σε μια διαφάνεια, ακολουθήστε τα εξής βήματα:

1. Εισαγάγετε τις απαραίτητες κλάσεις και δημιουργήστε μια παρουσία της κλάσης Presentation.

```java
// Δημιουργήστε μια παρουσία της κλάσης Presentation
Presentation presentation = new Presentation();
```

2. Αποκτήστε πρόσβαση στη διαφάνεια όπου θέλετε να προσθέσετε το γράφημα. Σε αυτό το παράδειγμα, έχουμε πρόσβαση στην πρώτη διαφάνεια.

```java
// Πρόσβαση στην πρώτη διαφάνεια
ISlide slide = presentation.getSlides().get_Item(0);
```

3. Προσθέστε ένα γράφημα με προεπιλεγμένα δεδομένα. Σε αυτήν την περίπτωση, προσθέτουμε ένα γράφημα StackedColumn3D.

```java
// Προσθήκη γραφήματος με προεπιλεγμένα δεδομένα
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
```

## Ρύθμιση δεδομένων γραφήματος

Για να ορίσουμε τα δεδομένα γραφήματος, πρέπει να δημιουργήσουμε ένα βιβλίο εργασίας δεδομένων γραφήματος και να προσθέσουμε σειρές και κατηγορίες. Ακολουθήστε τα παρακάτω βήματα:

4. Ορίστε τον δείκτη του φύλλου δεδομένων του γραφήματος.

```java
// Ρύθμιση του ευρετηρίου του φύλλου δεδομένων γραφήματος
int defaultWorksheetIndex = 0;
```

5. Αποκτήστε το βιβλίο εργασίας δεδομένων γραφήματος.

```java
// Λήψη του φύλλου εργασίας δεδομένων γραφήματος
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

6. Προσθήκη σειράς στο γράφημα. Σε αυτό το παράδειγμα, προσθέτουμε δύο σειρές με το όνομα "Σειρά 1" και "Σειρά 2".

```java
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

7. Προσθέστε κατηγορίες στο γράφημα. Εδώ, προσθέτουμε τρεις κατηγορίες.

```java
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## Ορισμός ιδιοτήτων περιστροφής 3D

Τώρα, ας ορίσουμε τις ιδιότητες περιστροφής 3D για το γράφημα:

8. Ορίστε τους άξονες ορθής γωνίας.

```java
chart.getRotation3D().setRightAngleAxes(true);
```

9. Ορίστε τις γωνίες περιστροφής για τους άξονες X και Y. Σε αυτό το παράδειγμα, περιστρέφουμε τον άξονα X κατά 40 μοίρες και τον άξονα Y κατά 270 μοίρες.

```java
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
```

10. Ορίστε το ποσοστό βάθους σε 150.

```java
chart.getRotation3D().setDepthPercents(150);
```

## Συμπλήρωση δεδομένων σειράς

11. Πάρτε τη δεύτερη σειρά γραφημάτων και συμπληρώστε την με σημεία δεδομένων.

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Συμπλήρωση δεδομένων σειράς
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## Ρύθμιση επικάλυψης

12. Ορίστε την τιμή επικάλυψης για τη σειρά. Για παράδειγμα, μπορείτε να την ορίσετε σε 100 για να μην υπάρχει επικάλυψη.

```java
series.getParentSeriesGroup().setOverlap((byte) 100);
```

## Αποθήκευση της παρουσίασης

Τέλος, αποθηκεύστε την παρουσίαση στο δίσκο.

```java
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

Αυτό ήταν! Δημιουργήσατε με επιτυχία ένα τρισδιάστατο γράφημα σωρευμένων στηλών με προσαρμοσμένες ιδιότητες χρησιμοποιώντας το Aspose.Slides σε Java.

## Πλήρης πηγαίος κώδικας για τη διαχείριση γραφημάτων ιδιοτήτων σε διαφάνειες Java

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
// Δημιουργήστε μια παρουσία της κλάσης Presentation
Presentation presentation = new Presentation();
// Πρόσβαση στην πρώτη διαφάνεια
ISlide slide = presentation.getSlides().get_Item(0);
// Προσθήκη γραφήματος με προεπιλεγμένα δεδομένα
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
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
// Ορισμός ιδιοτήτων Rotation3D
chart.getRotation3D().setRightAngleAxes(true);
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
chart.getRotation3D().setDepthPercents(150);
// Πάρτε τη δεύτερη σειρά γραφημάτων
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// Συμπληρώνονται τώρα τα δεδομένα σειράς
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Ορισμός τιμής επικάλυψης
series.getParentSeriesGroup().setOverlap((byte) 100);
// Εγγραφή παρουσίασης σε δίσκο
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

## Σύναψη

Σε αυτό το σεμινάριο, εμβαθύναμε στον κόσμο της διαχείρισης ιδιοτήτων και της δημιουργίας γραφημάτων σε διαφάνειες Java χρησιμοποιώντας το Aspose.Slides. Το Aspose.Slides είναι ένα ισχυρό API Java που δίνει τη δυνατότητα στους προγραμματιστές να εργάζονται αποτελεσματικά με παρουσιάσεις PowerPoint. Καλύψαμε τα βασικά βήματα και παρέχουμε παραδείγματα πηγαίου κώδικα για να σας καθοδηγήσουμε στη διαδικασία.

## Συχνές ερωτήσεις

### Πώς μπορώ να αλλάξω τον τύπο γραφήματος;

Μπορείτε να αλλάξετε τον τύπο γραφήματος τροποποιώντας το `ChartType` παράμετρος κατά την προσθήκη του γραφήματος. Ανατρέξτε στην τεκμηρίωση του Aspose.Slides για τους διαθέσιμους τύπους γραφημάτων.

### Μπορώ να προσαρμόσω τα χρώματα του γραφήματος;

Ναι, μπορείτε να προσαρμόσετε τα χρώματα του γραφήματος ορίζοντας τις ιδιότητες συμπλήρωσης των σημείων δεδομένων σειράς ή των κατηγοριών.

### Πώς μπορώ να προσθέσω περισσότερα σημεία δεδομένων σε μια σειρά;

Μπορείτε να προσθέσετε περισσότερα σημεία δεδομένων σε μια σειρά χρησιμοποιώντας το `series.getDataPoints().addDataPointForBarSeries()` μέθοδος και καθορίζοντας το κελί που περιέχει την τιμή δεδομένων.

### Πώς μπορώ να ορίσω διαφορετική γωνία περιστροφής;

Για να ορίσετε διαφορετική γωνία περιστροφής για τους άξονες X και Y, χρησιμοποιήστε `chart.getRotation3D().setRotationX()` και `chart.getRotation3D().setRotationY()` με τις επιθυμητές τιμές γωνίας.

### Ποιες άλλες ιδιότητες 3D μπορώ να προσαρμόσω;

Μπορείτε να εξερευνήσετε άλλες τρισδιάστατες ιδιότητες του γραφήματος, όπως το βάθος, την προοπτική και τον φωτισμό, ανατρέχοντας στην τεκμηρίωση του Aspose.Slides.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}