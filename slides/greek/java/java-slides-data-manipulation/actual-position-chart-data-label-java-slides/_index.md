---
"description": "Μάθετε πώς να λαμβάνετε την πραγματική θέση των ετικετών δεδομένων γραφήματος σε Java Slides χρησιμοποιώντας το Aspose.Slides για Java. Οδηγός βήμα προς βήμα με πηγαίο κώδικα."
"linktitle": "Λήψη πραγματικής θέσης ετικέτας δεδομένων γραφήματος σε διαφάνειες Java"
"second_title": "Aspose.Slides API επεξεργασίας Java PowerPoint"
"title": "Λήψη πραγματικής θέσης ετικέτας δεδομένων γραφήματος σε διαφάνειες Java"
"url": "/el/java/data-manipulation/actual-position-chart-data-label-java-slides/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Λήψη πραγματικής θέσης ετικέτας δεδομένων γραφήματος σε διαφάνειες Java


## Εισαγωγή στη Λήψη της Πραγματικής Θέσης της Ετικέτας Δεδομένων Γραφήματος σε Διαφάνειες Java

Σε αυτό το σεμινάριο, θα μάθετε πώς να ανακτάτε την πραγματική θέση των ετικετών δεδομένων γραφήματος χρησιμοποιώντας το Aspose.Slides για Java. Θα δημιουργήσουμε ένα πρόγραμμα Java που δημιουργεί μια παρουσίαση PowerPoint με ένα γράφημα, προσαρμόζει τις ετικέτες δεδομένων και, στη συνέχεια, προσθέτει σχήματα που αντιπροσωπεύουν τις θέσεις αυτών των ετικετών δεδομένων.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε ρυθμίσει τη βιβλιοθήκη Aspose.Slides για Java στο έργο Java σας.

## Βήμα 1: Δημιουργήστε μια παρουσίαση PowerPoint

Αρχικά, ας δημιουργήσουμε μια νέα παρουσίαση PowerPoint και ας προσθέσουμε ένα γράφημα σε αυτήν. Θα προσαρμόσουμε τις ετικέτες δεδομένων του γραφήματος αργότερα στο σεμινάριο.

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
    chart.validateChartLayout();
} finally {
    if (pres != null) pres.dispose();
}
```

## Βήμα 2: Προσαρμογή ετικετών δεδομένων
Τώρα, ας προσαρμόσουμε τις ετικέτες δεδομένων για τη σειρά γραφημάτων. Θα ορίσουμε τη θέση τους και θα εμφανίσουμε τις τιμές.

```java
try {
    // ... (προηγούμενος κώδικας)
    for (IChartSeries series : chart.getChartData().getSeries()) {
        series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
        series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    // ... (υπολειπόμενος κώδικας)
} finally {
    if (pres != null) pres.dispose();
}
```

## Βήμα 3: Λήψη πραγματικής θέσης ετικετών δεδομένων
Σε αυτό το βήμα, θα επαναλάβουμε τα σημεία δεδομένων της σειράς γραφημάτων και θα ανακτήσουμε την πραγματική θέση των ετικετών δεδομένων που έχουν τιμή μεγαλύτερη από 4. Στη συνέχεια, θα προσθέσουμε ελλείψεις για να αναπαραστήσουμε αυτές τις θέσεις.

```java
try {
    // ... (προηγούμενος κώδικας)
    for (IChartSeries series : chart.getChartData().getSeries()) {
        for (IChartDataPoint point : series.getDataPoints()) {
            if (point.getValue().toDouble() > 4) {
                float x = point.getLabel().getActualX();
                float y = point.getLabel().getActualY();
                float w = point.getLabel().getActualWidth();
                float h = point.getLabel().getActualHeight();
                IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
                shape.getFillFormat().setFillType(FillType.Solid);
                shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());
            }
        }
    }
    // ... (υπολειπόμενος κώδικας)
} finally {
    if (pres != null) pres.dispose();
}
```

## Βήμα 4: Αποθήκευση της παρουσίασης
Τέλος, αποθηκεύστε την παρουσίαση που δημιουργήθηκε σε ένα αρχείο.

```java
try {
    // ... (προηγούμενος κώδικας)
    pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Πλήρης πηγαίος κώδικας για λήψη της πραγματικής θέσης της ετικέτας δεδομένων γραφήματος σε διαφάνειες Java

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
	for (IChartSeries series : chart.getChartData().getSeries())
	{
		series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
		series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
	}
	chart.validateChartLayout();
	for (IChartSeries series : chart.getChartData().getSeries())
	{
		for (IChartDataPoint point : series.getDataPoints())
		{
			if (point.getValue().toDouble() > 4)
			{
				float x = point.getLabel().getActualX();
				float y = point.getLabel().getActualY();
				float w = point.getLabel().getActualWidth();
				float h = point.getLabel().getActualHeight();
				IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
				shape.getFillFormat().setFillType(FillType.Solid);
				shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());//ΝΑ ΚΑΝΩ
			}
		}
	}
	pres.save(dataDir + "GetActualPositionOFChartDatalabel", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Σύναψη

Σε αυτό το σεμινάριο, μάθατε πώς να ανακτήσετε την πραγματική θέση των ετικετών δεδομένων γραφήματος σε διαφάνειες Java χρησιμοποιώντας το Aspose.Slides για Java. Τώρα μπορείτε να χρησιμοποιήσετε αυτές τις γνώσεις για να βελτιώσετε τις παρουσιάσεις PowerPoint σας με προσαρμοσμένες ετικέτες δεδομένων και οπτικές αναπαραστάσεις των θέσεών τους.

## Συχνές ερωτήσεις

### Πώς μπορώ να προσαρμόσω τις ετικέτες δεδομένων σε ένα γράφημα;

Για να προσαρμόσετε τις ετικέτες δεδομένων σε ένα γράφημα, μπορείτε να χρησιμοποιήσετε το `setDefaultDataLabelFormat` μέθοδο στη σειρά γραφημάτων και ορίστε ιδιότητες όπως η θέση και η ορατότητα. Για παράδειγμα:
```java
for (IChartSeries series : chart.getChartData().getSeries()) {
    series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
    series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
}
```

### Πώς μπορώ να προσθέσω σχήματα για να αναπαραστήσω θέσεις ετικετών δεδομένων;

Μπορείτε να επαναλάβετε τα σημεία δεδομένων μιας σειράς γραφημάτων και να χρησιμοποιήσετε το `getActualX`, `getActualY`, `getActualWidth`, και `getActualHeight` μεθόδους της ετικέτας δεδομένων για να λάβετε τη θέση της. Στη συνέχεια, μπορείτε να προσθέσετε σχήματα χρησιμοποιώντας το `addAutoShape` μέθοδος. Ακολουθεί ένα παράδειγμα:
```java
float x = point.getLabel().getActualX();
float y = point.getLabel().getActualY();
float w = point.getLabel().getActualWidth();
float h = point.getLabel().getActualHeight();
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
```

### Πώς μπορώ να αποθηκεύσω την παρουσίαση που δημιουργήθηκε;

Μπορείτε να αποθηκεύσετε την παρουσίαση που δημιουργήθηκε χρησιμοποιώντας το `save` μέθοδος. Παρέχετε την επιθυμητή διαδρομή αρχείου και το `SaveFormat` ως παράμετροι. Για παράδειγμα:
```java
pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}