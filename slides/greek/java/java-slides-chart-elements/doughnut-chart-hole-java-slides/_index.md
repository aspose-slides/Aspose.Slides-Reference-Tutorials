---
"description": "Δημιουργήστε γραφήματα ντόνατ με προσαρμοσμένα μεγέθη οπών σε διαφάνειες Java χρησιμοποιώντας το Aspose.Slides για Java. Οδηγός βήμα προς βήμα με πηγαίο κώδικα για προσαρμογή γραφημάτων."
"linktitle": "Τρύπα γραφήματος ντόνατ σε διαφάνειες Java"
"second_title": "Aspose.Slides API επεξεργασίας Java PowerPoint"
"title": "Τρύπα γραφήματος ντόνατ σε διαφάνειες Java"
"url": "/el/java/chart-elements/doughnut-chart-hole-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Τρύπα γραφήματος ντόνατ σε διαφάνειες Java


## Εισαγωγή στο γράφημα ντόνατ με τρύπα στις διαφάνειες Java

Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη δημιουργία ενός γραφήματος ντόνατ με μια τρύπα χρησιμοποιώντας το Aspose.Slides για Java. Αυτός ο οδηγός βήμα προς βήμα θα σας καθοδηγήσει στη διαδικασία με παραδείγματα πηγαίου κώδικα.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε εγκαταστήσει και ρυθμίσει τη βιβλιοθήκη Aspose.Slides για Java στο έργο Java σας. Μπορείτε να την κατεβάσετε από το [Aspose.Slides για τεκμηρίωση Java](https://reference.aspose.com/slides/java/).

## Βήμα 1: Εισαγωγή των απαιτούμενων βιβλιοθηκών

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Βήμα 2: Αρχικοποίηση της παρουσίασης

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";

// Δημιουργήστε μια παρουσία της κλάσης Presentation
Presentation presentation = new Presentation();
```

## Βήμα 3: Δημιουργήστε το γράφημα ντόνατ

```java
try {
    // Δημιουργήστε ένα γράφημα ντόνατ στην πρώτη διαφάνεια
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
    
    // Ορίστε το μέγεθος της τρύπας στο γράφημα ντόνατ (σε ποσοστό)
    chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
    
    // Αποθήκευση της παρουσίασης σε δίσκο
    presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
} finally {
    // Απόρριψη του αντικειμένου παρουσίασης
    if (presentation != null) presentation.dispose();
}
```

## Βήμα 4: Εκτελέστε τον κώδικα

Εκτελέστε τον κώδικα Java στο IDE ή στο πρόγραμμα επεξεργασίας κειμένου για να δημιουργήσετε ένα γράφημα ντόνατ με συγκεκριμένο μέγεθος τρύπας. Βεβαιωθείτε ότι έχετε αντικαταστήσει `"Your Document Directory"` με την πραγματική διαδρομή όπου θέλετε να αποθηκεύσετε την παρουσίαση.

## Πλήρης πηγαίος κώδικας για τρύπα γραφήματος ντόνατ σε διαφάνειες Java

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
// Δημιουργήστε μια παρουσία της κλάσης Presentation
Presentation presentation = new Presentation();
try
{
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
	chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
	// Εγγραφή παρουσίασης σε δίσκο
	presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Σύναψη

Σε αυτό το σεμινάριο, μάθατε πώς να δημιουργήσετε ένα διάγραμμα ντόνατ με μια τρύπα χρησιμοποιώντας το Aspose.Slides για Java. Μπορείτε να προσαρμόσετε το μέγεθος της τρύπας προσαρμόζοντας το `setDoughnutHoleSize` παράμετρος μεθόδου.

## Συχνές ερωτήσεις

### Πώς μπορώ να αλλάξω το χρώμα των τμημάτων του γραφήματος;

Για να αλλάξετε το χρώμα των τμημάτων του γραφήματος, μπορείτε να χρησιμοποιήσετε το `setDataPointsInLegend` μέθοδος στο `IChart` αντικείμενο και ορίστε το επιθυμητό χρώμα για κάθε σημείο δεδομένων.

### Μπορώ να προσθέσω ετικέτες στα τμήματα του γραφήματος ντόνατ;

Ναι, μπορείτε να προσθέσετε ετικέτες στα τμήματα του γραφήματος ντόνατ χρησιμοποιώντας το `setDataPointsLabelValue` μέθοδος στο `IChart` αντικείμενο.

### Είναι δυνατόν να προσθέσω έναν τίτλο στο διάγραμμα;

Σίγουρα! Μπορείτε να προσθέσετε έναν τίτλο στο γράφημα χρησιμοποιώντας το `setTitle` μέθοδος στο `IChart` αντικείμενο και παρέχοντας το επιθυμητό κείμενο τίτλου.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}