---
"description": "Μάθετε πώς να προσθέτετε προσαρμοσμένες γραμμές σφάλματος σε γραφήματα PowerPoint σε Java Slides χρησιμοποιώντας το Aspose.Slides. Οδηγός βήμα προς βήμα με πηγαίο κώδικα για ακριβή οπτικοποίηση δεδομένων."
"linktitle": "Προσθήκη προσαρμοσμένου σφάλματος σε διαφάνειες Java"
"second_title": "Aspose.Slides API επεξεργασίας Java PowerPoint"
"title": "Προσθήκη προσαρμοσμένου σφάλματος σε διαφάνειες Java"
"url": "/el/java/chart-data-manipulation/add-custom-error-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Προσθήκη προσαρμοσμένου σφάλματος σε διαφάνειες Java


## Εισαγωγή στην προσθήκη προσαρμοσμένων γραμμών σφάλματος σε διαφάνειες Java χρησιμοποιώντας το Aspose.Slides

Σε αυτό το σεμινάριο, θα μάθετε πώς να προσθέτετε προσαρμοσμένες γραμμές σφάλματος σε ένα γράφημα σε μια παρουσίαση PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Οι γραμμές σφάλματος είναι χρήσιμες για την εμφάνιση μεταβλητότητας ή αβεβαιότητας σε σημεία δεδομένων σε ένα γράφημα.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα εξής:

- Η βιβλιοθήκη Aspose.Slides για Java εγκαταστάθηκε και διαμορφώθηκε στο έργο σας.
- Ρύθμιση ενός περιβάλλοντος ανάπτυξης Java.

## Βήμα 1: Δημιουργήστε μια κενή παρουσίαση

Αρχικά, δημιουργήστε μια κενή παρουσίαση PowerPoint.

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
// Δημιουργία κενής παρουσίασης
Presentation presentation = new Presentation();
```

## Βήμα 2: Προσθήκη γραφήματος φυσαλίδων

Στη συνέχεια, θα προσθέσουμε ένα γράφημα φυσαλίδων στην παρουσίαση.

```java
// Δημιουργία γραφήματος φυσαλίδων
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

## Βήμα 3: Προσθήκη προσαρμοσμένων γραμμών σφάλματος

Τώρα, ας προσθέσουμε προσαρμοσμένες γραμμές σφάλματος στη σειρά γραφημάτων.

```java
// Προσθήκη προσαρμοσμένων γραμμών σφάλματος και ορισμός της μορφής τους
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Custom);
errBarY.setValueType(ErrorBarValueType.Custom);
```

## Βήμα 4: Ορισμός δεδομένων γραμμών σφάλματος

Σε αυτό το βήμα, θα έχουμε πρόσβαση στα σημεία δεδομένων της σειράς γραφημάτων και θα ορίσουμε τις τιμές των προσαρμοσμένων γραμμών σφάλματος για κάθε σημείο.

```java
// Πρόσβαση σε σημεία δεδομένων σειράς γραφημάτων και ορισμός τιμών γραμμών σφάλματος για μεμονωμένα σημεία
IChartDataPointCollection points = series.getDataPoints();
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);

// Ορισμός γραμμών σφάλματος για σημεία σειράς γραφήματος
for (int i = 0; i < points.size(); i++)
{
    points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
}
```

## Βήμα 5: Αποθήκευση της παρουσίασης

Τέλος, αποθηκεύστε την παρουσίαση με τις προσαρμοσμένες γραμμές σφάλματος.

```java
// Αποθήκευση παρουσίασης
presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
```

Αυτό ήταν! Προσθέσατε με επιτυχία προσαρμοσμένες γραμμές σφάλματος σε ένα γράφημα σε μια παρουσίαση PowerPoint χρησιμοποιώντας το Aspose.Slides για Java.

## Πλήρης πηγαίος κώδικας για σφάλμα προσθήκης προσαρμοσμένου σε διαφάνειες Java

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
// Δημιουργία κενής παρουσίασης
Presentation presentation = new Presentation();
try
{
	// Δημιουργία γραφήματος φυσαλίδων
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// Προσθήκη προσαρμοσμένων γραμμών σφάλματος και ορισμός της μορφής τους
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
	IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Custom);
	errBarY.setValueType(ErrorBarValueType.Custom);
	// Πρόσβαση σε δεδομένα σειρών γραφημάτων και ορισμός τιμών γραμμών σφάλματος για μεμονωμένο σημείο
	IChartDataPointCollection points = series.getDataPoints();
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);
	// Ορισμός γραμμών σφάλματος για σημεία σειράς γραφήματος
	for (int i = 0; i < points.size(); i++)
	{
		points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
	}
	// Αποθήκευση παρουσίασης
	presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Σύναψη

Σε αυτό το ολοκληρωμένο σεμινάριο, μάθατε πώς να βελτιώσετε τις παρουσιάσεις σας στο PowerPoint προσθέτοντας προσαρμοσμένες γραμμές σφάλματος σε γραφήματα χρησιμοποιώντας το Aspose.Slides για Java. Οι γραμμές σφάλματος παρέχουν πολύτιμες πληροφορίες σχετικά με τη μεταβλητότητα και την αβεβαιότητα των δεδομένων, καθιστώντας τα γραφήματά σας πιο ενημερωτικά και οπτικά ελκυστικά.

## Συχνές ερωτήσεις

### Πώς μπορώ να προσαρμόσω την εμφάνιση των γραμμών σφάλματος;

Μπορείτε να προσαρμόσετε την εμφάνιση των γραμμών σφάλματος τροποποιώντας τις ιδιότητες του `IErrorBarsFormat` αντικείμενο, όπως στυλ γραμμής, χρώμα γραμμής και πλάτος γραμμής σφάλματος.

### Μπορώ να προσθέσω γραμμές σφάλματος σε άλλους τύπους γραφημάτων;

Ναι, μπορείτε να προσθέσετε γραμμές σφάλματος σε διάφορους τύπους γραφημάτων που υποστηρίζονται από το Aspose.Slides για Java, συμπεριλαμβανομένων γραφημάτων ράβδων, γραφημάτων γραμμών και γραφημάτων διασποράς.

### Πώς μπορώ να ορίσω διαφορετικές τιμές γραμμής σφάλματος για κάθε σημείο δεδομένων;

Μπορείτε να κάνετε επανάληψη στα σημεία δεδομένων και να ορίσετε προσαρμοσμένες τιμές γραμμής σφάλματος για κάθε σημείο, όπως φαίνεται στον παραπάνω κώδικα.

### Είναι δυνατή η απόκρυψη γραμμών σφάλματος για συγκεκριμένα σημεία δεδομένων;

Ναι, μπορείτε να ελέγξετε την ορατότητα των γραμμών σφάλματος για μεμονωμένα σημεία δεδομένων ορίζοντας το `setVisible` ιδιοκτησία του `IErrorBarsFormat` αντικείμενο.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}