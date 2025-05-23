---
"description": "Μάθετε πώς να ορίζετε εξωτερικά βιβλία εργασίας σε Java Slides χρησιμοποιώντας το Aspose.Slides για Java. Δημιουργήστε δυναμικές παρουσιάσεις με ενοποίηση δεδομένων Excel."
"linktitle": "Ορισμός εξωτερικού βιβλίου εργασίας σε διαφάνειες Java"
"second_title": "Aspose.Slides API επεξεργασίας Java PowerPoint"
"title": "Ορισμός εξωτερικού βιβλίου εργασίας σε διαφάνειες Java"
"url": "/el/java/data-manipulation/set-external-workbook-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ορισμός εξωτερικού βιβλίου εργασίας σε διαφάνειες Java


## Εισαγωγή στο Ορισμός Εξωτερικού Βιβλίου Εργασίας σε Διαφάνειες Java

Σε αυτό το σεμινάριο, θα εξερευνήσουμε πώς να ορίσετε ένα εξωτερικό βιβλίο εργασίας σε Java Slides χρησιμοποιώντας το Aspose.Slides. Θα μάθετε πώς να δημιουργείτε μια παρουσίαση PowerPoint με ένα γράφημα που αναφέρεται σε δεδομένα από ένα εξωτερικό βιβλίο εργασίας του Excel. Μέχρι το τέλος αυτού του οδηγού, θα έχετε μια σαφή κατανόηση του πώς να ενσωματώνετε εξωτερικά δεδομένα στις παρουσιάσεις σας σε Java Slides.

## Προαπαιτούμενα

Πριν προχωρήσουμε στην υλοποίηση, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

- Το Java Development Kit (JDK) είναι εγκατεστημένο στο σύστημά σας.
- Το Aspose.Slides για τη βιβλιοθήκη Java προστέθηκε στο έργο σας.
- Ένα βιβλίο εργασίας του Excel με τα δεδομένα που θέλετε να αναφέρετε στην παρουσίασή σας.

## Βήμα 1: Δημιουργία νέας παρουσίασης

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

Ξεκινάμε δημιουργώντας μια νέα παρουσίαση PowerPoint χρησιμοποιώντας το Aspose.Slides.

## Βήμα 2: Προσθήκη γραφήματος

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
```

Στη συνέχεια, εισάγουμε ένα γράφημα πίτας στην παρουσίαση. Μπορείτε να προσαρμόσετε τον τύπο και τη θέση του γραφήματος όπως απαιτείται.

## Βήμα 3: Πρόσβαση σε εξωτερικό βιβλίο εργασίας

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
```

Για να αποκτήσουμε πρόσβαση στο εξωτερικό βιβλίο εργασίας, χρησιμοποιούμε το `setExternalWorkbook` μέθοδο και παρέχετε τη διαδρομή προς το βιβλίο εργασίας του Excel που περιέχει τα δεδομένα.

## Βήμα 4: Σύνδεση δεδομένων γραφήματος

```java
chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
```

Συνδέουμε το γράφημα με δεδομένα από το εξωτερικό βιβλίο εργασίας καθορίζοντας τις αναφορές κελιών για σειρές και κατηγορίες.

## Βήμα 5: Αποθήκευση της παρουσίασης

```java
pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
```

Τέλος, αποθηκεύουμε την παρουσίαση με την αναφορά εξωτερικού βιβλίου εργασίας ως αρχείο PowerPoint.

## Πλήρης πηγαίος κώδικας για το σύνολο εξτερικού βιβλίου εργασίας σε διαφάνειες Java

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
	chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
	pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Σύναψη

Σε αυτό το σεμινάριο, μάθαμε πώς να ορίσουμε ένα εξωτερικό βιβλίο εργασίας σε Java Slides χρησιμοποιώντας το Aspose.Slides. Τώρα μπορείτε να δημιουργήσετε παρουσιάσεις που αναφέρονται δυναμικά σε δεδομένα από βιβλία εργασίας του Excel, βελτιώνοντας την ευελιξία και την διαδραστικότητα των διαφανειών σας.

## Συχνές ερωτήσεις

### Πώς μπορώ να εγκαταστήσω το Aspose.Slides για Java;

Το Aspose.Slides για Java μπορεί να εγκατασταθεί προσθέτοντας τη βιβλιοθήκη στο έργο Java σας. Μπορείτε να κατεβάσετε τη βιβλιοθήκη από τον ιστότοπο Aspose και να ακολουθήσετε τις οδηγίες εγκατάστασης που παρέχονται στην τεκμηρίωση.

### Μπορώ να χρησιμοποιήσω διαφορετικούς τύπους γραφημάτων με εξωτερικά βιβλία εργασίας;

Ναι, μπορείτε να χρησιμοποιήσετε διάφορους τύπους γραφημάτων που υποστηρίζονται από το Aspose.Slides και να τους συνδέσετε με δεδομένα από εξωτερικά βιβλία εργασίας. Η διαδικασία ενδέχεται να διαφέρει ελαφρώς ανάλογα με τον τύπο γραφήματος που θα επιλέξετε.

### Τι γίνεται αν αλλάξει η δομή δεδομένων του εξωτερικού βιβλίου εργασίας μου;

Εάν αλλάξει η δομή των δεδομένων του εξωτερικού βιβλίου εργασίας σας, ίσως χρειαστεί να ενημερώσετε τις αναφορές κελιών στον κώδικα Java για να διασφαλίσετε ότι τα δεδομένα του γραφήματος παραμένουν ακριβή.

### Είναι το Aspose.Slides συμβατό με τις πιο πρόσφατες εκδόσεις Java;

Το Aspose.Slides για Java ενημερώνεται τακτικά για να διασφαλιστεί η συμβατότητα με τις πιο πρόσφατες εκδόσεις Java. Βεβαιωθείτε ότι ελέγχετε για ενημερώσεις και χρησιμοποιείτε την πιο πρόσφατη έκδοση της βιβλιοθήκης για βέλτιστη απόδοση και συμβατότητα.

### Μπορώ να προσθέσω πολλά γραφήματα που αναφέρονται στο ίδιο εξωτερικό βιβλίο εργασίας;

Ναι, μπορείτε να προσθέσετε πολλά γραφήματα στην παρουσίασή σας, όλα με αναφορά στο ίδιο εξωτερικό βιβλίο εργασίας. Απλώς επαναλάβετε τα βήματα που περιγράφονται σε αυτό το σεμινάριο για κάθε γράφημα που θέλετε να δημιουργήσετε.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}