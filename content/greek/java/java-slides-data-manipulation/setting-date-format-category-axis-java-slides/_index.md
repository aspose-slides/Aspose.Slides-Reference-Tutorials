---
title: Ρύθμιση μορφής ημερομηνίας για άξονα κατηγορίας σε διαφάνειες Java
linktitle: Ρύθμιση μορφής ημερομηνίας για άξονα κατηγορίας σε διαφάνειες Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Μάθετε πώς να ορίζετε μια μορφή ημερομηνίας για τον άξονα κατηγορίας σε ένα γράφημα PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Οδηγός βήμα προς βήμα με τον πηγαίο κώδικα.
type: docs
weight: 26
url: /el/java/data-manipulation/setting-date-format-category-axis-java-slides/
---

## Εισαγωγή στη ρύθμιση της μορφής ημερομηνίας για τον άξονα κατηγορίας στις διαφάνειες Java

Σε αυτό το σεμινάριο, θα μάθουμε πώς να ορίζουμε μια μορφή ημερομηνίας για τον άξονα κατηγορίας σε ένα γράφημα PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Το Aspose.Slides for Java είναι μια ισχυρή βιβλιοθήκη που σας επιτρέπει να δημιουργείτε, να χειρίζεστε και να διαχειρίζεστε παρουσιάσεις PowerPoint μέσω προγραμματισμού.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα ακόλουθα:

1.  Aspose.Slides for Java βιβλιοθήκη (μπορείτε να την κατεβάσετε από[εδώ](https://releases.aspose.com/slides/java/).
2. Ρύθμιση περιβάλλοντος ανάπτυξης Java.

## Βήμα 1: Δημιουργήστε μια παρουσίαση PowerPoint

Αρχικά, πρέπει να δημιουργήσουμε μια παρουσίαση PowerPoint όπου θα προσθέσουμε ένα γράφημα. Βεβαιωθείτε ότι έχετε εισαγάγει τις απαραίτητες κλάσεις Aspose.Slides.

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Βήμα 2: Προσθέστε ένα γράφημα στη διαφάνεια

Τώρα, ας προσθέσουμε ένα γράφημα στη διαφάνεια του PowerPoint. Θα χρησιμοποιήσουμε ένα γράφημα περιοχής σε αυτό το παράδειγμα.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
```

## Βήμα 3: Προετοιμάστε δεδομένα γραφήματος

Θα ρυθμίσουμε τα δεδομένα γραφήματος και τις κατηγορίες. Σε αυτό το παράδειγμα, θα χρησιμοποιήσουμε κατηγορίες ημερομηνιών.

```java
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);

chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

// Προσθήκη κατηγοριών ημερομηνιών
chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));

// Προσθήκη σειρών δεδομένων
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));
```

## Βήμα 4: Προσαρμόστε τον Άξονα Κατηγορίας
Τώρα, ας προσαρμόσουμε τον άξονα της κατηγορίας ώστε να εμφανίζει ημερομηνίες σε συγκεκριμένη μορφή (π.χ. εεεε).

```java
chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
```

## Βήμα 5: Αποθηκεύστε την παρουσίαση
Τέλος, αποθηκεύστε την παρουσίαση του PowerPoint.

```java
pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
```

Αυτό είναι! Έχετε ορίσει με επιτυχία μια μορφή ημερομηνίας για τον άξονα κατηγορίας σε ένα γράφημα PowerPoint χρησιμοποιώντας το Aspose.Slides για Java.

## Ολοκληρώστε τον πηγαίο κώδικα για τη ρύθμιση της μορφής ημερομηνίας για τον άξονα κατηγορίας σε διαφάνειες Java

```java
	// Η διαδρομή προς τον κατάλογο εγγράφων.
	String dataDir = "Your Document Directory";
	Presentation pres = new Presentation();
	try
	{
		IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
		IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
		wb.clear(0);
		chart.getChartData().getCategories().clear();
		chart.getChartData().getSeries().clear();
		chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));
		IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));
		chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
		chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
		chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
		pres.save(RunExamples.getOutPath() + "test.pptx", SaveFormat.Pptx);
	}
	finally
	{
		if (pres != null) pres.dispose();
	}
}
public static String convertToOADate(GregorianCalendar date) throws ParseException
{
	double oaDate;
	SimpleDateFormat myFormat = new SimpleDateFormat("dd MM yyyy");
	java.util.Date baseDate = myFormat.parse("30 12 1899");
	Long days = TimeUnit.DAYS.convert(date.getTimeInMillis() - baseDate.getTime(), TimeUnit.MILLISECONDS);
	oaDate = (double) days + ((double) date.get(Calendar.HOUR_OF_DAY) / 24) + ((double) date.get(Calendar.MINUTE) / (60 * 24)) + ((double) date.get(Calendar.SECOND) / (60 * 24 * 60));
	return String.valueOf(oaDate);
```

##Συμπέρασμα

Προσαρμόσατε με επιτυχία τη μορφή ημερομηνίας για τον άξονα κατηγορίας σε ένα γράφημα διαφανειών Java χρησιμοποιώντας το Aspose.Slides για Java. Αυτό σας επιτρέπει να παρουσιάζετε τις τιμές ημερομηνίας στην επιθυμητή μορφή στα γραφήματα σας. Μη διστάσετε να εξερευνήσετε περαιτέρω επιλογές προσαρμογής με βάση τις συγκεκριμένες απαιτήσεις σας.

## Συχνές ερωτήσεις

### Πώς μπορώ να αλλάξω τη μορφή ημερομηνίας για τον άξονα της κατηγορίας;

 Για να αλλάξετε τη μορφή ημερομηνίας για τον άξονα κατηγορίας, χρησιμοποιήστε το`setNumberFormat` μέθοδο στον άξονα της κατηγορίας και παρέχετε το επιθυμητό μοτίβο μορφής ημερομηνίας, όπως "εεεε-ΜΜ-ηη" ή "ΜΜ/εεεε". Φροντίστε να ρυθμίσετε`setNumberFormatLinkedToSource(false)` για να παρακάμψετε την προεπιλεγμένη μορφή.

### Μπορώ να χρησιμοποιήσω διαφορετικές μορφές ημερομηνίας για διαφορετικά γραφήματα στην ίδια παρουσίαση;

Ναι, μπορείτε να ορίσετε διαφορετικές μορφές ημερομηνίας για άξονες κατηγορίας σε διαφορετικά γραφήματα στην ίδια παρουσίαση. Απλώς προσαρμόστε τον άξονα κατηγορίας για κάθε γράφημα όπως απαιτείται.

### Πώς μπορώ να προσθέσω περισσότερα σημεία δεδομένων στο γράφημα;

 Για να προσθέσετε περισσότερα σημεία δεδομένων στο γράφημα, χρησιμοποιήστε το`getDataPoints().addDataPointForLineSeries` μέθοδος στη σειρά δεδομένων και παρέχετε τις τιμές δεδομένων.