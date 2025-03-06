---
title: Τρύπα γραφήματος ντόνατ σε διαφάνειες Java
linktitle: Τρύπα γραφήματος ντόνατ σε διαφάνειες Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Δημιουργήστε γραφήματα ντόνατ με προσαρμοσμένα μεγέθη οπών σε διαφάνειες Java χρησιμοποιώντας το Aspose.Slides για Java. Οδηγός βήμα προς βήμα με πηγαίο κώδικα για προσαρμογή γραφήματος.
weight: 11
url: /el/java/chart-elements/doughnut-chart-hole-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Τρύπα γραφήματος ντόνατ σε διαφάνειες Java


## Εισαγωγή στο γράφημα ντόνατ με τρύπα σε διαφάνειες Java

Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη δημιουργία ενός γραφήματος ντόνατ με μια τρύπα χρησιμοποιώντας το Aspose.Slides για Java. Αυτός ο οδηγός βήμα προς βήμα θα σας καθοδηγήσει στη διαδικασία με παραδείγματα πηγαίου κώδικα.

## Προαπαιτούμενα

 Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε εγκαταστήσει και ρυθμίσει τη βιβλιοθήκη Aspose.Slides for Java στο έργο σας Java. Μπορείτε να το κατεβάσετε από το[Aspose.Slides για τεκμηρίωση Java](https://reference.aspose.com/slides/java/).

## Βήμα 1: Εισαγάγετε τις Απαιτούμενες Βιβλιοθήκες

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Βήμα 2: Αρχικοποιήστε την Παρουσίαση

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";

// Δημιουργήστε μια παρουσία της κλάσης παρουσίασης
Presentation presentation = new Presentation();
```

## Βήμα 3: Δημιουργήστε το γράφημα ντόνατ

```java
try {
    // Δημιουργήστε ένα γράφημα ντόνατ στην πρώτη διαφάνεια
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
    
    // Ορίστε το μέγεθος της τρύπας στο διάγραμμα ντόνατ (σε ποσοστό)
    chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
    
    // Αποθηκεύστε την παρουσίαση στο δίσκο
    presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
} finally {
    // Απορρίψτε το αντικείμενο παρουσίασης
    if (presentation != null) presentation.dispose();
}
```

## Βήμα 4: Εκτελέστε τον Κώδικα

 Εκτελέστε τον κώδικα Java στο IDE ή το πρόγραμμα επεξεργασίας κειμένου για να δημιουργήσετε ένα γράφημα ντόνατ με καθορισμένο μέγεθος τρύπας. Φροντίστε να αντικαταστήσετε`"Your Document Directory"` με την πραγματική διαδρομή όπου θέλετε να αποθηκεύσετε την παρουσίαση.

## Ολοκληρώστε τον πηγαίο κώδικα για την τρύπα γραφήματος ντόνατ σε διαφάνειες Java

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
// Δημιουργήστε μια παρουσία της κλάσης παρουσίασης
Presentation presentation = new Presentation();
try
{
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
	chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
	// Γράψτε την παρουσίαση στο δίσκο
	presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## συμπέρασμα

 Σε αυτό το σεμινάριο, μάθατε πώς να δημιουργείτε ένα γράφημα ντόνατ με μια τρύπα χρησιμοποιώντας το Aspose.Slides για Java. Μπορείτε να προσαρμόσετε το μέγεθος της τρύπας προσαρμόζοντας το`setDoughnutHoleSize` παράμετρος μεθόδου.

## Συχνές ερωτήσεις

### Πώς μπορώ να αλλάξω το χρώμα των τμημάτων του γραφήματος;

 Για να αλλάξετε το χρώμα των τμημάτων του γραφήματος, μπορείτε να χρησιμοποιήσετε το`setDataPointsInLegend` μέθοδος στο`IChart` αντικείμενο και ορίστε το επιθυμητό χρώμα για κάθε σημείο δεδομένων.

### Μπορώ να προσθέσω ετικέτες στα τμήματα του γραφήματος ντόνατ;

 Ναι, μπορείτε να προσθέσετε ετικέτες στα τμήματα του γραφήματος ντόνατ χρησιμοποιώντας το`setDataPointsLabelValue` μέθοδος στο`IChart` αντικείμενο.

### Είναι δυνατόν να προστεθεί ένας τίτλος στο γράφημα;

 Σίγουρα! Μπορείτε να προσθέσετε έναν τίτλο στο γράφημα χρησιμοποιώντας το`setTitle` μέθοδος στο`IChart` αντικείμενο και παρέχοντας το επιθυμητό κείμενο τίτλου.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
