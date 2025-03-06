---
title: Ορισμός δεδομένων γραφήματος από το βιβλίο εργασίας σε διαφάνειες Java
linktitle: Ορισμός δεδομένων γραφήματος από το βιβλίο εργασίας σε διαφάνειες Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Μάθετε πώς να ορίζετε δεδομένα γραφήματος από ένα βιβλίο εργασίας του Excel σε Java Slides χρησιμοποιώντας το Aspose.Slides. Οδηγός βήμα προς βήμα με παραδείγματα κώδικα για δυναμικές παρουσιάσεις.
weight: 15
url: /el/java/data-manipulation/set-chart-data-from-workbook-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ορισμός δεδομένων γραφήματος από το βιβλίο εργασίας σε διαφάνειες Java


## Εισαγωγή στον ορισμό δεδομένων γραφήματος από το βιβλίο εργασίας σε διαφάνειες Java

Το Aspose.Slides for Java είναι μια ισχυρή βιβλιοθήκη που επιτρέπει στους προγραμματιστές να εργάζονται με παρουσιάσεις PowerPoint μέσω προγραμματισμού. Παρέχει εκτεταμένες δυνατότητες για τη δημιουργία, τον χειρισμό και τη διαχείριση διαφανειών PowerPoint. Μια κοινή απαίτηση κατά την εργασία με παρουσιάσεις είναι να ορίσετε δυναμικά δεδομένα γραφήματος από μια εξωτερική πηγή δεδομένων, όπως ένα βιβλίο εργασίας του Excel. Σε αυτό το σεμινάριο, θα δείξουμε πώς να το πετύχετε αυτό χρησιμοποιώντας Java.

## Προαπαιτούμενα

Πριν προχωρήσουμε στην υλοποίηση, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

- Το Java Development Kit (JDK) είναι εγκατεστημένο στο σύστημά σας.
- Η βιβλιοθήκη Aspose.Slides for Java προστέθηκε στο έργο σας.
- Ένα βιβλίο εργασίας του Excel με τα δεδομένα που θέλετε να χρησιμοποιήσετε για το γράφημα.

## Βήμα 1: Δημιουργήστε μια παρουσίαση

```java
String outPath = "Your Output Directory" + "response2.pptx";
Presentation pres = new Presentation();
```

Ξεκινάμε δημιουργώντας μια νέα παρουσίαση PowerPoint χρησιμοποιώντας το Aspose.Slides για Java.

## Βήμα 2: Προσθέστε ένα γράφημα

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```

Στη συνέχεια, προσθέτουμε ένα γράφημα σε μία από τις διαφάνειες της παρουσίασης. Σε αυτό το παράδειγμα, προσθέτουμε ένα γράφημα πίτας, αλλά μπορείτε να επιλέξετε τον τύπο γραφήματος που ταιριάζει στις ανάγκες σας.

## Βήμα 3: Διαγραφή δεδομένων γραφήματος

```java
chart.getChartData().getChartDataWorkbook().clear(0);
```

Διαγράφουμε τυχόν υπάρχοντα δεδομένα από το γράφημα για να τα προετοιμάσουμε για νέα δεδομένα από το βιβλίο εργασίας του Excel.

## Βήμα 4: Φορτώστε το βιβλίο εργασίας του Excel

```java
Workbook workbook = new Workbook("Your Document Directory";
```

 Φορτώνουμε το βιβλίο εργασίας του Excel που περιέχει τα δεδομένα που θέλουμε να χρησιμοποιήσουμε για το γράφημα. Αντικαθιστώ`"book1.xlsx"` με τη διαδρομή προς το αρχείο Excel.

## Βήμα 5: Γράψτε τη ροή του βιβλίου εργασίας σε δεδομένα γραφήματος

```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
mem.flush();
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```

Μετατρέπουμε τα δεδομένα του βιβλίου εργασίας του Excel σε ροή και τα γράφουμε στα δεδομένα του γραφήματος.

## Βήμα 6: Ορισμός εύρους δεδομένων γραφήματος

```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```

Καθορίζουμε το εύρος των κελιών από το βιβλίο εργασίας του Excel που πρέπει να χρησιμοποιούνται ως δεδομένα για το γράφημα. Προσαρμόστε το εύρος όπως απαιτείται για τα δεδομένα σας.

## Βήμα 7: Προσαρμόστε τη σειρά γραφημάτων

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```

Μπορείτε να προσαρμόσετε διάφορες ιδιότητες της σειράς γραφημάτων για να ταιριάζουν με τις απαιτήσεις σας. Σε αυτό το παράδειγμα, ενεργοποιούμε ποικίλα χρώματα για τη σειρά γραφημάτων.

## Βήμα 8: Αποθηκεύστε την παρουσίαση

```java
pres.save(outPath, SaveFormat.Pptx);
```

Τέλος, αποθηκεύουμε την παρουσίαση με τα ενημερωμένα δεδομένα γραφήματος στην καθορισμένη διαδρομή εξόδου.

## Ολοκληρώστε τον πηγαίο κώδικα για τη ρύθμιση δεδομένων γραφήματος από το βιβλίο εργασίας σε διαφάνειες Java

```java
String outPath = "Your Output Directory" + "response2.pptx";
Presentation pres = new Presentation();
try {
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
	chart.getChartData().getChartDataWorkbook().clear(0);
	Workbook workbook = null;
	try {
		workbook = new Workbook("Your Document Directory";
	} catch (Exception ex) {
		System.out.println(ex);
	}
	ByteArrayOutputStream mem = new ByteArrayOutputStream();
	workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
	mem.flush();
	chart.getChartData().writeWorkbookStream(mem.toByteArray());
	chart.getChartData().setRange("Sheet2!$A$1:$B$3");
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	series.getParentSeriesGroup().setColorVaried(true);
	pres.save(outPath, SaveFormat.Pptx);
} catch(Exception e) {
} finally {
	if (pres != null) pres.dispose();
}
```

## συμπέρασμα

Σε αυτό το σεμινάριο, μάθαμε πώς να ορίζουμε δεδομένα γραφήματος από ένα βιβλίο εργασίας του Excel σε Java Slides χρησιμοποιώντας τη βιβλιοθήκη Aspose.Slides for Java. Ακολουθώντας τον οδηγό βήμα προς βήμα και χρησιμοποιώντας τα παρεχόμενα παραδείγματα πηγαίου κώδικα, μπορείτε εύκολα να ενσωματώσετε δεδομένα δυναμικού γραφήματος στις παρουσιάσεις σας στο PowerPoint.

## Συχνές ερωτήσεις

### Πώς μπορώ να προσαρμόσω την εμφάνιση του γραφήματος στην παρουσίασή μου;

Μπορείτε να προσαρμόσετε την εμφάνιση του γραφήματος τροποποιώντας ιδιότητες όπως χρώματα, γραμματοσειρές, ετικέτες και άλλα. Ανατρέξτε στην τεκμηρίωση Aspose.Slides for Java για λεπτομερείς πληροφορίες σχετικά με τις επιλογές προσαρμογής γραφημάτων.

### Μπορώ να χρησιμοποιήσω δεδομένα από διαφορετικό αρχείο Excel για το γράφημα;

Ναι, μπορείτε να χρησιμοποιήσετε δεδομένα από οποιοδήποτε αρχείο Excel, καθορίζοντας τη σωστή διαδρομή αρχείου κατά τη φόρτωση του βιβλίου εργασίας στον κώδικα.

### Τι άλλους τύπους γραφημάτων μπορώ να δημιουργήσω με το Aspose.Slides για Java;

Το Aspose.Slides για Java υποστηρίζει διάφορους τύπους γραφημάτων, συμπεριλαμβανομένων γραμμικών γραφημάτων, γραφημάτων γραμμών, διαγραμμάτων διασποράς και άλλων. Μπορείτε να επιλέξετε τον τύπο γραφήματος που ταιριάζει καλύτερα στις ανάγκες αναπαράστασης δεδομένων σας.

### Είναι δυνατή η δυναμική ενημέρωση των δεδομένων γραφήματος σε μια παρουσίαση που εκτελείται;

Ναι, μπορείτε να ενημερώσετε δυναμικά τα δεδομένα γραφήματος σε μια παρουσίαση, τροποποιώντας το υποκείμενο βιβλίο εργασίας και, στη συνέχεια, ανανεώνοντας τα δεδομένα του γραφήματος.

### Πού μπορώ να βρω περισσότερα παραδείγματα και πόρους για την εργασία με το Aspose.Slides για Java;

 Μπορείτε να εξερευνήσετε πρόσθετα παραδείγματα και πόρους στο[Aspose website](https://www.aspose.com/). Επιπλέον, η τεκμηρίωση Aspose.Slides for Java παρέχει ολοκληρωμένη καθοδήγηση σχετικά με την εργασία με τη βιβλιοθήκη.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
