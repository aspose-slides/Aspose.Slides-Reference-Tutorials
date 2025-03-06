---
title: Προσθήκη Donut Callout σε Java Slides
linktitle: Προσθήκη Donut Callout σε Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Μάθετε να προσθέτετε Donut Callouts σε Java Slides χρησιμοποιώντας το Aspose.Slides για Java. Οδηγός βήμα προς βήμα με πηγαίο κώδικα για βελτιωμένες παρουσιάσεις.
weight: 12
url: /el/java/chart-data-manipulation/add-doughnut-callout-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Εισαγωγή στην προσθήκη ενός μηνύματος ντόνατ σε διαφάνειες Java χρησιμοποιώντας το Aspose.Slides για Java

Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία προσθήκης ενός Donut Callout σε μια διαφάνεια σε Java χρησιμοποιώντας το Aspose.Slides για Java. Ένα Donut Callout είναι ένα στοιχείο γραφήματος που μπορεί να χρησιμοποιηθεί για την επισήμανση συγκεκριμένων σημείων δεδομένων σε ένα γράφημα Donut. Θα σας παρέχουμε οδηγίες βήμα προς βήμα και πλήρη πηγαίο κώδικα για τη διευκόλυνσή σας.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

1. Περιβάλλον Ανάπτυξης Java
2. Aspose.Slides για βιβλιοθήκη Java
3. Ολοκληρωμένο περιβάλλον ανάπτυξης (IDE) όπως το Eclipse ή το IntelliJ IDEA
4. Μια παρουσίαση PowerPoint όπου θέλετε να προσθέσετε το μήνυμα Donut

## Βήμα 1: Ρυθμίστε το Java Project σας

1. Δημιουργήστε ένα νέο έργο Java στο IDE που έχετε επιλέξει.
2. Προσθέστε τη βιβλιοθήκη Aspose.Slides for Java στο έργο σας ως εξάρτηση.

## Βήμα 2: Αρχικοποιήστε την Παρουσίαση

Για να ξεκινήσετε, θα χρειαστεί να αρχικοποιήσετε μια παρουσίαση του PowerPoint και να δημιουργήσετε μια διαφάνεια όπου θέλετε να προσθέσετε το Donut Callout. Εδώ είναι ο κώδικας για να το πετύχετε αυτό:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
```

 Φροντίστε να αντικαταστήσετε`"Your Document Directory"` με την πραγματική διαδρομή προς το αρχείο παρουσίασης του PowerPoint.

## Βήμα 3: Δημιουργήστε ένα γράφημα ντόνατ

Στη συνέχεια, θα δημιουργήσετε ένα γράφημα Donut στη διαφάνεια. Μπορείτε να προσαρμόσετε τη θέση και το μέγεθος του γραφήματος σύμφωνα με τις απαιτήσεις σας. Ακολουθεί ο κώδικας για να προσθέσετε ένα γράφημα Donut:

```java
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## Βήμα 4: Προσαρμόστε το γράφημα ντόνατ

Τώρα, ήρθε η ώρα να προσαρμόσετε το γράφημα Donut. Θα ορίσουμε διάφορες ιδιότητες όπως η αφαίρεση του υπομνήματος, η διαμόρφωση του μεγέθους της οπής και η προσαρμογή της γωνίας πρώτης τομής. Εδώ είναι ο κωδικός:

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

Αυτό το απόσπασμα κώδικα ορίζει τις ιδιότητες για το γράφημα Donut. Μπορείτε να προσαρμόσετε τις τιμές για να καλύψετε τις συγκεκριμένες ανάγκες σας.

## Βήμα 5: Προσθέστε δεδομένα στο γράφημα ντόνατ

Τώρα, ας προσθέσουμε δεδομένα στο γράφημα Donut. Θα προσαρμόσουμε επίσης την εμφάνιση των σημείων δεδομένων. Εδώ είναι ο κώδικας για να το πετύχετε αυτό:

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        // Προσαρμόστε την εμφάνιση του σημείου δεδομένων εδώ
        i++;
    }
    categoryIndex++;
}
```

Σε αυτόν τον κώδικα, προσθέτουμε κατηγορίες και σημεία δεδομένων στο γράφημα Donut. Μπορείτε να προσαρμόσετε περαιτέρω την εμφάνιση των σημείων δεδομένων όπως απαιτείται.

## Βήμα 6: Αποθηκεύστε την παρουσίαση

Τέλος, μην ξεχάσετε να αποθηκεύσετε την παρουσίασή σας αφού προσθέσετε το Donut Callout. Ακολουθεί ο κώδικας για την αποθήκευση της παρουσίασης:

```java
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

 Φροντίστε να αντικαταστήσετε`"chart.pptx"` με το όνομα αρχείου που επιθυμείτε.

Συγχαρητήρια! Προσθέσατε με επιτυχία ένα Donut Callout σε μια διαφάνεια Java χρησιμοποιώντας το Aspose.Slides for Java. Τώρα μπορείτε να εκτελέσετε την εφαρμογή Java για να δημιουργήσετε την παρουσίαση του PowerPoint με το γράφημα Donut και το Callout.

## Ολοκληρώστε τον πηγαίο κώδικα για την προσθήκη επεξήγησης ντόνατ σε διαφάνειες Java

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

## συμπέρασμα

Σε αυτό το σεμινάριο, καλύψαμε τη διαδικασία προσθήκης ενός Donut Callout σε μια διαφάνεια Java χρησιμοποιώντας το Aspose.Slides για Java. Έχετε μάθει πώς να δημιουργείτε ένα γράφημα Donut, να προσαρμόζετε την εμφάνισή του και να προσθέτετε σημεία δεδομένων. Μη διστάσετε να βελτιώσετε περαιτέρω τις παρουσιάσεις σας με αυτήν την ισχυρή βιβλιοθήκη και να εξερευνήσετε περισσότερες επιλογές χαρτογράφησης.

## Συχνές ερωτήσεις

### Πώς μπορώ να αλλάξω την εμφάνιση του Donut Callout;

Μπορείτε να προσαρμόσετε την εμφάνιση του Donut Callout τροποποιώντας τις ιδιότητες των σημείων δεδομένων στο γράφημα. Στον κώδικα που παρέχεται, μπορείτε να δείτε πώς να ορίσετε το χρώμα πλήρωσης, το χρώμα γραμμής, το στυλ γραμματοσειράς και άλλα χαρακτηριστικά των σημείων δεδομένων.

### Μπορώ να προσθέσω περισσότερα σημεία δεδομένων στο γράφημα Donut;

Ναι, μπορείτε να προσθέσετε όσα σημεία δεδομένων χρειάζονται στο γράφημα Donut. Απλώς επεκτείνετε τους βρόχους στον κώδικα όπου προστίθενται κατηγορίες και σημεία δεδομένων και παρέχετε τα κατάλληλα δεδομένα και μορφοποίηση.

### Πώς μπορώ να προσαρμόσω τη θέση και το μέγεθος του γραφήματος Donut στη διαφάνεια;

 Μπορείτε να αλλάξετε τη θέση και το μέγεθος του γραφήματος Donut τροποποιώντας τις παραμέτρους στο`addChart` μέθοδος. Οι τέσσερις αριθμοί σε αυτήν τη μέθοδο αντιστοιχούν στις συντεταγμένες X και Y της επάνω αριστερής γωνίας του γραφήματος και στο πλάτος και το ύψος του, αντίστοιχα.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
