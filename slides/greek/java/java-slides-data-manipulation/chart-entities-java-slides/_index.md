---
"description": "Μάθετε να δημιουργείτε και να προσαρμόζετε γραφήματα Java Slides με το Aspose.Slides. Βελτιώστε τις παρουσιάσεις σας με ισχυρές οντότητες γραφημάτων."
"linktitle": "Οντότητες γραφημάτων σε διαφάνειες Java"
"second_title": "Aspose.Slides API επεξεργασίας Java PowerPoint"
"title": "Οντότητες γραφημάτων σε διαφάνειες Java"
"url": "/el/java/data-manipulation/chart-entities-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Οντότητες γραφημάτων σε διαφάνειες Java


## Εισαγωγή στις Οντότητες Γραφημάτων σε Διαφάνειες Java

Τα γραφήματα είναι ισχυρά εργαλεία για την οπτικοποίηση δεδομένων σε παρουσιάσεις. Είτε δημιουργείτε επιχειρηματικές αναφορές, ακαδημαϊκές παρουσιάσεις ή οποιαδήποτε άλλη μορφή περιεχομένου, τα γραφήματα βοηθούν στην αποτελεσματική μεταφορά πληροφοριών. Το Aspose.Slides για Java παρέχει ισχυρές λειτουργίες για εργασία με γραφήματα, καθιστώντας το μια εξαιρετική επιλογή για τους προγραμματιστές Java.

## Προαπαιτούμενα

Πριν εμβαθύνουμε στον κόσμο των οντοτήτων γραφημάτων, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

- Εγκατεστημένο κιτ ανάπτυξης Java (JDK)
- Λήψη και προσθήκη της βιβλιοθήκης Aspose.Slides για Java στο έργο σας
- Βασικές γνώσεις προγραμματισμού Java

Τώρα, ας ξεκινήσουμε με τη δημιουργία και την προσαρμογή γραφημάτων χρησιμοποιώντας το Aspose.Slides για Java.

## Βήμα 1: Δημιουργία παρουσίασης

Το πρώτο βήμα είναι να δημιουργήσετε μια νέα παρουσίαση όπου θα προσθέσετε το γράφημά σας. Ακολουθεί ένα απόσπασμα κώδικα για τη δημιουργία μιας παρουσίασης:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Βήμα 2: Προσθήκη γραφήματος

Μόλις ετοιμάσετε την παρουσίασή σας, ήρθε η ώρα να προσθέσετε ένα γράφημα. Σε αυτό το παράδειγμα, θα προσθέσουμε ένα απλό γράφημα γραμμών με δείκτες. Δείτε πώς μπορείτε να το κάνετε:

```java
// Πρόσβαση στην πρώτη διαφάνεια
ISlide slide = pres.getSlides().get_Item(0);

// Προσθήκη του δείγματος γραφήματος
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## Βήμα 3: Προσαρμογή τίτλου γραφήματος

Ένα καλά καθορισμένο γράφημα θα πρέπει να έχει έναν τίτλο. Ας ορίσουμε έναν τίτλο για το γράφημά μας:

```java
// Ορισμός τίτλου γραφήματος
chart.setTitle(true);
chart.getChartTitle().addTextFrameForOverriding("");
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
chartTitle.setText("Sample Chart");
```

## Βήμα 4: Μορφοποίηση γραμμών πλέγματος

Μπορείτε να μορφοποιήσετε τις κύριες και τις δευτερεύουσες γραμμές πλέγματος του γραφήματός σας. Ας ορίσουμε κάποια μορφοποίηση για τις γραμμές πλέγματος του κατακόρυφου άξονα:

```java
// Ορισμός μορφής κύριων γραμμών πλέγματος για τον άξονα τιμών
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Ορισμός μορφής δευτερευουσών γραμμών πλέγματος για τον άξονα τιμών
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## Βήμα 5: Προσαρμογή του άξονα τιμών

Έχετε τον έλεγχο της μορφής αριθμών, των μέγιστων και ελάχιστων τιμών του άξονα τιμών. Δείτε πώς μπορείτε να την προσαρμόσετε:

```java
// Ορισμός μορφής αριθμού άξονα τιμών
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");

// Ρύθμιση μέγιστων και ελάχιστων τιμών στο διάγραμμα
chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(15f);
chart.getAxes().getVerticalAxis().setMinValue(-2f);
chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
```

## Βήμα 6: Προσθήκη τίτλου άξονα αξίας

Για να κάνετε το γράφημά σας πιο κατατοπιστικό, μπορείτε να προσθέσετε έναν τίτλο στον άξονα τιμών:

```java
// Ορισμός τίτλου άξονα τιμών
chart.getAxes().getVerticalAxis().setTitle(true);
chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
valtitle.setText("Primary Axis");
```

## Βήμα 7: Μορφοποίηση άξονα κατηγορίας

Ο άξονας κατηγοριών, ο οποίος συνήθως αντιπροσωπεύει κατηγορίες δεδομένων, μπορεί επίσης να προσαρμοστεί:

```java
// Ορισμός μορφής κύριων γραμμών πλέγματος για τον άξονα κατηγορίας
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);

// Ορισμός μορφής δευτερευουσών γραμμών πλέγματος για τον άξονα κατηγορίας
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## Βήμα 8: Προσθήκη υπομνημάτων

Οι υπόμνημες βοηθούν στην επεξήγηση των σειρών δεδομένων στο γράφημά σας. Ας προσαρμόσουμε τους υπόμνημες:

```java
// Ορισμός ιδιοτήτων κειμένου υπομνημάτων
IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(16);
txtleg.setFontItalic(NullableBool.True);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);

// Ορισμός εμφάνισης υπομνημάτων γραφήματος χωρίς επικαλυπτόμενο γράφημα
chart.getLegend().setOverlay(true);
```

## Βήμα 9: Αποθήκευση της παρουσίασης

Τέλος, αποθηκεύστε την παρουσίασή σας με το διάγραμμα:

```java
pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## Πλήρης πηγαίος κώδικας για οντότητες γραφημάτων σε διαφάνειες Java

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
// Δημιουργήστε έναν κατάλογο εάν δεν υπάρχει ήδη.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Δημιουργία στιγμιαίας παρουσίασης// Δημιουργία στιγμιαίας παρουσίασης
Presentation pres = new Presentation();
try
{
	// Πρόσβαση στην πρώτη διαφάνεια
	ISlide slide = pres.getSlides().get_Item(0);
	// Προσθήκη του δείγματος γραφήματος
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
	// Ρύθμιση τίτλου γραφήματος
	chart.setTitle(true);
	chart.getChartTitle().addTextFrameForOverriding("");
	IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	chartTitle.setText("Sample Chart");
	chartTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	chartTitle.getPortionFormat().setFontHeight(20);
	chartTitle.getPortionFormat().setFontBold(NullableBool.True);
	chartTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Ορισμός μορφής κύριων γραμμών πλέγματος για τον άξονα τιμών
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);
	// Ορισμός μορφής δευτερευουσών γραμμών πλέγματος για τον άξονα τιμών
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// Ορισμός μορφής αριθμού άξονα τιμών
	chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
	chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");
	// Ρύθμιση μέγιστων και ελάχιστων τιμών στο διάγραμμα
	chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(15f);
	chart.getAxes().getVerticalAxis().setMinValue(-2f);
	chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
	chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
	// Ορισμός ιδιοτήτων κειμένου άξονα τιμών
	IChartPortionFormat txtVal = chart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(16);
	txtVal.setFontItalic(NullableBool.True);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	txtVal.setLatinFont(new FontData("Times New Roman"));
	// Ορισμός τίτλου άξονα τιμών
	chart.getAxes().getVerticalAxis().setTitle(true);
	chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
	IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	valtitle.setText("Primary Axis");
	valtitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	valtitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	valtitle.getPortionFormat().setFontHeight(20);
	valtitle.getPortionFormat().setFontBold(NullableBool.True);
	valtitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Ορισμός μορφής γραμμής άξονα τιμών: Τώρα παρωχημένη
	// chart.getAxes().getVerticalAxis().aVerticalAxis.l.AxisLine.setWidth(10);
	// chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().setFillType(FillType.Solid);
	// Chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().getSolidFillColor().Color = Color.Red;
	// Ορισμός μορφής κύριων γραμμών πλέγματος για τον άξονα κατηγορίας
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	// Ορισμός μορφής δευτερευουσών γραμμών πλέγματος για τον άξονα κατηγορίας
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// Ορισμός ιδιοτήτων κειμένου άξονα κατηγορίας
	IChartPortionFormat txtCat = chart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(16);
	txtCat.setFontItalic(NullableBool.True);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	txtCat.setLatinFont(new FontData("Arial"));
	// Ορισμός τίτλου κατηγορίας
	chart.getAxes().getHorizontalAxis().setTitle(true);
	chart.getAxes().getHorizontalAxis().getTitle().addTextFrameForOverriding("");
	IPortion catTitle = chart.getAxes().getHorizontalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	catTitle.setText("Sample Category");
	catTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	catTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	catTitle.getPortionFormat().setFontHeight(20);
	catTitle.getPortionFormat().setFontBold(NullableBool.True);
	catTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Ορισμός θέσης ετικέτας άξονα κατηγορίας
	chart.getAxes().getHorizontalAxis().setTickLabelPosition(TickLabelPositionType.Low);
	// Ρύθμιση γωνίας περιστροφής ετικέτας άξονα κατηγορίας
	chart.getAxes().getHorizontalAxis().setTickLabelRotationAngle(45);
	// Ορισμός ιδιοτήτων κειμένου υπομνημάτων
	IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(16);
	txtleg.setFontItalic(NullableBool.True);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);
	// Ορισμός εμφάνισης υπομνημάτων γραφήματος χωρίς επικαλυπτόμενο γράφημα
	chart.getLegend().setOverlay(true);
	// Σχεδίαση της πρώτης σειράς στον δευτερεύοντα άξονα τιμών
	// Chart.getChartData().getSeries().get_Item(0).PlotOnSecondAxis = true;
	// Ρύθμιση χρώματος πίσω τοίχου γραφήματος
	chart.getBackWall().setThickness(1);
	chart.getBackWall().getFormat().getFill().setFillType(FillType.Solid);
	chart.getBackWall().getFormat().getFill().getSolidFillColor().setColor(Color.ORANGE);
	chart.getFloor().getFormat().getFill().setFillType(FillType.Solid);
	chart.getFloor().getFormat().getFill().getSolidFillColor().getColor();
	// Ορισμός χρώματος περιοχής σχεδίασης
	chart.getPlotArea().getFormat().getFill().setFillType(FillType.Solid);
	chart.getPlotArea().getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
	// Αποθήκευση παρουσίασης
	pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Σύναψη

Σε αυτό το άρθρο, εξερευνήσαμε τον κόσμο των οντοτήτων γραφημάτων σε Java Slides χρησιμοποιώντας το Aspose.Slides για Java. Μάθατε πώς να δημιουργείτε, να προσαρμόζετε και να χειρίζεστε γραφήματα για να βελτιώσετε τις παρουσιάσεις σας. Τα γραφήματα όχι μόνο κάνουν τα δεδομένα σας οπτικά ελκυστικά, αλλά βοηθούν και το κοινό σας να κατανοήσει πιο εύκολα σύνθετες πληροφορίες.

## Συχνές ερωτήσεις

### Πώς μπορώ να αλλάξω τον τύπο γραφήματος;

Για να αλλάξετε τον τύπο γραφήματος, χρησιμοποιήστε το `chart.setType()` μέθοδο και καθορίστε τον επιθυμητό τύπο γραφήματος.

### Μπορώ να προσθέσω πολλές σειρές δεδομένων σε ένα γράφημα;

Ναι, μπορείτε να προσθέσετε πολλές σειρές δεδομένων σε ένα γράφημα χρησιμοποιώντας το `chart.getChartData().getSeries().addSeries()` μέθοδος.

### Πώς μπορώ να προσαρμόσω τα χρώματα του γραφήματος;

Μπορείτε να προσαρμόσετε τα χρώματα του γραφήματος ορίζοντας τη μορφή γεμίσματος για διάφορα στοιχεία γραφήματος, όπως γραμμές πλέγματος, τίτλο και υπομνήματα.

### Μπορώ να δημιουργήσω τρισδιάστατα γραφήματα;

Ναι, το Aspose.Slides για Java υποστηρίζει τη δημιουργία τρισδιάστατων γραφημάτων. Μπορείτε να ορίσετε το `ChartType` σε έναν τύπο γραφήματος 3D για να δημιουργήσετε έναν.

### Είναι το Aspose.Slides για Java συμβατό με τις πιο πρόσφατες εκδόσεις Java;

Ναι, το Aspose.Slides για Java ενημερώνεται τακτικά για να υποστηρίζει τις πιο πρόσφατες εκδόσεις Java και παρέχει συμβατότητα σε ένα ευρύ φάσμα περιβαλλόντων Java.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}