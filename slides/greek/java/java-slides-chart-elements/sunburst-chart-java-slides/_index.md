---
title: Διάγραμμα Sunburst σε Java Slides
linktitle: Διάγραμμα Sunburst σε Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Δημιουργήστε εκπληκτικά γραφήματα Sunburst σε Java Slides με το Aspose.Slides. Μάθετε βήμα προς βήμα τη δημιουργία γραφήματος και τη χειραγώγηση δεδομένων.
weight: 16
url: /el/java/chart-elements/sunburst-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Εισαγωγή στο γράφημα Sunburst σε διαφάνειες Java με Aspose.Slides

Σε αυτό το σεμινάριο, θα μάθετε πώς να δημιουργείτε ένα γράφημα Sunburst σε μια παρουσίαση του PowerPoint χρησιμοποιώντας το Aspose.Slides for Java API. Το διάγραμμα Sunburst είναι ένα ακτινωτό γράφημα που χρησιμοποιείται για την αναπαράσταση ιεραρχικών δεδομένων. Θα παρέχουμε οδηγίες βήμα προς βήμα μαζί με τον πηγαίο κώδικα.

## Προαπαιτούμενα

 Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε εγκαταστήσει και διαμορφώσει τη βιβλιοθήκη Aspose.Slides for Java στο έργο σας Java. Μπορείτε να κατεβάσετε τη βιβλιοθήκη από[εδώ](https://releases.aspose.com/slides/java/).

## Βήμα 1: Εισαγάγετε τις απαιτούμενες βιβλιοθήκες

Αρχικά, εισαγάγετε τις απαραίτητες βιβλιοθήκες για να εργαστείτε με το Aspose.Slides και δημιουργήστε ένα γράφημα Sunburst στην εφαρμογή σας Java.

```java
import com.aspose.slides.*;
```

## Βήμα 2: Αρχικοποιήστε την Παρουσίαση

Εκκινήστε μια παρουσίαση του PowerPoint και καθορίστε τον κατάλογο όπου θα αποθηκευτεί το αρχείο παρουσίασής σας.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Βήμα 3: Δημιουργήστε το Διάγραμμα Sunburst

Δημιουργήστε ένα γράφημα Sunburst σε μια διαφάνεια. Καθορίζουμε τη θέση (Χ, Υ) και τις διαστάσεις (πλάτος, ύψος) του γραφήματος.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
```

## Βήμα 4: Προετοιμάστε δεδομένα γραφήματος

Διαγράψτε τυχόν υπάρχοντα δεδομένα κατηγοριών και σειρών από το γράφημα και δημιουργήστε ένα βιβλίο εργασίας δεδομένων για το γράφημα.

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);
```

## Βήμα 5: Ορισμός ιεραρχίας γραφήματος

Ορίστε την ιεραρχική δομή του γραφήματος Sunburst. Μπορείτε να προσθέσετε κλαδιά, μίσχους και φύλλα ως κατηγορίες.

```java
// Κλάδος 1
IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));

// Κλάδος 2
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
```

## Βήμα 6: Προσθήκη δεδομένων στο γράφημα

Προσθέστε σημεία δεδομένων στη σειρά γραφημάτων Sunburst.

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
```

## Βήμα 7: Αποθηκεύστε την Παρουσίαση

Τέλος, αποθηκεύστε την παρουσίαση με το γράφημα Sunburst.

```java
pres.save("Sunburst.pptx", SaveFormat.Pptx);
```

## Πλήρης πηγαίος κώδικας για το γράφημα Sunburst σε διαφάνειες Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
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
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
	series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
	pres.save("Sunburst.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## συμπέρασμα

Σε αυτό το σεμινάριο, μάθατε πώς να δημιουργείτε ένα γράφημα Sunburst σε μια παρουσίαση του PowerPoint χρησιμοποιώντας το Aspose.Slides for Java API. Έχετε δει πώς να αρχικοποιήσετε την παρουσίαση, να δημιουργήσετε το γράφημα, να ορίσετε την ιεραρχία του γραφήματος, να προσθέσετε σημεία δεδομένων και να αποθηκεύσετε την παρουσίαση. Τώρα μπορείτε να χρησιμοποιήσετε αυτή τη γνώση για να δημιουργήσετε διαδραστικά και ενημερωτικά γραφήματα Sunburst στις εφαρμογές σας Java.

## Συχνές ερωτήσεις

### Πώς μπορώ να προσαρμόσω την εμφάνιση του γραφήματος Sunburst;

Μπορείτε να προσαρμόσετε την εμφάνιση του γραφήματος Sunburst τροποποιώντας ιδιότητες όπως χρώματα, ετικέτες και στυλ. Ανατρέξτε στην τεκμηρίωση Aspose.Slides για λεπτομερείς επιλογές προσαρμογής.

### Μπορώ να προσθέσω περισσότερα σημεία δεδομένων στο γράφημα;

 Ναι, μπορείτε να προσθέσετε περισσότερα σημεία δεδομένων στο γράφημα χρησιμοποιώντας το`series.getDataPoints().addDataPointForSunburstSeries()` μέθοδο για κάθε σημείο δεδομένων που θέλετε να συμπεριλάβετε.

### Πώς μπορώ να προσθέσω συμβουλές εργαλείων στο γράφημα Sunburst;

Για να προσθέσετε συμβουλές εργαλείων στο γράφημα Sunburst, μπορείτε να ρυθμίσετε τη μορφή ετικέτας δεδομένων ώστε να εμφανίζει πρόσθετες πληροφορίες, όπως τιμές ή περιγραφές, όταν τοποθετείτε το δείκτη του ποντικιού πάνω από τμήματα γραφήματος.

### Είναι δυνατή η δημιουργία διαδραστικών γραφημάτων Sunburst με υπερσυνδέσμους;

Ναι, μπορείτε να δημιουργήσετε διαδραστικά γραφήματα Sunburst με υπερσυνδέσμους προσθέτοντας υπερσυνδέσμους σε συγκεκριμένα στοιχεία ή τμήματα γραφήματος. Ανατρέξτε στην τεκμηρίωση Aspose.Slides για λεπτομέρειες σχετικά με την προσθήκη υπερσυνδέσμων.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
