---
"description": "Μάθετε να προσθέτετε επεξηγήσεις ντόνατ σε διαφάνειες Java χρησιμοποιώντας το Aspose.Slides για Java. Οδηγός βήμα προς βήμα με πηγαίο κώδικα για βελτιωμένες παρουσιάσεις."
"linktitle": "Προσθήκη επεξήγησης ντόνατ σε διαφάνειες Java"
"second_title": "Aspose.Slides API επεξεργασίας Java PowerPoint"
"title": "Προσθήκη επεξήγησης ντόνατ σε διαφάνειες Java"
"url": "/el/java/chart-data-manipulation/add-doughnut-callout-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Προσθήκη επεξήγησης ντόνατ σε διαφάνειες Java


## Εισαγωγή στην Προσθήκη Επεξήγησης Ντόνατ σε Διαφάνειες Java χρησιμοποιώντας το Aspose.Slides για Java

Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία προσθήκης ενός Doughnut Callout σε μια διαφάνεια σε Java χρησιμοποιώντας το Aspose.Slides για Java. Ένα Doughnut Callout είναι ένα στοιχείο γραφήματος που μπορεί να χρησιμοποιηθεί για την επισήμανση συγκεκριμένων σημείων δεδομένων σε ένα γράφημα Doughnut. Θα σας παρέχουμε οδηγίες βήμα προς βήμα και πλήρη πηγαίο κώδικα για την διευκόλυνσή σας.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

1. Περιβάλλον Ανάπτυξης Java
2. Aspose.Slides για βιβλιοθήκη Java
3. Ολοκληρωμένο Περιβάλλον Ανάπτυξης (IDE) όπως το Eclipse ή το IntelliJ IDEA
4. Μια παρουσίαση PowerPoint όπου θέλετε να προσθέσετε το μήνυμα "Ντόνατς"

## Βήμα 1: Ρύθμιση του έργου Java

1. Δημιουργήστε ένα νέο έργο Java στο IDE της επιλογής σας.
2. Προσθέστε τη βιβλιοθήκη Aspose.Slides για Java στο έργο σας ως εξάρτηση.

## Βήμα 2: Αρχικοποίηση της παρουσίασης

Για να ξεκινήσετε, θα χρειαστεί να αρχικοποιήσετε μια παρουσίαση PowerPoint και να δημιουργήσετε μια διαφάνεια όπου θέλετε να προσθέσετε το Doughnut Callout. Ακολουθεί ο κώδικας για να το πετύχετε αυτό:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
```

Φροντίστε να αντικαταστήσετε `"Your Document Directory"` με την πραγματική διαδρομή προς το αρχείο παρουσίασης PowerPoint.

## Βήμα 3: Δημιουργήστε ένα διάγραμμα ντόνατ

Στη συνέχεια, θα δημιουργήσετε ένα γράφημα ντόνατ στη διαφάνεια. Μπορείτε να προσαρμόσετε τη θέση και το μέγεθος του γραφήματος σύμφωνα με τις απαιτήσεις σας. Ακολουθεί ο κώδικας για την προσθήκη ενός γραφήματος ντόνατ:

```java
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## Βήμα 4: Προσαρμόστε το διάγραμμα ντόνατ

Τώρα, ήρθε η ώρα να προσαρμόσουμε το γράφημα Doughnut. Θα ορίσουμε διάφορες ιδιότητες, όπως την αφαίρεση του υπομνήματος, τη διαμόρφωση του μεγέθους της οπής και την προσαρμογή της γωνίας της πρώτης τομής. Ορίστε ο κώδικας:

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

Αυτό το απόσπασμα κώδικα ορίζει τις ιδιότητες για το γράφημα Doughnut. Μπορείτε να προσαρμόσετε τις τιμές ώστε να ανταποκρίνονται στις συγκεκριμένες ανάγκες σας.

## Βήμα 5: Προσθήκη δεδομένων στο γράφημα ντόνατ

Τώρα, ας προσθέσουμε δεδομένα στο γράφημα Doughnut. Θα προσαρμόσουμε επίσης την εμφάνιση των σημείων δεδομένων. Ακολουθεί ο κώδικας για να το πετύχουμε αυτό:

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        // Προσαρμόστε την εμφάνιση των σημείων δεδομένων εδώ
        i++;
    }
    categoryIndex++;
}
```

Σε αυτόν τον κώδικα, προσθέτουμε κατηγορίες και σημεία δεδομένων στο γράφημα Doughnut. Μπορείτε να προσαρμόσετε περαιτέρω την εμφάνιση των σημείων δεδομένων, όπως απαιτείται.

## Βήμα 6: Αποθήκευση της παρουσίασης

Τέλος, μην ξεχάσετε να αποθηκεύσετε την παρουσίασή σας αφού προσθέσετε το Doughnut Callout. Ακολουθεί ο κώδικας για την αποθήκευση της παρουσίασης:

```java
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

Φροντίστε να αντικαταστήσετε `"chart.pptx"` με το όνομα αρχείου που επιθυμείτε.

Συγχαρητήρια! Προσθέσατε με επιτυχία ένα Doughnut Callout σε μια διαφάνεια Java χρησιμοποιώντας το Aspose.Slides για Java. Τώρα μπορείτε να εκτελέσετε την εφαρμογή Java για να δημιουργήσετε την παρουσίαση PowerPoint με το γράφημα Doughnut και το Callout.

## Πλήρης πηγαίος κώδικας για την προσθήκη επεξήγησης ντόνατ σε διαφάνειες Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
int seriesIndex = 0;
while (seriesIndex < 15)
{
	IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
	series.setExplosion(0);
	series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
	series.getParentSeriesGroup().setFirstSliceAngle(351);
	seriesIndex++;
}
int categoryIndex = 0;
while (categoryIndex < 15)
{
	chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
	int i = 0;
	while (i < chart.getChartData().getSeries().size())
	{
		IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
		IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
		dataPoint.getFormat().getFill().setFillType(FillType.Solid);
		dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
		dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
		dataPoint.getFormat().getLine().setWidth(1);
		dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
		dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
		if (i == chart.getChartData().getSeries().size() - 1)
		{
			IDataLabel lbl = dataPoint.getLabel();
			lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
			lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
			lbl.getDataLabelFormat().setShowValue(false);
			lbl.getDataLabelFormat().setShowCategoryName(true);
			lbl.getDataLabelFormat().setShowSeriesName(false);
			//lbl.getDataLabelFormat().setShowLabelAsDataCallout(true);
			lbl.getDataLabelFormat().setShowLeaderLines(true);
			lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);
			chart.validateChartLayout();
			lbl.setX(lbl.getX() + (float) 0.5);
			lbl.setY(lbl.getY() + (float) 0.5);
		}
		i++;
	}
	categoryIndex++;
}
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

## Σύναψη

Σε αυτό το σεμινάριο, καλύψαμε τη διαδικασία προσθήκης ενός γραφήματος Doughnut σε μια διαφάνεια Java χρησιμοποιώντας το Aspose.Slides για Java. Μάθατε πώς να δημιουργείτε ένα γράφημα Doughnut, να προσαρμόζετε την εμφάνισή του και να προσθέτετε σημεία δεδομένων. Μη διστάσετε να βελτιώσετε περαιτέρω τις παρουσιάσεις σας με αυτήν την ισχυρή βιβλιοθήκη και να εξερευνήσετε περισσότερες επιλογές δημιουργίας γραφημάτων.

## Συχνές ερωτήσεις

### Πώς μπορώ να αλλάξω την εμφάνιση του επεξηγηματικού μηνύματος για ντόνατς;

Μπορείτε να προσαρμόσετε την εμφάνιση του Doughnut Callout τροποποιώντας τις ιδιότητες των σημείων δεδομένων στο γράφημα. Στον κώδικα που παρέχεται, μπορείτε να δείτε πώς να ορίσετε το χρώμα γεμίσματος, το χρώμα γραμμής, το στυλ γραμματοσειράς και άλλα χαρακτηριστικά των σημείων δεδομένων.

### Μπορώ να προσθέσω περισσότερα σημεία δεδομένων στο γράφημα Doughnut;

Ναι, μπορείτε να προσθέσετε όσα σημεία δεδομένων χρειάζεστε στο γράφημα Doughnut. Απλώς επεκτείνετε τους βρόχους στον κώδικα όπου προστίθενται κατηγορίες και σημεία δεδομένων και παρέχετε τα κατάλληλα δεδομένα και μορφοποίηση.

### Πώς μπορώ να προσαρμόσω τη θέση και το μέγεθος του γραφήματος Doughnut στη διαφάνεια;

Μπορείτε να αλλάξετε τη θέση και το μέγεθος του γραφήματος Doughnut τροποποιώντας τις παραμέτρους στο `addChart` μέθοδος. Οι τέσσερις αριθμοί σε αυτήν τη μέθοδο αντιστοιχούν στις συντεταγμένες X και Y της επάνω αριστερής γωνίας του γραφήματος και στο πλάτος και ύψος του, αντίστοιχα.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}