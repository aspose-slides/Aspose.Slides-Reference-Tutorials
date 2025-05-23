---
"description": "Επικύρωση διάταξης κύριου γραφήματος στο PowerPoint με το Aspose.Slides για Java. Μάθετε να χειρίζεστε γραφήματα μέσω προγραμματισμού για εκπληκτικές παρουσιάσεις."
"linktitle": "Επικύρωση διάταξης γραφήματος που προστέθηκε σε διαφάνειες Java"
"second_title": "Aspose.Slides API επεξεργασίας Java PowerPoint"
"title": "Επικύρωση διάταξης γραφήματος που προστέθηκε σε διαφάνειες Java"
"url": "/el/java/data-manipulation/validate-chart-layout-added-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Επικύρωση διάταξης γραφήματος που προστέθηκε σε διαφάνειες Java


## Εισαγωγή στην Επικύρωση Διάταξης Γραφήματος στο Aspose.Slides για Java

Σε αυτό το σεμινάριο, θα εξερευνήσουμε πώς να επικυρώσετε τη διάταξη γραφήματος σε μια παρουσίαση PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Αυτή η βιβλιοθήκη σάς επιτρέπει να εργάζεστε με παρουσιάσεις PowerPoint μέσω προγραμματισμού, διευκολύνοντας τον χειρισμό και την επικύρωση διαφόρων στοιχείων, συμπεριλαμβανομένων των γραφημάτων.

## Βήμα 1: Αρχικοποίηση της παρουσίασης

Αρχικά, πρέπει να αρχικοποιήσουμε ένα αντικείμενο παρουσίασης και να φορτώσουμε μια υπάρχουσα παρουσίαση PowerPoint. Αντικατάσταση `"Your Document Directory"` με την πραγματική διαδρομή προς το αρχείο παρουσίασής σας (`test.pptx` σε αυτό το παράδειγμα).

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Βήμα 2: Προσθήκη γραφήματος

Στη συνέχεια, θα προσθέσουμε ένα γράφημα στην παρουσίαση. Σε αυτό το παράδειγμα, προσθέτουμε ένα γράφημα ομαδοποιημένων στηλών, αλλά μπορείτε να αλλάξετε το `ChartType` όπως απαιτείται.

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
```

## Βήμα 3: Επικύρωση διάταξης γραφήματος

Τώρα, θα επικυρώσουμε τη διάταξη του γραφήματος χρησιμοποιώντας το `validateChartLayout()` μέθοδος. Αυτό διασφαλίζει ότι το γράφημα έχει τοποθετηθεί σωστά μέσα στη διαφάνεια.

```java
chart.validateChartLayout();
```

## Βήμα 4: Ανάκτηση θέσης και μεγέθους γραφήματος

Αφού επικυρώσετε τη διάταξη του γραφήματος, ίσως θελήσετε να ανακτήσετε πληροφορίες σχετικά με τη θέση και το μέγεθός του. Μπορούμε να λάβουμε τις πραγματικές συντεταγμένες X και Y, καθώς και το πλάτος και το ύψος της περιοχής σχεδίασης του γραφήματος.

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

## Βήμα 5: Αποθήκευση της παρουσίασης

Τέλος, μην ξεχάσετε να αποθηκεύσετε την τροποποιημένη παρουσίαση. Σε αυτό το παράδειγμα, την αποθηκεύουμε ως `Result.pptx`, αλλά μπορείτε να καθορίσετε διαφορετικό όνομα αρχείου εάν χρειάζεται.

```java
pres.save(dataDir + "Result.pptx", SaveFormat.Pptx);
```

## Προστέθηκε πλήρης πηγαίος κώδικας για την επικύρωση διάταξης γραφήματος σε διαφάνειες Java

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

## Σύναψη

Σε αυτό το σεμινάριο, εμβαθύναμε στον κόσμο της εργασίας με γραφήματα σε παρουσιάσεις PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Καλύψαμε τα βασικά βήματα για την επικύρωση της διάταξης του γραφήματος, την ανάκτηση της θέσης και του μεγέθους του και την αποθήκευση της τροποποιημένης παρουσίασης. Ακολουθεί μια γρήγορη ανακεφαλαίωση:

## Συχνές ερωτήσεις

### Πώς μπορώ να αλλάξω τον τύπο γραφήματος;

Για να αλλάξετε τον τύπο γραφήματος, απλώς αντικαταστήστε `ChartType.ClusteredColumn` με τον επιθυμητό τύπο γραφήματος στο `addChart()` μέθοδος.

### Μπορώ να προσαρμόσω τα δεδομένα του γραφήματος;

Ναι, μπορείτε να προσαρμόσετε τα δεδομένα του γραφήματος προσθέτοντας και τροποποιώντας σειρές δεδομένων, κατηγορίες και τιμές. Ανατρέξτε στην τεκμηρίωση του Aspose.Slides για περισσότερες λεπτομέρειες.

### Τι γίνεται αν θέλω να τροποποιήσω άλλες ιδιότητες γραφήματος;

Μπορείτε να αποκτήσετε πρόσβαση σε διάφορες ιδιότητες γραφήματος και να τις προσαρμόσετε σύμφωνα με τις απαιτήσεις σας. Εξερευνήστε την τεκμηρίωση του Aspose.Slides για αναλυτικές πληροφορίες σχετικά με τον χειρισμό γραφημάτων.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}