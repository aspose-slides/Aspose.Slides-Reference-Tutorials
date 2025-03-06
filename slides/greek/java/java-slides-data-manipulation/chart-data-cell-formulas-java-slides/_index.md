---
title: Τύποι κυψελών δεδομένων γραφήματος σε διαφάνειες Java
linktitle: Τύποι κυψελών δεδομένων γραφήματος σε διαφάνειες Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Μάθετε πώς να ορίζετε τύπους κελιών δεδομένων γραφήματος σε παρουσιάσεις Java PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Δημιουργήστε δυναμικά γραφήματα με τύπους.
weight: 11
url: /el/java/data-manipulation/chart-data-cell-formulas-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Τύποι κυψελών δεδομένων γραφήματος σε διαφάνειες Java


## Εισαγωγή στους τύπους κυψελών δεδομένων γραφημάτων στο Aspose.Slides για Java

Σε αυτό το σεμινάριο, θα εξερευνήσουμε τον τρόπο εργασίας με τύπους κελιών δεδομένων γραφήματος χρησιμοποιώντας Aspose.Slides για Java. Με το Aspose.Slides, μπορείτε να δημιουργείτε και να χειρίζεστε γραφήματα σε παρουσιάσεις PowerPoint, συμπεριλαμβανομένων τύπων ρύθμισης για κελιά δεδομένων.

## Προαπαιτούμενα

 Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε εγκαταστήσει τη βιβλιοθήκη Aspose.Slides for Java. Μπορείτε να το κατεβάσετε από[εδώ](https://releases.aspose.com/slides/java/).

## Βήμα 1: Δημιουργήστε μια παρουσίαση PowerPoint

Αρχικά, ας δημιουργήσουμε μια νέα παρουσίαση PowerPoint και ας προσθέσουμε ένα γράφημα σε αυτήν.

```java
String outpptxFile = "Your Output Directory" + File.separator + "ChartDataCell_Formulas_out.pptx";
Presentation presentation = new Presentation();
try
{
    // Προσθέστε ένα γράφημα στην πρώτη διαφάνεια
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 150, 150, 500, 300);
    
    // Λάβετε το βιβλίο εργασίας για δεδομένα γραφήματος
    IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    
    // Συνεχίστε με τις λειτουργίες κυψελών δεδομένων
    // ...
    
    // Αποθηκεύστε την παρουσίαση
    presentation.save(outpptxFile, SaveFormat.Pptx);
}
finally
{
    if (presentation != null) presentation.dispose();
}
```

## Βήμα 2: Ορίστε τύπους για κελιά δεδομένων

Τώρα, ας ορίσουμε τύπους για συγκεκριμένα κελιά δεδομένων στο γράφημα. Σε αυτό το παράδειγμα, θα ορίσουμε τύπους για δύο διαφορετικά κελιά.

### Κελί 1: Χρήση σημειογραφίας A1

```java
IChartDataCell cell1 = workbook.getCell(0, "B2");
cell1.setFormula("1 + SUM(F2:H5)");
```

Στον παραπάνω κώδικα, ορίσαμε έναν τύπο για το κελί B2 χρησιμοποιώντας συμβολισμό A1. Ο τύπος υπολογίζει το άθροισμα των κελιών F2 έως H5 και προσθέτει 1 στο αποτέλεσμα.

### Κελί 2: Χρήση συμβολισμού R1C1

```java
IChartDataCell cell2 = workbook.getCell(0, "C2");
cell2.setR1C1Formula("MAX(R2C6:R5C8) / 3");
```

Εδώ, ορίσαμε έναν τύπο για το κελί C2 χρησιμοποιώντας συμβολισμό R1C1. Ο τύπος υπολογίζει τη μέγιστη τιμή εντός του εύρους R2C6 έως R5C8 και στη συνέχεια τη διαιρεί με το 3.

## Βήμα 3: Υπολογισμός τύπων

Αφού ορίσετε τους τύπους, είναι απαραίτητο να τους υπολογίσετε χρησιμοποιώντας τον ακόλουθο κώδικα:

```java
workbook.calculateFormulas();
```

Αυτό το βήμα διασφαλίζει ότι το γράφημα αντικατοπτρίζει τις ενημερωμένες τιμές με βάση τους τύπους.

## Βήμα 4: Αποθηκεύστε την Παρουσίαση

Τέλος, αποθηκεύστε την τροποποιημένη παρουσίαση σε ένα αρχείο.

```java
presentation.save(outpptxFile, SaveFormat.Pptx);
```

## Πλήρης πηγαίος κώδικας για τύπους κυψελών δεδομένων γραφήματος σε διαφάνειες Java

```java
String outpptxFile = "Your Output Directory" + File.pathSeparator + "ChartDataCell_Formulas_out.pptx";
Presentation presentation = new Presentation();
try
{
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 150, 150, 500, 300);
	IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
	IChartDataCell cell1 = workbook.getCell(0, "B2");
	cell1.setFormula("1 + SUM(F2:H5)");
	IChartDataCell cell2 = workbook.getCell(0, "C2");
	cell2.setR1C1Formula("MAX(R2C6:R5C8) / 3");
	workbook.calculateFormulas();
	presentation.save(outpptxFile, SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## συμπέρασμα

Σε αυτό το σεμινάριο, εξερευνήσαμε τον τρόπο εργασίας με τύπους κελιών δεδομένων γραφήματος στο Aspose.Slides για Java. Έχουμε καλύψει τη δημιουργία μιας παρουσίασης PowerPoint, την προσθήκη γραφήματος, τη ρύθμιση τύπων για κελιά δεδομένων, τον υπολογισμό των τύπων και την αποθήκευση της παρουσίασης. Τώρα μπορείτε να αξιοποιήσετε αυτές τις δυνατότητες για να δημιουργήσετε δυναμικά και βασισμένα σε δεδομένα γραφήματα στις παρουσιάσεις σας.

## Συχνές ερωτήσεις

### Πώς μπορώ να προσθέσω ένα γράφημα σε μια συγκεκριμένη διαφάνεια;

 Για να προσθέσετε ένα γράφημα σε μια συγκεκριμένη διαφάνεια, μπορείτε να χρησιμοποιήσετε το`getSlides().get_Item(slideIndex)` μέθοδο για να αποκτήσετε πρόσβαση στην επιθυμητή διαφάνεια και, στη συνέχεια, χρησιμοποιήστε το`addChart` μέθοδο προσθήκης του γραφήματος.

### Μπορώ να χρησιμοποιήσω διαφορετικούς τύπους τύπων σε κελιά δεδομένων;

Ναι, μπορείτε να χρησιμοποιήσετε διάφορους τύπους τύπων, συμπεριλαμβανομένων μαθηματικών πράξεων, συναρτήσεων και αναφορών σε άλλα κελιά, σε τύπους κελιών δεδομένων.

### Πώς μπορώ να αλλάξω τον τύπο του γραφήματος;

 Μπορείτε να αλλάξετε τον τύπο γραφήματος χρησιμοποιώντας το`setChartType` μέθοδος στο`IChart` αντικείμενο και προσδιορίζοντας το επιθυμητό`ChartType`.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
