---
title: Ρύθμιση Callout For Data Label σε Java Slides
linktitle: Ρύθμιση Callout For Data Label σε Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Μάθετε πώς να ρυθμίζετε μηνύματα προώθησης για ετικέτες δεδομένων στο Aspose.Slides για Java. Οδηγός βήμα προς βήμα με τον πηγαίο κώδικα.
weight: 25
url: /el/java/data-manipulation/setting-callout-data-label-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Εισαγωγή στη ρύθμιση Callout για ετικέτα δεδομένων στο Aspose.Slides για Java

Σε αυτό το σεμινάριο, θα δείξουμε πώς να ρυθμίσετε μηνύματα προώθησης για ετικέτες δεδομένων σε ένα γράφημα χρησιμοποιώντας το Aspose.Slides για Java. Τα μηνύματα προώθησης μπορεί να είναι χρήσιμα για την επισήμανση συγκεκριμένων σημείων δεδομένων στο γράφημά σας. Θα περιηγηθούμε στον κώδικα βήμα προς βήμα και θα παρέχουμε τον απαραίτητο πηγαίο κώδικα.

## Προαπαιτούμενα

- Θα πρέπει να έχετε εγκατεστημένο το Aspose.Slides για Java.
- Δημιουργήστε ένα έργο Java και προσθέστε τη βιβλιοθήκη Aspose.Slides στο έργο σας.

## Βήμα 1: Δημιουργήστε μια παρουσίαση και προσθέστε ένα γράφημα

 Αρχικά, πρέπει να δημιουργήσουμε μια παρουσίαση και να προσθέσουμε ένα γράφημα σε μια διαφάνεια. Φροντίστε να αντικαταστήσετε`"Your Document Directory"` με την πραγματική διαδρομή προς τον κατάλογο εγγράφων σας.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## Βήμα 2: Διαμόρφωση του γραφήματος

Στη συνέχεια, θα διαμορφώσουμε το γράφημα ορίζοντας ιδιότητες όπως το υπόμνημα, τη σειρά και τις κατηγορίες.

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Διαμόρφωση σειρών και κατηγοριών (Μπορείτε να προσαρμόσετε τον αριθμό των σειρών και των κατηγοριών)
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        // Προσθέστε σημεία δεδομένων εδώ
        // ...
        i++;
    }
    categoryIndex++;
}
```

## Βήμα 3: Προσαρμογή ετικετών δεδομένων

Τώρα, θα προσαρμόσουμε τις ετικέτες δεδομένων, συμπεριλαμβανομένης της ρύθμισης μηνυμάτων για την τελευταία σειρά.

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    // Προσαρμογή μορφοποίησης σημείου δεδομένων (Γέμισμα, Γραμμή, κ.λπ.)

    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        //Προσαρμογή μορφοποίησης ετικετών (Γραμματοσειρά, Γέμισμα, κ.λπ.)
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        // Ενεργοποίηση μηνυμάτων
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(true);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
    }
    i++;
}
```

## Βήμα 4: Αποθηκεύστε την Παρουσίαση

Τέλος, αποθηκεύστε την παρουσίαση με το διαμορφωμένο γράφημα.

```java
pres.save("chart.pptx", SaveFormat.Pptx);
```

Τώρα, έχετε ρυθμίσει με επιτυχία μηνύματα προώθησης για ετικέτες δεδομένων σε ένα γράφημα χρησιμοποιώντας το Aspose.Slides για Java. Προσαρμόστε τον κώδικα σύμφωνα με το συγκεκριμένο γράφημα και τις απαιτήσεις δεδομένων σας.

## Ολοκληρώστε τον πηγαίο κώδικα για τη ρύθμιση του Callout For Data Label σε Java Slides

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
pres.save("chart.pptx", SaveFormat.Pptx);
```

## συμπέρασμα

Σε αυτό το σεμινάριο, έχουμε εξερευνήσει πώς να ρυθμίσετε μηνύματα προώθησης για ετικέτες δεδομένων σε ένα γράφημα χρησιμοποιώντας το Aspose.Slides για Java. Τα μηνύματα προώθησης είναι πολύτιμα εργαλεία για την έμφαση σε συγκεκριμένα σημεία δεδομένων στα γραφήματα και τις παρουσιάσεις σας. Παρέχουμε έναν οδηγό βήμα προς βήμα μαζί με τον πηγαίο κώδικα για να σας βοηθήσουμε να επιτύχετε αυτήν την προσαρμογή.

## Συχνές ερωτήσεις

### Πώς μπορώ να προσαρμόσω την εμφάνιση των ετικετών δεδομένων;

Για να προσαρμόσετε την εμφάνιση των ετικετών δεδομένων, μπορείτε να τροποποιήσετε ιδιότητες όπως γραμματοσειρά, γέμισμα και στυλ γραμμής. Για παράδειγμα:

```java
IDataLabel lbl = dataPoint.getLabel();
lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
```

### Πώς μπορώ να ενεργοποιήσω ή να απενεργοποιήσω τα μηνύματα προώθησης για ετικέτες δεδομένων;

 Για να ενεργοποιήσετε ή να απενεργοποιήσετε τα μηνύματα προώθησης για ετικέτες δεδομένων, χρησιμοποιήστε το`setShowLabelAsDataCallout` μέθοδος. Ρυθμίστε το σε`true` για ενεργοποίηση μηνυμάτων και`false`για να τα απενεργοποιήσετε.

```java
lbl.getDataLabelFormat().setShowLabelAsDataCallout(true); // Ενεργοποίηση μηνυμάτων
lbl.getDataLabelFormat().setShowLabelAsDataCallout(false); // Απενεργοποίηση μηνυμάτων
```

### Μπορώ να προσαρμόσω τις γραμμές οδηγού για ετικέτες δεδομένων;

Ναι, μπορείτε να προσαρμόσετε τις γραμμές οδηγού για ετικέτες δεδομένων χρησιμοποιώντας ιδιότητες όπως το στυλ γραμμής, το χρώμα και το πλάτος. Για παράδειγμα:

```java
lbl.getDataLabelFormat().setShowLeaderLines(true); // Ενεργοποίηση γραμμών ηγέτη
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setStyle(LineStyle.Single);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setWidth(1);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```

Αυτές είναι μερικές κοινές επιλογές προσαρμογής για ετικέτες δεδομένων και μηνύματα προώθησης στο Aspose.Slides για Java. Μπορείτε να προσαρμόσετε περαιτέρω την εμφάνιση στις συγκεκριμένες ανάγκες σας.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
