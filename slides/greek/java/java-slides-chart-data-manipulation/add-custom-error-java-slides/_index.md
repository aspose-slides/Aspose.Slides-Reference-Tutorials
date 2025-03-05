---
title: Προσθήκη προσαρμοσμένου σφάλματος στις διαφάνειες Java
linktitle: Προσθήκη προσαρμοσμένου σφάλματος στις διαφάνειες Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Μάθετε πώς να προσθέτετε προσαρμοσμένες γραμμές σφαλμάτων σε γραφήματα PowerPoint σε Διαφάνειες Java χρησιμοποιώντας το Aspose.Slides. Οδηγός βήμα προς βήμα με πηγαίο κώδικα για ακριβή οπτικοποίηση δεδομένων.
type: docs
weight: 11
url: /el/java/chart-data-manipulation/add-custom-error-java-slides/
---

## Εισαγωγή στην προσθήκη προσαρμοσμένων γραμμών σφαλμάτων σε διαφάνειες Java χρησιμοποιώντας το Aspose.Slides

Σε αυτό το σεμινάριο, θα μάθετε πώς να προσθέτετε προσαρμοσμένες γραμμές σφάλματος σε ένα γράφημα σε μια παρουσίαση του PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Οι γραμμές σφαλμάτων είναι χρήσιμες για την εμφάνιση μεταβλητότητας ή αβεβαιότητας σε σημεία δεδομένων σε ένα γράφημα.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα ακόλουθα:

- Η βιβλιοθήκη Aspose.Slides for Java έχει εγκατασταθεί και ρυθμιστεί στο έργο σας.
- Δημιουργήθηκε ένα περιβάλλον ανάπτυξης Java.

## Βήμα 1: Δημιουργήστε μια κενή παρουσίαση

Αρχικά, δημιουργήστε μια κενή παρουσίαση PowerPoint.

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
// Δημιουργία κενής παρουσίασης
Presentation presentation = new Presentation();
```

## Βήμα 2: Προσθέστε ένα γράφημα φυσαλίδων

Στη συνέχεια, θα προσθέσουμε ένα γράφημα φυσαλίδων στην παρουσίαση.

```java
// Δημιουργία γραφήματος φυσαλίδων
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

## Βήμα 3: Προσθέστε προσαρμοσμένες γραμμές σφαλμάτων

Τώρα, ας προσθέσουμε προσαρμοσμένες γραμμές σφαλμάτων στη σειρά γραφημάτων.

```java
// Προσθήκη προσαρμοσμένων γραμμών σφάλματος και ρύθμιση της μορφής τους
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Custom);
errBarY.setValueType(ErrorBarValueType.Custom);
```

## Βήμα 4: Ορίστε δεδομένα γραμμών σφαλμάτων

Σε αυτό το βήμα, θα αποκτήσουμε πρόσβαση στα σημεία δεδομένων της σειράς γραφημάτων και θα ορίσουμε τις προσαρμοσμένες τιμές των γραμμών σφάλματος για κάθε σημείο.

```java
// Πρόσβαση σε σημεία δεδομένων σειράς γραφήματος και ρύθμιση τιμών ράβδων σφάλματος για μεμονωμένα σημεία
IChartDataPointCollection points = series.getDataPoints();
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);

// Ρύθμιση ράβδων σφάλματος για σημεία σειράς γραφήματος
for (int i = 0; i < points.size(); i++)
{
    points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
}
```

## Βήμα 5: Αποθηκεύστε την Παρουσίαση

Τέλος, αποθηκεύστε την παρουσίαση με τις προσαρμοσμένες γραμμές σφαλμάτων.

```java
// Αποθήκευση παρουσίασης
presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
```

Αυτό είναι! Προσθέσατε με επιτυχία προσαρμοσμένες γραμμές σφάλματος σε ένα γράφημα σε μια παρουσίαση του PowerPoint χρησιμοποιώντας το Aspose.Slides για Java.

## Ολοκληρώστε τον πηγαίο κώδικα για την προσθήκη προσαρμοσμένου σφάλματος σε διαφάνειες Java

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
// Δημιουργία κενής παρουσίασης
Presentation presentation = new Presentation();
try
{
	// Δημιουργία γραφήματος φυσαλίδων
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// Προσθήκη προσαρμοσμένων γραμμών σφάλματος και ρύθμιση της μορφής του
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
	IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Custom);
	errBarY.setValueType(ErrorBarValueType.Custom);
	// Πρόσβαση σε σημείο δεδομένων σειράς γραφήματος και ρύθμιση τιμών ράβδων σφάλματος για μεμονωμένο σημείο
	IChartDataPointCollection points = series.getDataPoints();
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);
	// Ρύθμιση ράβδων σφάλματος για σημεία σειράς γραφήματος
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

## συμπέρασμα

Σε αυτό το ολοκληρωμένο σεμινάριο, μάθατε πώς να βελτιώνετε τις παρουσιάσεις σας στο PowerPoint προσθέτοντας προσαρμοσμένες γραμμές σφαλμάτων σε γραφήματα χρησιμοποιώντας το Aspose.Slides για Java. Οι γραμμές σφαλμάτων παρέχουν πολύτιμες πληροφορίες σχετικά με τη μεταβλητότητα και την αβεβαιότητα των δεδομένων, καθιστώντας τα γραφήματα σας πιο ενημερωτικά και οπτικά ελκυστικά.

## Συχνές ερωτήσεις

### Πώς μπορώ να προσαρμόσω την εμφάνιση των γραμμών σφαλμάτων;

 Μπορείτε να προσαρμόσετε την εμφάνιση των γραμμών σφάλματος τροποποιώντας τις ιδιότητες του`IErrorBarsFormat` αντικείμενο, όπως στυλ γραμμής, χρώμα γραμμής και πλάτος γραμμής σφάλματος.

### Μπορώ να προσθέσω γραμμές σφαλμάτων σε άλλους τύπους γραφημάτων;

Ναι, μπορείτε να προσθέσετε γραμμές σφάλματος σε διάφορους τύπους γραφημάτων που υποστηρίζονται από το Aspose.Slides για Java, συμπεριλαμβανομένων των γραμμικών γραφημάτων, των γραμμικών γραφημάτων και των γραφημάτων scatter.

### Πώς μπορώ να ορίσω διαφορετικές τιμές γραμμής σφαλμάτων για κάθε σημείο δεδομένων;

Μπορείτε να κάνετε κύκλο στα σημεία δεδομένων και να ορίσετε προσαρμοσμένες τιμές γραμμής σφαλμάτων για κάθε σημείο, όπως φαίνεται στον παραπάνω κώδικα.

### Είναι δυνατή η απόκρυψη των γραμμών σφαλμάτων για συγκεκριμένα σημεία δεδομένων;

 Ναι, μπορείτε να ελέγξετε την ορατότητα των γραμμών σφάλματος για μεμονωμένα σημεία δεδομένων ορίζοντας το`setVisible` ιδιοκτησία του`IErrorBarsFormat` αντικείμενο.