---
"description": "Μάθετε πώς να ορίζετε χρώματα αντιστροφής γεμίσματος για γραφήματα Java Slides χρησιμοποιώντας το Aspose.Slides. Βελτιώστε τις απεικονίσεις των γραφημάτων σας με αυτόν τον οδηγό βήμα προς βήμα και τον πηγαίο κώδικα."
"linktitle": "Ορισμός γραφήματος χρωμάτων αντιστροφής γεμίσματος σε διαφάνειες Java"
"second_title": "Aspose.Slides API επεξεργασίας Java PowerPoint"
"title": "Ορισμός γραφήματος χρωμάτων αντιστροφής γεμίσματος σε διαφάνειες Java"
"url": "/el/java/data-manipulation/set-invert-fill-color-chart-java-slides/"
"weight": 22
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ορισμός γραφήματος χρωμάτων αντιστροφής γεμίσματος σε διαφάνειες Java


## Εισαγωγή στο γράφημα χρωμάτων ορισμού αντιστροφής γεμίσματος σε διαφάνειες Java

Σε αυτό το σεμινάριο, θα δείξουμε πώς να ορίσετε το χρώμα αντιστροφής γεμίσματος για ένα γράφημα σε Java Slides χρησιμοποιώντας το Aspose.Slides για Java. Η αντιστροφή του χρώματος γεμίσματος είναι μια χρήσιμη λειτουργία όταν θέλετε να επισημάνετε αρνητικές τιμές σε ένα γράφημα με ένα συγκεκριμένο χρώμα. Θα παρέχουμε οδηγίες βήμα προς βήμα και πηγαίο κώδικα για να το πετύχετε αυτό.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

1. Εγκατεστημένο Aspose.Slides για βιβλιοθήκη Java.
2. Ρύθμιση περιβάλλοντος ανάπτυξης Java.

## Βήμα 1: Δημιουργήστε μια παρουσίαση

Αρχικά, πρέπει να δημιουργήσουμε μια παρουσίαση για να προσθέσουμε το γράφημά μας. Μπορείτε να χρησιμοποιήσετε τον ακόλουθο κώδικα για να δημιουργήσετε μια παρουσίαση:

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Βήμα 2: Προσθήκη γραφήματος

Στη συνέχεια, θα προσθέσουμε ένα γράφημα ομαδοποιημένων στηλών στην παρουσίαση. Δείτε πώς μπορείτε να το κάνετε:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
```

## Βήμα 3: Ρύθμιση δεδομένων γραφήματος

Τώρα, ας ρυθμίσουμε τα δεδομένα του γραφήματος, συμπεριλαμβανομένων των σειρών και των κατηγοριών:

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Προσθήκη νέων σειρών και κατηγοριών
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
```

## Βήμα 4: Συμπλήρωση δεδομένων σειράς

Τώρα, ας συμπληρώσουμε τα δεδομένα σειράς για το γράφημα:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
```

## Βήμα 5: Ορισμός χρώματος αντιστροφής γεμίσματος

Για να ορίσετε το χρώμα γεμίσματος αντιστροφής για τη σειρά γραφημάτων, μπορείτε να χρησιμοποιήσετε τον ακόλουθο κώδικα:

```java
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
```

Στον παραπάνω κώδικα, ορίζουμε τη σειρά ώστε να αντιστρέφει το χρώμα γεμίσματος για αρνητικές τιμές και καθορίζουμε το χρώμα για το ανεστραμμένο γέμισμα.

## Βήμα 6: Αποθήκευση της παρουσίασης

Τέλος, αποθηκεύστε την παρουσίαση με το γράφημα:

```java
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
```

## Πλήρης πηγαίος κώδικας για το γράφημα χρωμάτων αντιστροφής γεμίσματος σε διαφάνειες Java

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
Color inverColor = Color.RED;
Presentation pres = new Presentation();
try
{
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Προσθήκη νέων σειρών και κατηγοριών
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
// Πάρτε την πρώτη σειρά γραφημάτων και συμπληρώστε τα δεδομένα σειράς.
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
}
finally
{
if (pres != null) pres.dispose();
}
```

## Σύναψη

Σε αυτό το σεμινάριο, σας δείξαμε πώς να ορίσετε το χρώμα αντιστροφής γεμίσματος για ένα γράφημα σε Java Slides χρησιμοποιώντας το Aspose.Slides για Java. Αυτή η λειτουργία σάς επιτρέπει να επισημάνετε αρνητικές τιμές στα γραφήματά σας με ένα συγκεκριμένο χρώμα, καθιστώντας τα δεδομένα σας πιο οπτικά κατατοπιστικά.

## Συχνές ερωτήσεις

Σε αυτήν την ενότητα, θα εξετάσουμε ορισμένες συνήθεις ερωτήσεις σχετικά με τον ορισμό του χρώματος αντιστροφής γεμίσματος για ένα γράφημα σε Java Slides χρησιμοποιώντας το Aspose.Slides για Java.

### Πώς μπορώ να εγκαταστήσω το Aspose.Slides για Java;

Μπορείτε να εγκαταστήσετε το Aspose.Slides για Java συμπεριλαμβάνοντας τα αρχεία JAR του Aspose.Slides στο έργο Java σας. Μπορείτε να κατεβάσετε τη βιβλιοθήκη από το [Σελίδα λήψης του Aspose.Slides για Java](https://releases.aspose.com/slides/java/)Ακολουθήστε τις οδηγίες εγκατάστασης που παρέχονται στην τεκμηρίωση για το συγκεκριμένο περιβάλλον ανάπτυξης που χρησιμοποιείτε.

### Μπορώ να προσαρμόσω το χρώμα για ανεστραμμένο γέμισμα στη σειρά γραφημάτων;

Ναι, μπορείτε να προσαρμόσετε το χρώμα για το ανεστραμμένο γέμισμα στη σειρά γραφημάτων. Στο παρεχόμενο παράδειγμα κώδικα, το `series.getInvertedSolidFillColor().setColor(Color.RED)` Η γραμμή ορίζει το χρώμα σε κόκκινο για το ανεστραμμένο γέμισμα. Μπορείτε να αντικαταστήσετε `Color.RED` με οποιοδήποτε άλλο χρώμα της επιλογής σας.

### Πώς μπορώ να τροποποιήσω τον τύπο γραφήματος στο Aspose.Slides για Java;

Μπορείτε να τροποποιήσετε τον τύπο γραφήματος αλλάζοντας το `ChartType` παράμετρο κατά την προσθήκη ενός γραφήματος στην παρουσίαση. Στο παράδειγμα κώδικα, χρησιμοποιήσαμε `ChartType.ClusteredColumn`Μπορείτε να εξερευνήσετε άλλους τύπους γραφημάτων, όπως γραφήματα γραμμών, γραφήματα ράβδων, γραφήματα πίτας κ.λπ., καθορίζοντας το κατάλληλο `ChartType` τιμή απαρίθμησης.

### Πώς μπορώ να προσθέσω πολλές σειρές δεδομένων σε ένα γράφημα;

Για να προσθέσετε πολλές σειρές δεδομένων σε ένα γράφημα, μπορείτε να χρησιμοποιήσετε το `chart.getChartData().getSeries().add(...)` μέθοδο για κάθε σειρά που θέλετε να προσθέσετε. Βεβαιωθείτε ότι έχετε παράσχει τα κατάλληλα σημεία δεδομένων και ετικέτες για κάθε σειρά, ώστε να συμπληρώσετε το γράφημά σας με πολλαπλές σειρές.

### Υπάρχει τρόπος να προσαρμόσω άλλες πτυχές της εμφάνισης του γραφήματος;

Ναι, μπορείτε να προσαρμόσετε διάφορες πτυχές της εμφάνισης του γραφήματος, όπως ετικέτες αξόνων, τίτλους, υπομνήματα και άλλα, χρησιμοποιώντας το Aspose.Slides για Java. Ανατρέξτε στην τεκμηρίωση για λεπτομερείς οδηγίες σχετικά με την προσαρμογή των στοιχείων και της εμφάνισης του γραφήματος.

### Μπορώ να αποθηκεύσω το γράφημα σε διαφορετικές μορφές;

Ναι, μπορείτε να αποθηκεύσετε το γράφημα σε διαφορετικές μορφές χρησιμοποιώντας το Aspose.Slides για Java. Στο παράδειγμα κώδικα που παρέχεται, αποθηκεύσαμε την παρουσίαση ως αρχείο PPTX. Μπορείτε να χρησιμοποιήσετε διαφορετικές μορφές `SaveFormat` επιλογές για να το αποθηκεύσετε σε άλλες μορφές όπως PDF, PNG ή SVG, ανάλογα με τις απαιτήσεις σας.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}