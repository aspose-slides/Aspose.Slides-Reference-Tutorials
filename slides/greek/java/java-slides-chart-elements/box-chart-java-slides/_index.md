---
"description": "Μάθετε πώς να δημιουργείτε γραφήματα πλαισίων σε παρουσιάσεις Java με το Aspose.Slides. Περιλαμβάνονται αναλυτικοί οδηγοί και πηγαίος κώδικας για αποτελεσματική οπτικοποίηση δεδομένων."
"linktitle": "Γράφημα πλαισίων σε διαφάνειες Java"
"second_title": "Aspose.Slides API επεξεργασίας Java PowerPoint"
"title": "Γράφημα πλαισίων σε διαφάνειες Java"
"url": "/el/java/chart-elements/box-chart-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Γράφημα πλαισίων σε διαφάνειες Java


## Εισαγωγή στο Box Chart στο Aspose.Slides για Java

Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία δημιουργίας ενός γραφήματος πλαισίου χρησιμοποιώντας το Aspose.Slides για Java. Τα γραφήματα πλαισίου είναι χρήσιμα για την οπτικοποίηση στατιστικών δεδομένων με διάφορα τεταρτημόρια και ακραίες τιμές. Θα παρέχουμε οδηγίες βήμα προς βήμα μαζί με τον πηγαίο κώδικα για να σας βοηθήσουμε να ξεκινήσετε.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα εξής:

- Εγκατάσταση και ρύθμιση παραμέτρων του Aspose.Slides για τη βιβλιοθήκη Java.
- Ρύθμιση ενός περιβάλλοντος ανάπτυξης Java.

## Βήμα 1: Αρχικοποίηση της παρουσίασης

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

Σε αυτό το βήμα, αρχικοποιούμε ένα αντικείμενο παρουσίασης χρησιμοποιώντας τη διαδρομή προς ένα υπάρχον αρχείο PowerPoint ("test.pptx" σε αυτό το παράδειγμα).

## Βήμα 2: Δημιουργήστε το γράφημα κουτιών

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
```

Σε αυτό το βήμα, δημιουργούμε ένα σχήμα γραφήματος πλαισίου στην πρώτη διαφάνεια της παρουσίασης. Επίσης, διαγράφουμε τυχόν υπάρχουσες κατηγορίες και σειρές από το γράφημα.

## Βήμα 3: Ορισμός κατηγοριών

```java
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    wb.clear(0);
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 1"));
```

Σε αυτό το βήμα, ορίζουμε τις κατηγορίες για το Γράφημα Πλαισίων. Χρησιμοποιούμε το `IChartDataWorkbook` για να προσθέσετε κατηγορίες και να τις ονομάσετε ανάλογα.

## Βήμα 4: Δημιουργήστε τη σειρά

```java
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
    series.setQuartileMethod(QuartileMethodType.Exclusive);
    series.setShowMeanLine(true);
    series.setShowMeanMarkers(true);
    series.setShowInnerPoints(true);
    series.setShowOutlierPoints(true);
```

Εδώ, δημιουργούμε μια σειρά BoxAndWhisker για το γράφημα και διαμορφώνουμε διάφορες επιλογές όπως η μέθοδος τεταρτημορίων, η μέση γραμμή, οι δείκτες μέσου όρου, τα εσωτερικά σημεία και τα ακραία σημεία.

## Βήμα 5: Προσθήκη σημείων δεδομένων

```java
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
```

Σε αυτό το βήμα, προσθέτουμε σημεία δεδομένων στη σειρά BoxAndWhisker. Αυτά τα σημεία δεδομένων αντιπροσωπεύουν τα στατιστικά δεδομένα για το γράφημα.

## Βήμα 6: Αποθήκευση της παρουσίασης

```java
    pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

Τέλος, αποθηκεύουμε την παρουσίαση με το Γράφημα Πλαισίων σε ένα νέο αρχείο PowerPoint με το όνομα "BoxAndWhisker.pptx".

Συγχαρητήρια! Δημιουργήσατε με επιτυχία ένα γράφημα πλαισίων χρησιμοποιώντας το Aspose.Slides για Java. Μπορείτε να προσαρμόσετε περαιτέρω το γράφημα προσαρμόζοντας διάφορες ιδιότητες και προσθέτοντας περισσότερα σημεία δεδομένων, όπως απαιτείται.

## Πλήρης πηγαίος κώδικας για διάγραμμα πλαισίων σε διαφάνειες Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 1"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
	series.setQuartileMethod(QuartileMethodType.Exclusive);
	series.setShowMeanLine(true);
	series.setShowMeanMarkers(true);
	series.setShowInnerPoints(true);
	series.setShowOutlierPoints(true);
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
	pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Σύναψη

Σε αυτό το σεμινάριο, μάθαμε πώς να δημιουργούμε ένα Γράφημα Πλαισίου χρησιμοποιώντας το Aspose.Slides για Java. Τα Γράφημα Πλαισίου είναι πολύτιμα εργαλεία για την οπτικοποίηση στατιστικών δεδομένων, συμπεριλαμβανομένων των τεταρτημορίων και των ακραίων τιμών. Παρέχουμε έναν οδηγό βήμα προς βήμα μαζί με πηγαίο κώδικα για να σας βοηθήσουμε να ξεκινήσετε τη δημιουργία Γραφημάτων Πλαισίου στις εφαρμογές Java σας.

## Συχνές ερωτήσεις

### Πώς μπορώ να αλλάξω την εμφάνιση του γραφήματος κουτιών;

Μπορείτε να προσαρμόσετε την εμφάνιση του γραφήματος πλαισίου τροποποιώντας ιδιότητες όπως στυλ γραμμών, χρώματα και γραμματοσειρές. Ανατρέξτε στην τεκμηρίωση Aspose.Slides για Java για λεπτομέρειες σχετικά με την προσαρμογή γραφήματος.

### Μπορώ να προσθέσω επιπλέον σειρές δεδομένων στο γράφημα πλαισίων;

Ναι, μπορείτε να προσθέσετε πολλές σειρές δεδομένων στο Γράφημα Πλαισίων δημιουργώντας επιπλέον `IChartSeries` αντικείμενα και προσθήκη σημείων δεδομένων σε αυτά.

### Τι σημαίνει το QuartileMethodType.Exclusive;

Ο `QuartileMethodType.Exclusive` Η ρύθμιση καθορίζει ότι οι υπολογισμοί των τεταρτημορίων θα πρέπει να γίνονται χρησιμοποιώντας την αποκλειστική μέθοδο. Μπορείτε να επιλέξετε διαφορετικές μεθόδους υπολογισμού τεταρτημορίων ανάλογα με τα δεδομένα και τις απαιτήσεις σας.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}