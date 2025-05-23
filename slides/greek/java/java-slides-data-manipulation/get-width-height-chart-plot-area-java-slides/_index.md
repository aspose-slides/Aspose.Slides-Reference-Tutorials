---
"description": "Μάθετε πώς να ανακτάτε τις διαστάσεις της περιοχής ενός γραφήματος σε Java Slides χρησιμοποιώντας το Aspose.Slides για Java. Βελτιώστε τις δεξιότητές σας στον αυτοματισμό του PowerPoint."
"linktitle": "Λήψη πλάτους και ύψους από την περιοχή σχεδίασης γραφήματος σε διαφάνειες Java"
"second_title": "Aspose.Slides API επεξεργασίας Java PowerPoint"
"title": "Λήψη πλάτους και ύψους από την περιοχή σχεδίασης γραφήματος σε διαφάνειες Java"
"url": "/el/java/data-manipulation/get-width-height-chart-plot-area-java-slides/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Λήψη πλάτους και ύψους από την περιοχή σχεδίασης γραφήματος σε διαφάνειες Java


## Εισαγωγή

Τα γραφήματα είναι ένας ισχυρός τρόπος για την οπτικοποίηση δεδομένων σε παρουσιάσεις PowerPoint. Μερικές φορές, μπορεί να χρειαστεί να γνωρίζετε τις διαστάσεις της περιοχής σχεδίασης ενός γραφήματος για διάφορους λόγους, όπως η αλλαγή μεγέθους ή η επανατοποθέτηση στοιχείων μέσα στο γράφημα. Αυτός ο οδηγός θα δείξει πώς να αποκτήσετε το πλάτος και το ύψος της περιοχής σχεδίασης χρησιμοποιώντας Java και Aspose.Slides για Java.

## Προαπαιτούμενα

Πριν εμβαθύνουμε στον κώδικα, βεβαιωθείτε ότι έχετε εγκαταστήσει και ρυθμίσει τη βιβλιοθήκη Aspose.Slides για Java στο έργο Java σας. Μπορείτε να κατεβάσετε τη βιβλιοθήκη από τον ιστότοπο Aspose. [εδώ](https://releases.aspose.com/slides/java/).

## Βήμα 1: Ρύθμιση του Περιβάλλοντος

Βεβαιωθείτε ότι έχετε προσθέσει τη βιβλιοθήκη Aspose.Slides για Java στο έργο σας Java. Μπορείτε να το κάνετε αυτό συμπεριλαμβάνοντας τη βιβλιοθήκη στις εξαρτήσεις του έργου σας ή προσθέτοντας χειροκίνητα το αρχείο JAR.

## Βήμα 2: Δημιουργία παρουσίασης PowerPoint

Ας ξεκινήσουμε δημιουργώντας μια παρουσίαση PowerPoint και προσθέτοντας μια διαφάνεια σε αυτήν. Αυτή θα χρησιμεύσει ως το δοχείο για το γράφημά μας.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
```

Αντικαθιστώ `"Your Document Directory"` με τη διαδρομή προς τον κατάλογο εγγράφων σας.

## Βήμα 3: Προσθήκη γραφήματος

Τώρα, ας προσθέσουμε ένα γράφημα ομαδοποιημένων στηλών στη διαφάνεια. Θα επικυρώσουμε επίσης τη διάταξη του γραφήματος.

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
chart.validateChartLayout();
```

Αυτός ο κώδικας δημιουργεί ένα γράφημα ομαδοποιημένων στηλών στη θέση (100, 100) με διαστάσεις (500, 350).

## Βήμα 4: Λήψη των διαστάσεων της επιφάνειας του οικοπέδου

Για να ανακτήσουμε το πλάτος και το ύψος της περιοχής σχεδίασης του γραφήματος, μπορούμε να χρησιμοποιήσουμε τον ακόλουθο κώδικα:

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

Τώρα, οι μεταβλητές `x`, `y`, `w`, και `h` περιέχουν τις αντίστοιχες τιμές για τη συντεταγμένη X, τη συντεταγμένη Y, το πλάτος και το ύψος της περιοχής γραφήματος.

## Βήμα 5: Αποθήκευση της παρουσίασης

Τέλος, αποθηκεύστε την παρουσίαση μαζί με το γράφημα.

```java
pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
```

Φροντίστε να αντικαταστήσετε `"Chart_out.pptx"` με το όνομα αρχείου εξόδου που επιθυμείτε.

## Πλήρης πηγαίος κώδικας για λήψη πλάτους και ύψους από περιοχή γραφήματος σε διαφάνειες Java

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
try
{
	Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
	chart.validateChartLayout();
	double x = chart.getPlotArea().getActualX();
	double y = chart.getPlotArea().getActualY();
	double w = chart.getPlotArea().getActualWidth();
	double h = chart.getPlotArea().getActualHeight();
	// Αποθήκευση παρουσίασης με γράφημα
	pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Σύναψη

Σε αυτό το άρθρο, καλύψαμε τον τρόπο με τον οποίο μπορείτε να υπολογίσετε το πλάτος και το ύψος της περιοχής σχεδίασης ενός γραφήματος σε Java Slides χρησιμοποιώντας το Aspose.Slides for Java API. Αυτές οι πληροφορίες μπορούν να είναι πολύτιμες όταν χρειάζεται να προσαρμόσετε δυναμικά τη διάταξη των γραφημάτων σας σε παρουσιάσεις PowerPoint.

## Συχνές ερωτήσεις

### Πώς μπορώ να αλλάξω τον τύπο γραφήματος σε κάτι διαφορετικό από ομαδοποιημένες στήλες;

Μπορείτε να αλλάξετε τον τύπο γραφήματος αντικαθιστώντας `ChartType.ClusteredColumn` με την επιθυμητή απαρίθμηση τύπου γραφήματος, όπως `ChartType.Line` ή `ChartType.Pie`.

### Μπορώ να τροποποιήσω άλλες ιδιότητες του γραφήματος;

Ναι, μπορείτε να τροποποιήσετε διάφορες ιδιότητες του γραφήματος, όπως δεδομένα, ετικέτες και μορφοποίηση, χρησιμοποιώντας το Aspose.Slides για Java API. Ανατρέξτε στην τεκμηρίωση για περισσότερες λεπτομέρειες.

### Είναι το Aspose.Slides για Java κατάλληλο για επαγγελματικό αυτοματισμό PowerPoint;

Ναι, το Aspose.Slides για Java είναι μια ισχυρή βιβλιοθήκη για την αυτοματοποίηση εργασιών PowerPoint σε εφαρμογές Java. Παρέχει ολοκληρωμένες δυνατότητες για εργασία με παρουσιάσεις, διαφάνειες, σχήματα, γραφήματα και άλλα.

### Πώς μπορώ να μάθω περισσότερα για το Aspose.Slides για Java;

Μπορείτε να βρείτε εκτενή τεκμηρίωση και παραδείγματα στη σελίδα τεκμηρίωσης του Aspose.Slides για Java. [εδώ](https://reference.aspose.com/slides/java/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}