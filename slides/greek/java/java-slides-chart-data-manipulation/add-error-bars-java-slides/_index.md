---
"description": "Μάθετε πώς να προσθέτετε γραμμές σφάλματος σε γραφήματα PowerPoint σε Java χρησιμοποιώντας το Aspose.Slides. Οδηγός βήμα προς βήμα με πηγαίο κώδικα για την προσαρμογή των γραμμών σφάλματος."
"linktitle": "Προσθήκη γραμμών σφάλματος σε διαφάνειες Java"
"second_title": "Aspose.Slides API επεξεργασίας Java PowerPoint"
"title": "Προσθήκη γραμμών σφάλματος σε διαφάνειες Java"
"url": "/el/java/chart-data-manipulation/add-error-bars-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Προσθήκη γραμμών σφάλματος σε διαφάνειες Java


## Εισαγωγή στην προσθήκη γραμμών σφάλματος σε διαφάνειες Java χρησιμοποιώντας το Aspose.Slides

Σε αυτό το σεμινάριο, θα δείξουμε πώς να προσθέσετε γραμμές σφάλματος σε ένα γράφημα σε μια διαφάνεια του PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Οι γραμμές σφάλματος παρέχουν πολύτιμες πληροφορίες σχετικά με τη μεταβλητότητα ή την αβεβαιότητα των σημείων δεδομένων σε ένα γράφημα. Θα δημιουργήσουμε ένα γράφημα φυσαλίδων και θα προσθέσουμε γραμμές σφάλματος σε αυτό. Ας ξεκινήσουμε!

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε εγκαταστήσει και ρυθμίσει τη βιβλιοθήκη Aspose.Slides για Java στο έργο Java σας. Μπορείτε να κατεβάσετε τη βιβλιοθήκη από το [Ιστότοπος Aspose](https://downloads.aspose.com/slides/java).

## Βήμα 1: Δημιουργήστε μια κενή παρουσίαση

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
// Δημιουργία κενής παρουσίασης
Presentation presentation = new Presentation();
```

Σε αυτό το βήμα, δημιουργούμε μια κενή παρουσίαση όπου θα προσθέσουμε το γράφημά μας με γραμμές σφάλματος.

## Βήμα 2: Δημιουργήστε ένα γράφημα φυσαλίδων

```java
// Δημιουργία γραφήματος φυσαλίδων
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

Εδώ, δημιουργούμε ένα γράφημα φυσαλίδων και καθορίζουμε τη θέση και τις διαστάσεις του στη διαφάνεια.

## Βήμα 3: Προσθήκη γραμμών σφάλματος και ρύθμιση μορφής

```java
// Προσθήκη γραμμών σφάλματος και ορισμός της μορφής τους
IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Fixed);
errBarX.setValue(0.1f);
errBarY.setValueType(ErrorBarValueType.Percentage);
errBarY.setValue(5);
errBarX.setType(ErrorBarType.Plus);
errBarY.getFormat().getLine().setWidth(2);
errBarX.setEndCap(true);
```

Σε αυτό το βήμα, προσθέτουμε γραμμές σφάλματος στο γράφημα και ορίζουμε τη μορφή τους. Μπορείτε να προσαρμόσετε τις γραμμές σφάλματος αλλάζοντας τιμές, τύπους και άλλες ιδιότητες.

- `errBarX` αντιπροσωπεύει γραμμές σφάλματος κατά μήκος του άξονα Χ.
- `errBarY` αντιπροσωπεύει γραμμές σφάλματος κατά μήκος του άξονα Y.
- Κάνουμε ορατές και τις δύο γραμμές σφάλματος X και Y.
- `setValueType` καθορίζει τον τύπο τιμής για τις γραμμές σφάλματος (π.χ., Σταθερή ή Ποσοστό).
- `setValue` ορίζει την τιμή για τις γραμμές σφάλματος.
- `setType` ορίζει τον τύπο των γραμμών σφάλματος (π.χ., Συν ή Πλην).
- Ορίζουμε το πλάτος των γραμμών της γραμμής σφάλματος χρησιμοποιώντας `getFormat().getLine().setWidth(2)`.
- `setEndCap` Καθορίζει εάν θα συμπεριληφθούν τελικά καπάκια στις γραμμές σφάλματος.

## Βήμα 4: Αποθήκευση της παρουσίασης

```java
// Αποθήκευση παρουσίασης
presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
```

Τέλος, αποθηκεύουμε την παρουσίαση με τις πρόσθετες γραμμές σφάλματος σε μια καθορισμένη τοποθεσία.

Αυτό ήταν! Προσθέσατε με επιτυχία γραμμές σφάλματος σε ένα γράφημα σε μια διαφάνεια του PowerPoint χρησιμοποιώντας το Aspose.Slides για Java.

## Πλήρης πηγαίος κώδικας για γραμμές σφάλματος προσθήκης σε διαφάνειες Java

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
// Δημιουργία κενής παρουσίασης
Presentation presentation = new Presentation();
try
{
	// Δημιουργία γραφήματος φυσαλίδων
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// Προσθήκη γραμμών σφάλματος και ορισμός της μορφής τους
	IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
	IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Fixed);
	errBarX.setValue(0.1f);
	errBarY.setValueType(ErrorBarValueType.Percentage);
	errBarY.setValue(5);
	errBarX.setType(ErrorBarType.Plus);
	errBarY.getFormat().getLine().setWidth(2);
	errBarX.setEndCap(true);
	// Αποθήκευση παρουσίασης
	presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Σύναψη

Σε αυτό το σεμινάριο, εξερευνήσαμε πώς να βελτιώσετε τις παρουσιάσεις σας στο PowerPoint προσθέτοντας γραμμές σφάλματος σε γραφήματα χρησιμοποιώντας το Aspose.Slides για Java. Οι γραμμές σφάλματος παρέχουν πολύτιμες πληροφορίες σχετικά με τη μεταβλητότητα και τις αβεβαιότητες των δεδομένων, καθιστώντας τις παρουσιάσεις σας πιο ενημερωτικές και οπτικά ελκυστικές.

## Συχνές ερωτήσεις

### Πώς μπορώ να προσαρμόσω περαιτέρω την εμφάνιση των γραμμών σφάλματος;

Μπορείτε να προσαρμόσετε τις γραμμές σφάλματος τροποποιώντας τις ιδιότητές τους, όπως το στυλ γραμμής, το χρώμα και το πλάτος, όπως φαίνεται στο Βήμα 3.

### Μπορώ να προσθέσω γραμμές σφάλματος σε διαφορετικούς τύπους γραφημάτων;

Ναι, μπορείτε να προσθέσετε γραμμές σφάλματος σε διάφορους τύπους γραφημάτων που υποστηρίζονται από το Aspose.Slides για Java. Απλώς δημιουργήστε τον επιθυμητό τύπο γραφήματος και ακολουθήστε τα ίδια βήματα προσαρμογής της γραμμής σφάλματος.

### Πώς μπορώ να προσαρμόσω τη θέση και το μέγεθος του γραφήματος στη διαφάνεια;

Μπορείτε να ελέγξετε τη θέση και τις διαστάσεις του γραφήματος προσαρμόζοντας τις παραμέτρους στο `addChart` μέθοδος, όπως φαίνεται στο Βήμα 2.

### Πού μπορώ να βρω περισσότερες πληροφορίες σχετικά με το Aspose.Slides για Java;

Μπορείτε να ανατρέξετε στο [Aspose.Slides για τεκμηρίωση Java](https://reference.aspose.com/slides/java/) για λεπτομερείς πληροφορίες σχετικά με τη χρήση της βιβλιοθήκης.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}