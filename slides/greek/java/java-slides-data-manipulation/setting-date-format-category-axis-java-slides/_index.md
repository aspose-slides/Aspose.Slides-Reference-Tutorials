---
"description": "Μάθετε πώς να ορίσετε μια μορφή ημερομηνίας για τον άξονα κατηγορίας σε ένα γράφημα PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Οδηγός βήμα προς βήμα με πηγαίο κώδικα."
"linktitle": "Ορισμός μορφής ημερομηνίας για τον άξονα κατηγορίας σε διαφάνειες Java"
"second_title": "Aspose.Slides API επεξεργασίας Java PowerPoint"
"title": "Ορισμός μορφής ημερομηνίας για τον άξονα κατηγορίας σε διαφάνειες Java"
"url": "/el/java/data-manipulation/setting-date-format-category-axis-java-slides/"
"weight": 26
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ορισμός μορφής ημερομηνίας για τον άξονα κατηγορίας σε διαφάνειες Java


## Εισαγωγή στον ορισμό μορφής ημερομηνίας για άξονα κατηγορίας σε διαφάνειες Java

Σε αυτό το σεμινάριο, θα μάθουμε πώς να ορίσουμε μια μορφή ημερομηνίας για τον άξονα κατηγοριών σε ένα γράφημα PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Το Aspose.Slides για Java είναι μια ισχυρή βιβλιοθήκη που σας επιτρέπει να δημιουργείτε, να χειρίζεστε και να διαχειρίζεστε παρουσιάσεις PowerPoint μέσω προγραμματισμού.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα εξής:

1. Aspose.Slides για τη βιβλιοθήκη Java (μπορείτε να το κατεβάσετε από [εδώ](https://releases.aspose.com/slides/java/).
2. Ρύθμιση περιβάλλοντος ανάπτυξης Java.

## Βήμα 1: Δημιουργήστε μια παρουσίαση PowerPoint

Αρχικά, πρέπει να δημιουργήσουμε μια παρουσίαση PowerPoint όπου θα προσθέσουμε ένα γράφημα. Βεβαιωθείτε ότι έχετε εισαγάγει τις απαραίτητες κλάσεις Aspose.Slides.

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Βήμα 2: Προσθήκη γραφήματος στη διαφάνεια

Τώρα, ας προσθέσουμε ένα γράφημα στη διαφάνεια του PowerPoint. Σε αυτό το παράδειγμα θα χρησιμοποιήσουμε ένα γράφημα περιοχής.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
```

## Βήμα 3: Προετοιμασία δεδομένων γραφήματος

Θα ρυθμίσουμε τα δεδομένα και τις κατηγορίες του γραφήματος. Σε αυτό το παράδειγμα, θα χρησιμοποιήσουμε κατηγορίες ημερομηνιών.

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

## Βήμα 4: Προσαρμογή άξονα κατηγορίας
Τώρα, ας προσαρμόσουμε τον άξονα κατηγοριών ώστε να εμφανίζει ημερομηνίες σε συγκεκριμένη μορφή (π.χ., εεεε).

```java
chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
```

## Βήμα 5: Αποθήκευση της παρουσίασης
Τέλος, αποθηκεύστε την παρουσίαση του PowerPoint.

```java
pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
```

Αυτό ήταν! Ορίσατε με επιτυχία μια μορφή ημερομηνίας για τον άξονα κατηγορίας σε ένα γράφημα PowerPoint χρησιμοποιώντας το Aspose.Slides για Java.

## Πλήρης πηγαίος κώδικας για τον ορισμό μορφής ημερομηνίας για τον άξονα κατηγορίας σε διαφάνειες Java

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
		pres.save("Your Output Directory" + "test.pptx", SaveFormat.Pptx);
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

##Σύναψη

Έχετε προσαρμόσει με επιτυχία τη μορφή ημερομηνίας για τον άξονα κατηγορίας σε ένα γράφημα Java Slides χρησιμοποιώντας το Aspose.Slides για Java. Αυτό σας επιτρέπει να παρουσιάζετε τιμές ημερομηνίας στην επιθυμητή μορφή στα γραφήματά σας. Μη διστάσετε να εξερευνήσετε περαιτέρω επιλογές προσαρμογής με βάση τις συγκεκριμένες απαιτήσεις σας.

## Συχνές ερωτήσεις

### Πώς μπορώ να αλλάξω τη μορφή ημερομηνίας για τον άξονα κατηγορίας;

Για να αλλάξετε τη μορφή ημερομηνίας για τον άξονα κατηγορίας, χρησιμοποιήστε το `setNumberFormat` στον άξονα κατηγορίας και παρέχετε το επιθυμητό μοτίβο μορφής ημερομηνίας, όπως "yyyy-MM-dd" ή "MM/yyyy". Βεβαιωθείτε ότι έχετε ορίσει `setNumberFormatLinkedToSource(false)` για να παρακάμψετε την προεπιλεγμένη μορφή.

### Μπορώ να χρησιμοποιήσω διαφορετικές μορφές ημερομηνίας για διαφορετικά γραφήματα στην ίδια παρουσίαση;

Ναι, μπορείτε να ορίσετε διαφορετικές μορφές ημερομηνίας για τους άξονες κατηγοριών σε διαφορετικά γραφήματα εντός της ίδιας παρουσίασης. Απλώς προσαρμόστε τον άξονα κατηγορίας για κάθε γράφημα, όπως απαιτείται.

### Πώς μπορώ να προσθέσω περισσότερα σημεία δεδομένων στο γράφημα;

Για να προσθέσετε περισσότερα σημεία δεδομένων στο γράφημα, χρησιμοποιήστε το `getDataPoints().addDataPointForLineSeries` μέθοδος στη σειρά δεδομένων και παρέχετε τις τιμές δεδομένων.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}