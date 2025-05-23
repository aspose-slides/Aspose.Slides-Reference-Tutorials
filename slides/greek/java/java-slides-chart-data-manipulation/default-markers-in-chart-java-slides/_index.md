---
"description": "Μάθετε πώς να δημιουργείτε διαφάνειες Java με προεπιλεγμένους δείκτες σε γραφήματα χρησιμοποιώντας το Aspose.Slides για Java. Οδηγός βήμα προς βήμα με πηγαίο κώδικα."
"linktitle": "Προεπιλεγμένοι δείκτες σε γράφημα σε διαφάνειες Java"
"second_title": "Aspose.Slides API επεξεργασίας Java PowerPoint"
"title": "Προεπιλεγμένοι δείκτες σε γράφημα σε διαφάνειες Java"
"url": "/el/java/chart-data-manipulation/default-markers-in-chart-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Προεπιλεγμένοι δείκτες σε γράφημα σε διαφάνειες Java


## Εισαγωγή στους προεπιλεγμένους δείκτες σε διαφάνειες γραφημάτων σε Java

Σε αυτό το σεμινάριο, θα εξερευνήσουμε πώς να δημιουργήσουμε ένα γράφημα με προεπιλεγμένους δείκτες χρησιμοποιώντας το Aspose.Slides για Java. Οι προεπιλεγμένοι δείκτες είναι σύμβολα ή σχήματα που προστίθενται σε σημεία δεδομένων σε ένα γράφημα για να τα επισημάνουμε. Θα δημιουργήσουμε ένα γράφημα γραμμών με δείκτες για την οπτικοποίηση δεδομένων.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε εγκαταστήσει και ρυθμίσει τη βιβλιοθήκη Aspose.Slides για Java στο έργο Java σας.

## Βήμα 1: Δημιουργήστε μια παρουσίαση

Αρχικά, ας δημιουργήσουμε μια παρουσίαση και ας προσθέσουμε μια διαφάνεια σε αυτήν. Στη συνέχεια, θα προσθέσουμε ένα γράφημα στη διαφάνεια.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

## Βήμα 2: Προσθήκη γραφήματος γραμμών με δείκτες

Τώρα, ας προσθέσουμε ένα γράφημα γραμμών με δείκτες στη διαφάνεια. Θα διαγράψουμε επίσης τυχόν προεπιλεγμένα δεδομένα από το γράφημα.

```java
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## Βήμα 3: Συμπλήρωση δεδομένων γραφήματος

Θα συμπληρώσουμε το γράφημα με δείγματα δεδομένων. Σε αυτό το παράδειγμα, θα δημιουργήσουμε δύο σειρές με σημεία δεδομένων και κατηγορίες.

```java
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Σειρά 1
chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"));
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));
chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));

// Σειρά 2
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"));
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// Συμπλήρωση δεδομένων σειράς
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```

## Βήμα 4: Προσαρμόστε το γράφημα

Μπορείτε να προσαρμόσετε περαιτέρω το γράφημα, όπως προσθέτοντας έναν υπόμνημα και προσαρμόζοντας την εμφάνισή του.

```java
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

## Βήμα 5: Αποθήκευση της παρουσίασης

Τέλος, αποθηκεύστε την παρουσίαση με το γράφημα στην επιθυμητή θέση.

```java
pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
```

Αυτό ήταν! Δημιουργήσατε ένα γράφημα γραμμών με προεπιλεγμένους δείκτες χρησιμοποιώντας το Aspose.Slides για Java.

## Πλήρης πηγαίος κώδικας για προεπιλεγμένους δείκτες σε γράφημα σε διαφάνειες Java

```java
        // Η διαδρομή προς τον κατάλογο εγγράφων.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation();
        try
        {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
            chart.getChartData().getSeries().clear();
            chart.getChartData().getCategories().clear();
            IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
            chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
            IChartSeries series = chart.getChartData().getSeries().get_Item(0);
            chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));
            chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));
            chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));
            chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));
            chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"), chart.getType());
            //Πάρτε τη δεύτερη σειρά γραφημάτων
            IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);
            //Συμπληρώνονται τώρα τα δεδομένα σειράς
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
            chart.setLegend(true);
            chart.getLegend().setOverlay(false);
            pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## Σύναψη

Σε αυτό το ολοκληρωμένο σεμινάριο, μάθατε πώς να δημιουργείτε διαφάνειες Java με προεπιλεγμένους δείκτες σε γραφήματα χρησιμοποιώντας το Aspose.Slides για Java. Καλύψαμε ολόκληρη τη διαδικασία, από τη ρύθμιση μιας παρουσίασης έως την προσαρμογή της εμφάνισης του γραφήματος και την αποθήκευση του αποτελέσματος.

## Συχνές ερωτήσεις

### Πώς μπορώ να αλλάξω τα σύμβολα δεικτών;

Μπορείτε να προσαρμόσετε τα σύμβολα δείκτη ορίζοντας το στυλ δείκτη για κάθε σημείο δεδομένων. Χρησιμοποιήστε `IDataPoint.setMarkerStyle()` για να αλλάξετε το σύμβολο του δείκτη.

### Πώς μπορώ να προσαρμόσω τα χρώματα του γραφήματος;

Για να τροποποιήσετε τα χρώματα του γραφήματος, μπορείτε να χρησιμοποιήσετε το `IChartSeriesFormat` και `IShapeFillFormat` διεπαφές για τον ορισμό ιδιοτήτων γεμίσματος και γραμμής.

### Μπορώ να προσθέσω ετικέτες στα σημεία δεδομένων;

Ναι, μπορείτε να προσθέσετε ετικέτες σε σημεία δεδομένων χρησιμοποιώντας το `IDataPoint.getLabel()` μέθοδο και προσαρμόστε τα όπως απαιτείται.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}