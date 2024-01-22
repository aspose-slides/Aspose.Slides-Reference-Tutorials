---
title: Γράφημα πολλών κατηγοριών σε διαφάνειες Java
linktitle: Γράφημα πολλών κατηγοριών σε διαφάνειες Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Δημιουργήστε γραφήματα πολλών κατηγοριών σε διαφάνειες Java χρησιμοποιώντας το Aspose.Slides για Java. Οδηγός βήμα προς βήμα με πηγαίο κώδικα για εντυπωσιακή οπτικοποίηση δεδομένων σε παρουσιάσεις.
type: docs
weight: 20
url: /el/java/chart-data-manipulation/multi-category-chart-java-slides/
---

## Εισαγωγή στο γράφημα πολλών κατηγοριών σε διαφάνειες Java με Aspose.Slides

Σε αυτό το σεμινάριο, θα μάθουμε πώς να δημιουργήσουμε ένα γράφημα πολλών κατηγοριών σε διαφάνειες Java χρησιμοποιώντας το Aspose.Slides for Java API. Αυτός ο οδηγός θα παρέχει οδηγίες βήμα προς βήμα μαζί με τον πηγαίο κώδικα για να σας βοηθήσει να δημιουργήσετε ένα γράφημα στηλών ομαδοποίησης με πολλές κατηγορίες και σειρές.

## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε εγκαταστήσει και ρυθμίσει τη βιβλιοθήκη Aspose.Slides for Java στο περιβάλλον ανάπτυξης Java.

## Βήμα 1: Ρύθμιση του περιβάλλοντος
Πρώτα, εισαγάγετε τις απαραίτητες κλάσεις και δημιουργήστε ένα νέο αντικείμενο παρουσίασης για να εργαστείτε με διαφάνειες.

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Βήμα 2: Προσθήκη διαφάνειας και γραφήματος
Στη συνέχεια, δημιουργήστε μια διαφάνεια και προσθέστε ένα γράφημα ομαδοποιημένης στήλης σε αυτήν.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
```

## Βήμα 3: Διαγραφή υπαρχόντων δεδομένων
Διαγράψτε τυχόν υπάρχοντα δεδομένα από το γράφημα.

```java
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

## Βήμα 4: Ρύθμιση κατηγοριών δεδομένων
Τώρα, ας ορίσουμε κατηγορίες δεδομένων για το γράφημα. Θα δημιουργήσουμε πολλές κατηγορίες και θα τις ομαδοποιήσουμε.

```java
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);

int defaultWorksheetIndex = 0;

// Προσθέστε κατηγορίες και ομαδοποιήστε τις
IChartCategory category = ch.getChartData().getCategories().add(fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c4", "C"));
category.getGroupingLevels().setGroupingItem(1, "Group2");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c5", "D"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c6", "E"));
category.getGroupingLevels().setGroupingItem(1, "Group3");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c7", "F"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c8", "G"));
category.getGroupingLevels().setGroupingItem(1, "Group4");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c9", "H"));
```

## Βήμα 5: Προσθήκη σειράς
Τώρα, ας προσθέσουμε μια σειρά στο γράφημα μαζί με τα σημεία δεδομένων.

```java
IChartSeries series = ch.getChartData().getSeries().add(fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);

series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D3", 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D4", 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D5", 40));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D6", 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D7", 60));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D8", 70));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D9", 80));
```

## Βήμα 6: Αποθήκευση της παρουσίασης
Τέλος, αποθηκεύστε την παρουσίαση με το γράφημα.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

Αυτό είναι! Δημιουργήσατε επιτυχώς ένα γράφημα πολλών κατηγοριών σε μια διαφάνεια Java χρησιμοποιώντας το Aspose.Slides. Μπορείτε να προσαρμόσετε περαιτέρω αυτό το γράφημα για να ταιριάζει στις συγκεκριμένες απαιτήσεις σας.

## Ολοκληρωμένος πηγαίος κώδικας για γράφημα πολλών κατηγοριών σε διαφάνειες Java

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
IChartCategory category = ch.getChartData().getCategories().add(fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c4", "C"));
category.getGroupingLevels().setGroupingItem(1, "Group2");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c5", "D"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c6", "E"));
category.getGroupingLevels().setGroupingItem(1, "Group3");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c7", "F"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c8", "G"));
category.getGroupingLevels().setGroupingItem(1, "Group4");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c9", "H"));
// Προσθήκη σειράς
IChartSeries series = ch.getChartData().getSeries().add(fact.getCell(0, "D1", "Series 1"),
		ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D3", 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D4", 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D5", 40));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D6", 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D7", 60));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D8", 70));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D9", 80));
// Αποθήκευση παρουσίασης με γράφημα
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## συμπέρασμα

Σε αυτό το σεμινάριο, μάθαμε πώς να δημιουργήσουμε ένα γράφημα πολλών κατηγοριών σε διαφάνειες Java χρησιμοποιώντας το Aspose.Slides for Java API. Ακολουθήσαμε έναν αναλυτικό οδηγό με πηγαίο κώδικα για να δημιουργήσουμε ένα γράφημα στηλών ομαδοποίησης με πολλές κατηγορίες και σειρές.

## Συχνές ερωτήσεις

### Πώς μπορώ να προσαρμόσω την εμφάνιση του γραφήματος;

Μπορείτε να προσαρμόσετε την εμφάνιση του γραφήματος τροποποιώντας ιδιότητες όπως χρώματα, γραμματοσειρές και στυλ. Ανατρέξτε στην τεκμηρίωση Aspose.Slides για λεπτομερείς επιλογές προσαρμογής.

### Μπορώ να προσθέσω περισσότερες σειρές στο γράφημα;

Ναι, μπορείτε να προσθέσετε επιπλέον σειρές στο γράφημα ακολουθώντας μια παρόμοια διαδικασία όπως φαίνεται στο Βήμα 5.

### Πώς μπορώ να αλλάξω τον τύπο του γραφήματος;

 Για να αλλάξετε τον τύπο γραφήματος, αντικαταστήστε`ChartType.ClusteredColumn` με τον επιθυμητό τύπο γραφήματος κατά την προσθήκη του γραφήματος στο Βήμα 2.

### Πώς μπορώ να προσθέσω έναν τίτλο στο γράφημα;

 Μπορείτε να προσθέσετε έναν τίτλο στο γράφημα χρησιμοποιώντας το`ch.getChartTitle().getTextFrame().setText("Chart Title");` μέθοδος.