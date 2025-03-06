---
title: Γράφημα δενδρικού χάρτη σε Java Slides
linktitle: Γράφημα δενδρικού χάρτη σε Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Δημιουργήστε γραφήματα δέντρων χαρτών σε διαφάνειες Java χρησιμοποιώντας το Aspose.Slides για Java. Οδηγός βήμα προς βήμα με πηγαίο κώδικα για την απεικόνιση ιεραρχικών δεδομένων.
weight: 13
url: /el/java/chart-creation/tree-map-chart-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Εισαγωγή στο γράφημα δενδρικού χάρτη σε διαφάνειες Java

Σε αυτό το σεμινάριο, θα δείξουμε πώς να δημιουργήσετε ένα γράφημα δενδρικού χάρτη σε μια παρουσίαση του PowerPoint χρησιμοποιώντας τη βιβλιοθήκη Aspose.Slides for Java. Τα γραφήματα του δέντρου χάρτη είναι ένας αποτελεσματικός τρόπος για την οπτικοποίηση των ιεραρχικών δεδομένων.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε ρυθμίσει τη βιβλιοθήκη Aspose.Slides for Java στο έργο σας Java.

## Βήμα 1: Εισαγάγετε τις απαιτούμενες βιβλιοθήκες

```java
import com.aspose.slides.*;
```

## Βήμα 2: Φορτώστε την παρουσίαση

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Βήμα 3: Δημιουργήστε ένα γράφημα δενδρικού χάρτη

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Treemap, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    wb.clear(0);

    // Δημιουργία κλάδου 1
    IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
    leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
    leaf.getGroupingLevels().setGroupingItem(2, "Branch1");

    chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));

    leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
    leaf.getGroupingLevels().setGroupingItem(1, "Stem2");

    chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));

    // Δημιουργία κλάδου 2
    leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
    leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
    leaf.getGroupingLevels().setGroupingItem(2, "Branch2");

    chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));

    leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
    leaf.getGroupingLevels().setGroupingItem(1, "Stem4");

    chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));

    // Προσθήκη σημείων δεδομένων
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.Treemap);
    series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);

    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D1", 4));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D2", 5));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D3", 3));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D4", 6));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D5", 9));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D6", 9));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D7", 4));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D8", 3));

    series.setParentLabelLayout(ParentLabelLayoutType.Overlapping);

    // Αποθηκεύστε την παρουσίαση με το γράφημα του Χάρτη δέντρου
    pres.save("Treemap.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Πλήρης Πηγαίος Κώδικας για Γράφημα Χάρτη δέντρων σε διαφάνειες Java
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Treemap, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	//κλάδος 1
	IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
	chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));
	//κλάδος 2
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
	chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Treemap);
	series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D1", 4));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D2", 5));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D3", 3));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D4", 6));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D5", 9));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D6", 9));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D7", 4));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D8", 3));
	series.setParentLabelLayout(ParentLabelLayoutType.Overlapping);
	pres.save("Treemap.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## συμπέρασμα

Σε αυτό το σεμινάριο, έχετε μάθει πώς να δημιουργείτε ένα γράφημα δενδρικού χάρτη σε μια παρουσίαση του PowerPoint χρησιμοποιώντας τη βιβλιοθήκη Aspose.Slides for Java. Τα γραφήματα του δενδρικού χάρτη είναι ένα πολύτιμο εργαλείο για την οπτικοποίηση ιεραρχικών δεδομένων, κάνοντας τις παρουσιάσεις σας πιο ενημερωτικές και ελκυστικές.

## Συχνές ερωτήσεις

### Πώς μπορώ να προσθέσω δεδομένα στο γράφημα του Tree Map;

 Για να προσθέσετε δεδομένα στο γράφημα δενδρικού χάρτη, χρησιμοποιήστε το`series.getDataPoints().addDataPointForTreemapSeries()` μέθοδο, μεταβιβάζοντας τις τιμές δεδομένων ως παραμέτρους.

### Πώς μπορώ να προσαρμόσω την εμφάνιση του γραφήματος Tree Map;

 Μπορείτε να προσαρμόσετε την εμφάνιση του γραφήματος Tree Map τροποποιώντας διάφορες ιδιότητες του`chart` και`series`αντικείμενα, όπως χρώματα, ετικέτες και διατάξεις.

### Μπορώ να δημιουργήσω πολλαπλά γραφήματα Tree Map σε μία παρουσίαση;

Ναι, μπορείτε να δημιουργήσετε πολλά γραφήματα δενδρικού χάρτη σε μία παρουσίαση ακολουθώντας τα ίδια βήματα και καθορίζοντας διαφορετικές θέσεις διαφάνειας.

### Πώς μπορώ να αποθηκεύσω την παρουσίαση με το γράφημα του Χάρτη δέντρου;

 Χρησιμοποιήστε το`pres.save()` μέθοδος αποθήκευσης της παρουσίασης με το γράφημα του Δενδρικού Χάρτη στην επιθυμητή μορφή (π.χ. PPTX).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
