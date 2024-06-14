---
title: Επιλογές δείκτη γραφήματος στο σημείο δεδομένων σε διαφάνειες Java
linktitle: Επιλογές δείκτη γραφήματος στο σημείο δεδομένων σε διαφάνειες Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Βελτιστοποιήστε τις διαφάνειες Java σας με τις προσαρμοσμένες επιλογές δείκτη γραφήματος. Μάθετε να βελτιώνετε οπτικά τα σημεία δεδομένων χρησιμοποιώντας το Aspose.Slides για Java. Εξερευνήστε βήμα προς βήμα οδηγίες και συχνές ερωτήσεις.
type: docs
weight: 14
url: /el/java/data-manipulation/chart-marker-options-data-point-java-slides/
---

## Εισαγωγή στις Επιλογές δείκτη γραφήματος στο σημείο δεδομένων σε διαφάνειες Java

Όταν πρόκειται για τη δημιουργία εντυπωσιακών παρουσιάσεων, η δυνατότητα προσαρμογής και χειρισμού δεικτών γραφημάτων σε σημεία δεδομένων μπορεί να κάνει τη διαφορά. Με το Aspose.Slides για Java, έχετε τη δύναμη να μετατρέψετε τα γραφήματα σας σε δυναμικά και οπτικά ελκυστικά στοιχεία.

## Προαπαιτούμενα

Πριν βουτήξουμε στο τμήμα κωδικοποίησης, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

- Περιβάλλον Ανάπτυξης Java
- Aspose.Slides for Java Library
- Ένα ενσωματωμένο περιβάλλον ανάπτυξης Java (IDE)
- Δείγμα εγγράφου παρουσίασης (π.χ. "Test.pptx")

## Βήμα 1: Ρύθμιση του περιβάλλοντος

Αρχικά, βεβαιωθείτε ότι έχετε εγκατεστημένα και έτοιμα τα απαραίτητα εργαλεία. Δημιουργήστε ένα έργο Java στο IDE σας και εισαγάγετε τη βιβλιοθήκη Aspose.Slides for Java.

## Βήμα 2: Φόρτωση της παρουσίασης

Για να ξεκινήσετε, φορτώστε το δείγμα του εγγράφου παρουσίασης. Στον παρεχόμενο κώδικα, υποθέτουμε ότι το έγγραφο ονομάζεται "Test.pptx".

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
```

## Βήμα 3: Δημιουργία γραφήματος

Τώρα, ας δημιουργήσουμε ένα γράφημα στην παρουσίαση. Θα χρησιμοποιήσουμε ένα γραμμικό γράφημα με δείκτες σε αυτό το παράδειγμα.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

## Βήμα 4: Εργασία με δεδομένα γραφήματος

Για να χειριστούμε δεδομένα γραφήματος, πρέπει να αποκτήσουμε πρόσβαση στο βιβλίο εργασίας δεδομένων γραφήματος και να προετοιμάσουμε τη σειρά δεδομένων. Θα διαγράψουμε την προεπιλεγμένη σειρά και θα προσθέσουμε τα προσαρμοσμένα δεδομένα μας.

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
```

## Βήμα 5: Προσθήκη προσαρμοσμένων δεικτών

Εδώ έρχεται το συναρπαστικό μέρος - η προσαρμογή των δεικτών στα σημεία δεδομένων. Θα χρησιμοποιήσουμε εικόνες ως δείκτες σε αυτό το παράδειγμα.

```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);

BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);

IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Προσθήκη προσαρμοσμένων δεικτών σε σημεία δεδομένων
IChartDataPoint point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);

// Επαναλάβετε για άλλα σημεία δεδομένων
// ...

// Αλλαγή του μεγέθους του δείκτη σειράς γραφήματος
series.getMarker().setSize(15);
```

## Βήμα 6: Αποθήκευση της παρουσίασης

Αφού προσαρμόσετε τους δείκτες του γραφήματος, αποθηκεύστε την παρουσίαση για να δείτε τις αλλαγές σε δράση.

```java
pres.save(dataDir + "CustomizedChart.pptx", SaveFormat.Pptx);
```

## Ολοκληρώστε τον πηγαίο κώδικα για τις επιλογές δείκτη γραφήματος στο σημείο δεδομένων σε διαφάνειες Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
ISlide slide = pres.getSlides().get_Item(0);
//Δημιουργία του προεπιλεγμένου γραφήματος
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
//Λήψη του προεπιλεγμένου ευρετηρίου φύλλου εργασίας δεδομένων γραφήματος
int defaultWorksheetIndex = 0;
//Λήψη του φύλλου εργασίας δεδομένων γραφήματος
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
//Διαγραφή σειράς επίδειξης
chart.getChartData().getSeries().clear();
//Προσθήκη νέας σειράς
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
//Ρυθμίστε την εικόνα
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);
//Ρυθμίστε την εικόνα
BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);
//Πάρτε την πρώτη σειρά γραφημάτων
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
//Προσθέστε νέο σημείο (1:3) εκεί.
IChartDataPoint point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 2, 1, (double) 2.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx2);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 3, 1, (double) 3.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 4, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx2);
//Αλλαγή του δείκτη σειράς γραφήματος
series.getMarker().setSize(15);
pres.save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

## συμπέρασμα

Με το Aspose.Slides για Java, μπορείτε να αναβαθμίσετε τις παρουσιάσεις σας προσαρμόζοντας δείκτες γραφημάτων σε σημεία δεδομένων. Αυτό σας επιτρέπει να δημιουργήσετε οπτικά εντυπωσιακές και ενημερωτικές διαφάνειες που αιχμαλωτίζουν το κοινό σας.

## Συχνές ερωτήσεις

### Πώς μπορώ να αλλάξω το μέγεθος του δείκτη για τα σημεία δεδομένων;

 Για να αλλάξετε το μέγεθος του δείκτη για τα σημεία δεδομένων, χρησιμοποιήστε το`series.getMarker().setSize()` μέθοδο και παρέχετε το επιθυμητό μέγεθος ως όρισμα.

### Μπορώ να χρησιμοποιήσω εικόνες ως προσαρμοσμένους δείκτες;

 Ναι, μπορείτε να χρησιμοποιήσετε εικόνες ως προσαρμοσμένους δείκτες για σημεία δεδομένων. Ορίστε τον τύπο πλήρωσης σε`FillType.Picture` και δώστε την εικόνα που θέλετε να χρησιμοποιήσετε.

### Είναι το Aspose.Slides για Java κατάλληλο για τη δημιουργία δυναμικών γραφημάτων;

Απολύτως! Το Aspose.Slides για Java παρέχει εκτεταμένες δυνατότητες για τη δημιουργία δυναμικών και διαδραστικών γραφημάτων στις παρουσιάσεις σας.

### Μπορώ να προσαρμόσω άλλες πτυχές του γραφήματος χρησιμοποιώντας το Aspose.Slides;

Ναι, μπορείτε να προσαρμόσετε διάφορες πτυχές του γραφήματος, όπως τίτλους, άξονες, ετικέτες δεδομένων και άλλα, χρησιμοποιώντας το Aspose.Slides για Java.

### Πού μπορώ να έχω πρόσβαση στην τεκμηρίωση και λήψεις Aspose.Slides για Java;

 Μπορείτε να βρείτε την τεκμηρίωση στο[εδώ](https://reference.aspose.com/slides/java/) και κατεβάστε τη βιβλιοθήκη στο[εδώ](https://releases.aspose.com/slides/java/).