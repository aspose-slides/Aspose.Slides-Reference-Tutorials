---
title: Γράφημα πίτας σε διαφάνειες Java
linktitle: Γράφημα πίτας σε διαφάνειες Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Μάθετε πώς να δημιουργείτε εκπληκτικά γραφήματα πίτας σε παρουσιάσεις PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Οδηγός βήμα προς βήμα με πηγαίο κώδικα για προγραμματιστές Java.
weight: 23
url: /el/java/chart-data-manipulation/pie-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Εισαγωγή στη δημιουργία γραφήματος πίτας σε διαφάνειες Java χρησιμοποιώντας το Aspose.Slides

Σε αυτό το σεμινάριο, θα δείξουμε πώς να δημιουργήσετε ένα γράφημα πίτας σε μια παρουσίαση PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Θα σας παρέχουμε οδηγίες βήμα προς βήμα και τον πηγαίο κώδικα Java για να σας βοηθήσουμε να ξεκινήσετε. Αυτός ο οδηγός προϋποθέτει ότι έχετε ήδη ρυθμίσει το περιβάλλον ανάπτυξής σας με το Aspose.Slides για Java.

## Προαπαιτούμενα

 Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε εγκαταστήσει και διαμορφώσει τη βιβλιοθήκη Aspose.Slides for Java στο έργο σας. Μπορείτε να το κατεβάσετε από[εδώ](https://releases.aspose.com/slides/java/).

## Βήμα 1: Εισαγάγετε τις απαιτούμενες βιβλιοθήκες

```java
import com.aspose.slides.*;
import com.aspose.slides.charts.*;
```

Βεβαιωθείτε ότι έχετε εισαγάγει τις απαραίτητες κλάσεις από τη βιβλιοθήκη Aspose.Slides.

## Βήμα 2: Αρχικοποιήστε την Παρουσίαση

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";

// Κλάση Instantiation Presentation που αντιπροσωπεύει το αρχείο PPTX
Presentation presentation = new Presentation();
```

 Δημιουργήστε ένα νέο αντικείμενο παρουσίασης για να αντιπροσωπεύει το αρχείο PowerPoint σας. Αντικαθιστώ`"Your Document Directory"` με την πραγματική διαδρομή όπου θέλετε να αποθηκεύσετε την παρουσίαση.

## Βήμα 3: Προσθέστε μια Διαφάνεια

```java
// Πρόσβαση στην πρώτη διαφάνεια
ISlide slide = presentation.getSlides().get_Item(0);
```

Αποκτήστε την πρώτη διαφάνεια της παρουσίασης όπου θέλετε να προσθέσετε το γράφημα πίτας.

## Βήμα 4: Προσθέστε ένα γράφημα πίτας

```java
// Προσθέστε ένα γράφημα πίτας με προεπιλεγμένα δεδομένα
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
//Ρυθμίστε την πρώτη σειρά να εμφανίζει τιμές
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Ρύθμιση του ευρετηρίου του φύλλου δεδομένων γραφήματος
int defaultWorksheetIndex = 0;

// Λήψη του φύλλου εργασίας δεδομένων γραφήματος
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// Διαγραφή προεπιλεγμένων σειρών και κατηγοριών που δημιουργούνται
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

## Βήμα 7: Προσαρμογή τομέων γραφήματος πίτας

```java
// Ορίστε τα χρώματα του τομέα
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
// Προσαρμόστε τις ετικέτες δεδομένων
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

// Προσαρμόστε τις ετικέτες δεδομένων για άλλα σημεία δεδομένων με παρόμοιο τρόπο
```

Προσαρμόστε τις ετικέτες δεδομένων για κάθε σημείο δεδομένων στο γράφημα πίτας. Μπορείτε να ελέγξετε ποιες τιμές εμφανίζονται στο γράφημα.

## Βήμα 9: Εμφάνιση Γραμμών Leader

```java
// Εμφάνιση γραμμών αρχηγού για το γράφημα
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

Ενεργοποιήστε τις γραμμές οδηγών για τη σύνδεση ετικετών δεδομένων με τους αντίστοιχους τομείς τους.

## Βήμα 10: Ορίστε τη γωνία περιστροφής του γραφήματος πίτας

```java
// Ορίστε τη γωνία περιστροφής για τους τομείς του γραφήματος πίτας
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
```

Ορίστε τη γωνία περιστροφής για τους τομείς του Γραφήματος πίτας. Σε αυτό το παράδειγμα, το ρυθμίσαμε στις 180 μοίρες.

## Βήμα 11: Αποθηκεύστε την παρουσίαση

```java
// Αποθηκεύστε την παρουσίαση με το γράφημα πίτας
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

Αποθηκεύστε την παρουσίαση με το γράφημα πίτας στον καθορισμένο κατάλογο.

## Ολοκληρώστε τον πηγαίο κώδικα για το γράφημα πίτας σε διαφάνειες Java

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
// Κλάση Instantiation Presentation που αντιπροσωπεύει το αρχείο PPTX
Presentation presentation = new Presentation();
// Πρόσβαση στην πρώτη διαφάνεια
ISlide slides = presentation.getSlides().get_Item(0);
// Προσθήκη γραφήματος με προεπιλεγμένα δεδομένα
IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
// Ρύθμιση τίτλου γραφήματος
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
// Ορίστε την πρώτη σειρά σε Εμφάνιση τιμών
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Ρύθμιση του ευρετηρίου του φύλλου δεδομένων γραφήματος
int defaultWorksheetIndex = 0;
// Λήψη του φύλλου εργασίας δεδομένων γραφήματος
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Διαγραφή προεπιλεγμένων σειρών και κατηγοριών που δημιουργούνται
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Προσθήκη νέων κατηγοριών
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
// Προσθήκη νέας σειράς
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// Τώρα συμπληρώνονται δεδομένα σειράς
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// Δεν λειτουργεί σε νέα έκδοση
// Προσθήκη νέων σημείων και ρύθμιση χρώματος τομέα
// series.IsColorVaried = true;
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);
IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// Ρύθμιση περιγράμματος τομέα
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);
IChartDataPoint point1 = series.getDataPoints().get_Item(1);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Brown));
// Ρύθμιση περιγράμματος τομέα
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.Single);
point1.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDot);
IChartDataPoint point2 = series.getDataPoints().get_Item(2);
point2.getFormat().getFill().setFillType(FillType.Solid);
point2.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Coral));
// Ρύθμιση περιγράμματος τομέα
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
// Εμφάνιση γραμμών Leader για γράφημα
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
// Ρύθμιση γωνίας περιστροφής για τομείς γραφήματος πίτας
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
// Αποθήκευση παρουσίασης με γράφημα
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

## συμπέρασμα

Δημιουργήσατε με επιτυχία ένα γράφημα πίτας σε μια παρουσίαση PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Μπορείτε να προσαρμόσετε την εμφάνιση του γραφήματος και τις ετικέτες δεδομένων σύμφωνα με τις συγκεκριμένες απαιτήσεις σας. Αυτό το σεμινάριο παρέχει ένα βασικό παράδειγμα και μπορείτε να βελτιώσετε και να προσαρμόσετε περαιτέρω τα γραφήματα σας όπως απαιτείται.

## Συχνές ερωτήσεις

### Πώς μπορώ να αλλάξω τα χρώματα μεμονωμένων τομέων στο γράφημα πίτας;

 Για να αλλάξετε τα χρώματα μεμονωμένων τομέων στο γράφημα πίτας, μπορείτε να προσαρμόσετε το χρώμα πλήρωσης για κάθε σημείο δεδομένων. Στο παρεχόμενο παράδειγμα κώδικα, δείξαμε πώς να ορίσετε το χρώμα πλήρωσης για κάθε τομέα χρησιμοποιώντας το`getSolidFillColor().setColor()` μέθοδος. Μπορείτε να τροποποιήσετε τις τιμές χρώματος για να επιτύχετε την επιθυμητή εμφάνιση.

### Μπορώ να προσθέσω περισσότερες κατηγορίες και σειρές δεδομένων στο γράφημα πίτας;

 Ναι, μπορείτε να προσθέσετε επιπλέον κατηγορίες και σειρές δεδομένων στο γράφημα πίτας. Για να το κάνετε αυτό, μπορείτε να χρησιμοποιήσετε το`getChartData().getCategories().add()` και`getChartData().getSeries().add()` μεθόδους, όπως φαίνεται στο παράδειγμα. Απλώς παρέχετε τα κατάλληλα δεδομένα και ετικέτες για τις νέες κατηγορίες και σειρές για να επεκτείνετε το γράφημά σας.

### Πώς μπορώ να προσαρμόσω την εμφάνιση των ετικετών δεδομένων;

 Μπορείτε να προσαρμόσετε την εμφάνιση των ετικετών δεδομένων χρησιμοποιώντας το`getDataLabelFormat()` μέθοδος στην ετικέτα κάθε σημείου δεδομένων. Στο παράδειγμα, δείξαμε πώς να εμφανίζεται η τιμή σε ετικέτες δεδομένων χρησιμοποιώντας`getDataLabelFormat().setShowValue(true)`. Μπορείτε να προσαρμόσετε περαιτέρω τις ετικέτες δεδομένων ελέγχοντας ποιες τιμές εμφανίζονται, εμφανίζοντας πλήκτρα λεζάντα και προσαρμόζοντας άλλες επιλογές μορφοποίησης.

### Μπορώ να αλλάξω τον τίτλο του γραφήματος πίτας;

 Ναι, μπορείτε να αλλάξετε τον τίτλο του γραφήματος πίτας. Στον παρεχόμενο κώδικα, ορίσαμε τον τίτλο του γραφήματος χρησιμοποιώντας`chart.getChartTitle().addTextFrameForOverriding("Sample Title")` . Μπορείτε να αντικαταστήσετε`"Sample Title"` με το επιθυμητό κείμενο τίτλου.

### Πώς μπορώ να αποθηκεύσω την παρουσίαση που δημιουργήθηκε με το γράφημα πίτας;

 Για να αποθηκεύσετε την παρουσίαση με το γράφημα πίτας, χρησιμοποιήστε το`presentation.save()` μέθοδος. Δώστε την επιθυμητή διαδρομή αρχείου και το όνομα μαζί με τη μορφή στην οποία θέλετε να αποθηκεύσετε την παρουσίαση. Για παράδειγμα:
```java
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

Βεβαιωθείτε ότι έχετε καθορίσει τη σωστή διαδρομή και τη σωστή μορφή αρχείου.

### Μπορώ να δημιουργήσω άλλους τύπους γραφημάτων χρησιμοποιώντας το Aspose.Slides για Java;

Ναι, το Aspose.Slides για Java υποστηρίζει διάφορους τύπους γραφημάτων, συμπεριλαμβανομένων των γραφημάτων ράβδων, των γραμμικών γραφημάτων και άλλων. Μπορείτε να δημιουργήσετε διαφορετικούς τύπους γραφημάτων αλλάζοντας το`ChartType` κατά την προσθήκη γραφήματος. Ανατρέξτε στην τεκμηρίωση Aspose.Slides για περισσότερες λεπτομέρειες σχετικά με τη δημιουργία διαφορετικών τύπων γραφημάτων.

### Πώς μπορώ να βρω περισσότερες πληροφορίες και παραδείγματα για την εργασία με το Aspose.Slides για Java;

 Για περισσότερες πληροφορίες, λεπτομερή τεκμηρίωση και πρόσθετα παραδείγματα, μπορείτε να επισκεφτείτε το[Aspose.Slides για τεκμηρίωση Java](https://reference.aspose.com/slides/java/). Παρέχει ολοκληρωμένους πόρους για να σας βοηθήσει να χρησιμοποιήσετε τη βιβλιοθήκη αποτελεσματικά.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
