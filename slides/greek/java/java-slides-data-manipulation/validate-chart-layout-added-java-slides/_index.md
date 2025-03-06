---
title: Επικύρωση διάταξης γραφήματος που προστέθηκε σε διαφάνειες Java
linktitle: Επικύρωση διάταξης γραφήματος που προστέθηκε σε διαφάνειες Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Επικύρωση διάταξης κύριου γραφήματος στο PowerPoint με Aspose.Slides για Java. Μάθετε να χειρίζεστε γραφήματα μέσω προγραμματισμού για εντυπωσιακές παρουσιάσεις.
weight: 10
url: /el/java/data-manipulation/validate-chart-layout-added-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Εισαγωγή στην επικύρωση διάταξης γραφήματος στο Aspose.Slides για Java

Σε αυτό το σεμινάριο, θα διερευνήσουμε τον τρόπο επικύρωσης της διάταξης γραφήματος σε μια παρουσίαση του PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Αυτή η βιβλιοθήκη σάς επιτρέπει να εργάζεστε με παρουσιάσεις PowerPoint μέσω προγραμματισμού, καθιστώντας εύκολο τον χειρισμό και την επικύρωση διαφόρων στοιχείων, συμπεριλαμβανομένων των γραφημάτων.

## Βήμα 1: Εκκίνηση της Παρουσίασης

 Αρχικά, πρέπει να αρχικοποιήσουμε ένα αντικείμενο παρουσίασης και να φορτώσουμε μια υπάρχουσα παρουσίαση PowerPoint. Αντικαθιστώ`"Your Document Directory"` με την πραγματική διαδρομή προς το αρχείο παρουσίασής σας (`test.pptx` σε αυτό το παράδειγμα).

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Βήμα 2: Προσθήκη γραφήματος

 Στη συνέχεια, θα προσθέσουμε ένα γράφημα στην παρουσίαση. Σε αυτό το παράδειγμα, προσθέτουμε ένα γράφημα στηλών ομαδοποίησης, αλλά μπορείτε να το αλλάξετε`ChartType` όπως απαιτείται.

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
```

## Βήμα 3: Επικύρωση διάταξης γραφήματος

 Τώρα, θα επικυρώσουμε τη διάταξη του γραφήματος χρησιμοποιώντας το`validateChartLayout()` μέθοδος. Αυτό διασφαλίζει ότι το γράφημα έχει τοποθετηθεί σωστά μέσα στη διαφάνεια.

```java
chart.validateChartLayout();
```

## Βήμα 4: Ανάκτηση θέσης και μεγέθους γραφήματος

Αφού επικυρώσετε τη διάταξη του γραφήματος, ίσως θέλετε να ανακτήσετε πληροφορίες σχετικά με τη θέση και το μέγεθός του. Μπορούμε να πάρουμε τις πραγματικές συντεταγμένες X και Y, καθώς και το πλάτος και το ύψος της περιοχής γραφήματος του γραφήματος.

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

## Βήμα 5: Αποθήκευση της παρουσίασης

 Τέλος, μην ξεχάσετε να αποθηκεύσετε την τροποποιημένη παρουσίαση. Σε αυτό το παράδειγμα, το αποθηκεύουμε ως`Result.pptx`, αλλά μπορείτε να καθορίσετε διαφορετικό όνομα αρχείου εάν χρειάζεται.

```java
pres.save(dataDir + "Result.pptx", SaveFormat.Pptx);
```

## Ολοκληρωμένος πηγαίος κώδικας για επικύρωση διάταξης γραφήματος που προστέθηκε σε διαφάνειες Java

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
	chart.validateChartLayout();
	double x = chart.getPlotArea().getActualX();
	double y = chart.getPlotArea().getActualY();
	double w = chart.getPlotArea().getActualWidth();
	double h = chart.getPlotArea().getActualHeight();
	// Αποθήκευση παρουσίασης
	pres.save(dataDir + "Result.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## συμπέρασμα

Σε αυτό το σεμινάριο, εμβαθύναμε στον κόσμο της εργασίας με γραφήματα σε παρουσιάσεις PowerPoint χρησιμοποιώντας Aspose.Slides για Java. Καλύψαμε τα βασικά βήματα για την επικύρωση της διάταξης του γραφήματος, την ανάκτηση της θέσης και του μεγέθους της και την αποθήκευση της τροποποιημένης παρουσίασης. Ακολουθεί μια γρήγορη ανακεφαλαίωση:

## Συχνές ερωτήσεις

### Πώς μπορώ να αλλάξω τον τύπο του γραφήματος;

 Για να αλλάξετε τον τύπο γραφήματος, απλώς αντικαταστήστε`ChartType.ClusteredColumn`με τον επιθυμητό τύπο γραφήματος στο`addChart()` μέθοδος.

### Μπορώ να προσαρμόσω τα δεδομένα του γραφήματος;

Ναι, μπορείτε να προσαρμόσετε τα δεδομένα του γραφήματος προσθέτοντας και τροποποιώντας σειρές, κατηγορίες και τιμές δεδομένων. Ανατρέξτε στην τεκμηρίωση Aspose.Slides για περισσότερες λεπτομέρειες.

### Τι γίνεται αν θέλω να τροποποιήσω άλλες ιδιότητες γραφήματος;

Μπορείτε να αποκτήσετε πρόσβαση σε διάφορες ιδιότητες γραφήματος και να τις προσαρμόσετε σύμφωνα με τις απαιτήσεις σας. Εξερευνήστε την τεκμηρίωση Aspose.Slides για ολοκληρωμένες πληροφορίες σχετικά με τη χειραγώγηση γραφημάτων.

{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
