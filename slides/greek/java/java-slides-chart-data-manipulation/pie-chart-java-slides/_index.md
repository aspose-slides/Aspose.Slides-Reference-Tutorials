---
"description": "Μάθετε πώς να δημιουργείτε εκπληκτικά γραφήματα πίτας σε παρουσιάσεις PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Οδηγός βήμα προς βήμα με πηγαίο κώδικα για προγραμματιστές Java."
"linktitle": "Γράφημα πίτας σε διαφάνειες Java"
"second_title": "Aspose.Slides API επεξεργασίας Java PowerPoint"
"title": "Γράφημα πίτας σε διαφάνειες Java"
"url": "/el/java/chart-data-manipulation/pie-chart-java-slides/"
"weight": 23
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Γράφημα πίτας σε διαφάνειες Java


## Εισαγωγή στη δημιουργία γραφήματος πίτας σε Java Slides χρησιμοποιώντας το Aspose.Slides

Σε αυτό το σεμινάριο, θα δείξουμε πώς να δημιουργήσετε ένα γράφημα πίτας σε μια παρουσίαση PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Θα σας παρέχουμε οδηγίες βήμα προς βήμα και πηγαίο κώδικα Java για να σας βοηθήσουμε να ξεκινήσετε. Αυτός ο οδηγός προϋποθέτει ότι έχετε ήδη ρυθμίσει το περιβάλλον ανάπτυξής σας με το Aspose.Slides για Java.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε εγκαταστήσει και ρυθμίσει τη βιβλιοθήκη Aspose.Slides για Java στο έργο σας. Μπορείτε να την κατεβάσετε από [εδώ](https://releases.aspose.com/slides/java/).

## Βήμα 1: Εισαγωγή απαιτούμενων βιβλιοθηκών

```java
import com.aspose.slides.*;
import com.aspose.slides.charts.*;
```

Βεβαιωθείτε ότι έχετε εισαγάγει τις απαραίτητες κλάσεις από τη βιβλιοθήκη Aspose.Slides.

## Βήμα 2: Αρχικοποίηση της παρουσίασης

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";

// Δημιουργία κλάσης παρουσίασης που αντιπροσωπεύει αρχείο PPTX
Presentation presentation = new Presentation();
```

Δημιουργήστε ένα νέο αντικείμενο παρουσίασης για να αναπαραστήσετε το αρχείο PowerPoint. Αντικαταστήστε `"Your Document Directory"` με την πραγματική διαδρομή όπου θέλετε να αποθηκεύσετε την παρουσίαση.

## Βήμα 3: Προσθήκη διαφάνειας

```java
// Πρόσβαση στην πρώτη διαφάνεια
ISlide slide = presentation.getSlides().get_Item(0);
```

Αποκτήστε την πρώτη διαφάνεια της παρουσίασης όπου θέλετε να προσθέσετε το γράφημα πίτας.

## Βήμα 4: Προσθήκη γραφήματος πίτας

```java
// Προσθήκη κυκλικού γραφήματος με προεπιλεγμένα δεδομένα
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

Προσθέστε ένα γράφημα πίτας στη διαφάνεια στην καθορισμένη θέση και μέγεθος.

## Βήμα 5: Ορισμός τίτλου γραφήματος

```java
// Ορισμός τίτλου γραφήματος
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

Ορίστε έναν τίτλο για το γράφημα πίτας. Μπορείτε να προσαρμόσετε τον τίτλο όπως απαιτείται.

## Βήμα 6: Προσαρμογή δεδομένων γραφήματος

```java
// Ορίστε την πρώτη σειρά για εμφάνιση τιμών
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Ορισμός του ευρετηρίου του φύλλου δεδομένων γραφήματος
int defaultWorksheetIndex = 0;

// Λήψη του φύλλου εργασίας δεδομένων γραφήματος
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// Διαγραφή προεπιλεγμένων σειρών και κατηγοριών
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Προσθήκη νέων κατηγοριών
chart.getChartData().getCategories().add(workbook.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 3, 0, "3rd Qtr"));

// Προσθήκη νέας σειράς
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(0, 0, 1, "Series 1"), chart.getType());

// Συμπλήρωση δεδομένων σειράς
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 30));
```

Προσαρμόστε τα δεδομένα του γραφήματος προσθέτοντας κατηγορίες και σειρές και ορίζοντας τις τιμές τους. Σε αυτό το παράδειγμα, έχουμε τρεις κατηγορίες και μία σειρά με αντίστοιχα σημεία δεδομένων.

## Βήμα 7: Προσαρμογή τομέων κυκλικού γραφήματος

```java
// Ορισμός χρωμάτων τομέα
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

// Προσαρμόστε την εμφάνιση κάθε τομέα
IChartDataPoint point1 = series.getDataPoints().get_Item(0);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// Προσαρμογή περιγράμματος τομέα
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.ThinThick);
point1.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Προσαρμόστε άλλους τομείς με παρόμοιο τρόπο
```

Προσαρμόστε την εμφάνιση κάθε τομέα στο γράφημα πίτας. Μπορείτε να αλλάξετε τα χρώματα, τα στυλ περιγράμματος και άλλες οπτικές ιδιότητες.

## Βήμα 8: Προσαρμογή ετικετών δεδομένων

```java
// Προσαρμογή ετικετών δεδομένων
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

// Προσαρμόστε τις ετικέτες δεδομένων για άλλα σημεία δεδομένων με παρόμοιο τρόπο
```

Προσαρμόστε τις ετικέτες δεδομένων για κάθε σημείο δεδομένων στο κυκλικό διάγραμμα. Μπορείτε να ελέγξετε ποιες τιμές εμφανίζονται στο διάγραμμα.

## Βήμα 9: Εμφάνιση γραμμών ηγέτη

```java
// Εμφάνιση γραμμών οδηγού για το γράφημα
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

Ενεργοποιήστε τις γραμμές οδηγών για να συνδέσετε ετικέτες δεδομένων με τους αντίστοιχους τομείς τους.

## Βήμα 10: Ορισμός γωνίας περιστροφής κυκλικού διαγράμματος

```java
// Ορισμός της γωνίας περιστροφής για τους τομείς του κυκλικού διαγράμματος
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
```

Ορίστε τη γωνία περιστροφής για τους τομείς του κυκλικού διαγράμματος. Σε αυτό το παράδειγμα, την ορίσαμε στις 180 μοίρες.

## Βήμα 11: Αποθήκευση της παρουσίασης

```java
// Αποθήκευση της παρουσίασης με το γράφημα πίτας
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

Αποθηκεύστε την παρουσίαση με το γράφημα πίτας στον καθορισμένο κατάλογο.

## Πλήρης πηγαίος κώδικας για γράφημα πίτας σε διαφάνειες Java

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
// Δημιουργία κλάσης παρουσίασης που αντιπροσωπεύει αρχείο PPTX
Presentation presentation = new Presentation();
// Πρόσβαση στην πρώτη διαφάνεια
ISlide slides = presentation.getSlides().get_Item(0);
// Προσθήκη γραφήματος με προεπιλεγμένα δεδομένα
IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
// Τίτλος γραφήματος ρύθμισης
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
// Ορισμός της πρώτης σειράς σε Εμφάνιση τιμών
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Ρύθμιση του ευρετηρίου του φύλλου δεδομένων γραφήματος
int defaultWorksheetIndex = 0;
// Λήψη του φύλλου εργασίας δεδομένων γραφήματος
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Διαγραφή προεπιλεγμένων σειρών και κατηγοριών
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Προσθήκη νέων κατηγοριών
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
// Προσθήκη νέας σειράς
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// Συμπληρώνονται τώρα τα δεδομένα σειράς
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// Δεν λειτουργεί στη νέα έκδοση
// Προσθήκη νέων σημείων και ορισμός χρώματος τομέα
// series.IsColorVaried = true;
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);
IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// Ορισμός ορίου τομέα
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);
IChartDataPoint point1 = series.getDataPoints().get_Item(1);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Brown));
// Ορισμός ορίου τομέα
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.Single);
point1.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDot);
IChartDataPoint point2 = series.getDataPoints().get_Item(2);
point2.getFormat().getFill().setFillType(FillType.Solid);
point2.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Coral));
// Ορισμός ορίου τομέα
point2.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point2.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
point2.getFormat().getLine().setWidth(2.0);
point2.getFormat().getLine().setStyle(LineStyle.ThinThin);
point2.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDotDot);
// Δημιουργήστε προσαρμοσμένες ετικέτες για κάθε κατηγορία για νέες σειρές
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
// lbl.setShowCategoryName(true);
lbl1.getDataLabelFormat().setShowValue(true);
IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);
IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);
// Εμφάνιση γραμμών οδηγού για το διάγραμμα
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
// Ρύθμιση γωνίας περιστροφής για τομείς κυκλικού διαγράμματος
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
// Αποθήκευση παρουσίασης με γράφημα
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

## Σύναψη

Δημιουργήσατε με επιτυχία ένα γράφημα πίτας σε μια παρουσίαση PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Μπορείτε να προσαρμόσετε την εμφάνιση και τις ετικέτες δεδομένων του γραφήματος σύμφωνα με τις συγκεκριμένες απαιτήσεις σας. Αυτό το σεμινάριο παρέχει ένα βασικό παράδειγμα και μπορείτε να βελτιώσετε και να προσαρμόσετε περαιτέρω τα γραφήματά σας όπως απαιτείται.

## Συχνές ερωτήσεις

### Πώς μπορώ να αλλάξω τα χρώματα μεμονωμένων τομέων στο γράφημα πίτας;

Για να αλλάξετε τα χρώματα μεμονωμένων τομέων στο γράφημα πίτας, μπορείτε να προσαρμόσετε το χρώμα γεμίσματος για κάθε σημείο δεδομένων. Στο παράδειγμα κώδικα που παρέχεται, δείξαμε πώς να ορίσετε το χρώμα γεμίσματος για κάθε τομέα χρησιμοποιώντας το `getSolidFillColor().setColor()` μέθοδος. Μπορείτε να τροποποιήσετε τις τιμές χρώματος για να επιτύχετε την επιθυμητή εμφάνιση.

### Μπορώ να προσθέσω περισσότερες κατηγορίες και σειρές δεδομένων στο κυκλικό διάγραμμα;

Ναι, μπορείτε να προσθέσετε επιπλέον κατηγορίες και σειρές δεδομένων στο κυκλικό διάγραμμα. Για να το κάνετε αυτό, μπορείτε να χρησιμοποιήσετε το `getChartData().getCategories().add()` και `getChartData().getSeries().add()` μεθόδους, όπως φαίνεται στο παράδειγμα. Απλώς δώστε τα κατάλληλα δεδομένα και ετικέτες για τις νέες κατηγορίες και σειρές για να επεκτείνετε το γράφημά σας.

### Πώς μπορώ να προσαρμόσω την εμφάνιση των ετικετών δεδομένων;

Μπορείτε να προσαρμόσετε την εμφάνιση των ετικετών δεδομένων χρησιμοποιώντας το `getDataLabelFormat()` μέθοδος στην ετικέτα κάθε σημείου δεδομένων. Στο παράδειγμα, δείξαμε πώς να εμφανίσουμε την τιμή στις ετικέτες δεδομένων χρησιμοποιώντας `getDataLabelFormat().setShowValue(true)`Μπορείτε να προσαρμόσετε περαιτέρω τις ετικέτες δεδομένων ελέγχοντας ποιες τιμές εμφανίζονται, εμφανίζοντας κλειδιά υπομνήματος και προσαρμόζοντας άλλες επιλογές μορφοποίησης.

### Μπορώ να αλλάξω τον τίτλο του γραφήματος πίτας;

Ναι, μπορείτε να αλλάξετε τον τίτλο του κυκλικού γραφήματος. Στον παρεχόμενο κώδικα, ορίζουμε τον τίτλο του γραφήματος χρησιμοποιώντας `chart.getChartTitle().addTextFrameForOverriding("Sample Title")`Μπορείτε να αντικαταστήσετε `"Sample Title"` με το κείμενο τίτλου που επιθυμείτε.

### Πώς μπορώ να αποθηκεύσω την παρουσίαση που δημιουργήθηκε με το γράφημα πίτας;

Για να αποθηκεύσετε την παρουσίαση με το γράφημα πίτας, χρησιμοποιήστε το `presentation.save()` μέθοδος. Δώστε την επιθυμητή διαδρομή και όνομα αρχείου μαζί με τη μορφή στην οποία θέλετε να αποθηκεύσετε την παρουσίαση. Για παράδειγμα:
```java
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

Βεβαιωθείτε ότι έχετε καθορίσει τη σωστή διαδρομή και μορφή αρχείου.

### Μπορώ να δημιουργήσω άλλους τύπους γραφημάτων χρησιμοποιώντας το Aspose.Slides για Java;

Ναι, το Aspose.Slides για Java υποστηρίζει διάφορους τύπους γραφημάτων, όπως γραφήματα ράβδων, γραφήματα γραμμών και άλλα. Μπορείτε να δημιουργήσετε διαφορετικούς τύπους γραφημάτων αλλάζοντας το `ChartType` κατά την προσθήκη ενός γραφήματος. Ανατρέξτε στην τεκμηρίωση του Aspose.Slides για περισσότερες λεπτομέρειες σχετικά με τη δημιουργία διαφορετικών τύπων γραφημάτων.

### Πώς μπορώ να βρω περισσότερες πληροφορίες και παραδείγματα για την εργασία με το Aspose.Slides για Java;

Για περισσότερες πληροφορίες, λεπτομερή τεκμηρίωση και επιπλέον παραδείγματα, μπορείτε να επισκεφθείτε την ιστοσελίδα [Aspose.Slides για τεκμηρίωση Java](https://reference.aspose.com/slides/java/)Παρέχει ολοκληρωμένους πόρους που θα σας βοηθήσουν να χρησιμοποιήσετε αποτελεσματικά τη βιβλιοθήκη.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}