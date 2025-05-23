---
"description": "Δημιουργήστε γραφήματα δενδροειδούς χάρτη σε διαφάνειες Java χρησιμοποιώντας το Aspose.Slides για Java. Οδηγός βήμα προς βήμα με πηγαίο κώδικα για την οπτικοποίηση ιεραρχικών δεδομένων."
"linktitle": "Γράφημα χάρτη δέντρων σε διαφάνειες Java"
"second_title": "Aspose.Slides API επεξεργασίας Java PowerPoint"
"title": "Γράφημα χάρτη δέντρων σε διαφάνειες Java"
"url": "/el/java/chart-creation/tree-map-chart-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Γράφημα χάρτη δέντρων σε διαφάνειες Java


## Εισαγωγή στο διάγραμμα χάρτη δέντρων σε διαφάνειες Java

Σε αυτό το σεμινάριο, θα δείξουμε πώς να δημιουργήσετε ένα γράφημα Χάρτη Δέντρου σε μια παρουσίαση PowerPoint χρησιμοποιώντας τη βιβλιοθήκη Aspose.Slides για Java. Τα γραφήματα Χάρτη Δέντρου είναι ένας αποτελεσματικός τρόπος για την οπτικοποίηση ιεραρχικών δεδομένων.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε ρυθμίσει τη βιβλιοθήκη Aspose.Slides για Java στο έργο Java σας.

## Βήμα 1: Εισαγωγή απαιτούμενων βιβλιοθηκών

```java
import com.aspose.slides.*;
```

## Βήμα 2: Φόρτωση της παρουσίασης

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Βήμα 3: Δημιουργήστε ένα διάγραμμα χάρτη δέντρων

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Treemap, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    wb.clear(0);

    // Δημιουργία υποκαταστήματος 1
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

    // Αποθήκευση της παρουσίασης με το γράφημα "Χάρτης δέντρου"
    pres.save("Treemap.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Πλήρης πηγαίος κώδικας για διάγραμμα χάρτη δέντρων σε διαφάνειες Java
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
	//υποκατάστημα 1
	IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
	chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));
	//υποκατάστημα 2
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

## Σύναψη

Σε αυτό το σεμινάριο, μάθατε πώς να δημιουργήσετε ένα γράφημα Χάρτη Δέντρων σε μια παρουσίαση PowerPoint χρησιμοποιώντας τη βιβλιοθήκη Aspose.Slides για Java. Τα γραφήματα Χάρτη Δέντρων είναι ένα πολύτιμο εργαλείο για την οπτικοποίηση ιεραρχικών δεδομένων, καθιστώντας τις παρουσιάσεις σας πιο ενημερωτικές και ελκυστικές.

## Συχνές ερωτήσεις

### Πώς μπορώ να προσθέσω δεδομένα στο γράφημα "Χάρτης δέντρου";

Για να προσθέσετε δεδομένα στο γράφημα Χάρτης δέντρου, χρησιμοποιήστε το `series.getDataPoints().addDataPointForTreemapSeries()` μέθοδος, περνώντας τις τιμές δεδομένων ως παραμέτρους.

### Πώς μπορώ να προσαρμόσω την εμφάνιση του γραφήματος "Χάρτης δέντρου";

Μπορείτε να προσαρμόσετε την εμφάνιση του γραφήματος "Χάρτης δέντρου" τροποποιώντας διάφορες ιδιότητες του `chart` και `series` αντικείμενα, όπως χρώματα, ετικέτες και διατάξεις.

### Μπορώ να δημιουργήσω πολλά γραφήματα Χάρτη Δέντρων σε μία μόνο παρουσίαση;

Ναι, μπορείτε να δημιουργήσετε πολλά γραφήματα Χάρτη Δέντρων σε μία μόνο παρουσίαση ακολουθώντας τα ίδια βήματα και καθορίζοντας διαφορετικές θέσεις διαφανειών.

### Πώς μπορώ να αποθηκεύσω την παρουσίαση με το γράφημα "Χάρτης δέντρου";

Χρησιμοποιήστε το `pres.save()` μέθοδος για να αποθηκεύσετε την παρουσίαση με το διάγραμμα Δενδρικού Χάρτη στην επιθυμητή μορφή (π.χ., PPTX).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}