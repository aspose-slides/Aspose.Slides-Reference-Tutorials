---
"description": "Βελτιώστε τις ιδιότητες γραμματοσειράς γραφήματος σε διαφάνειες Java με το Aspose.Slides για Java. Προσαρμόστε το μέγεθος, το στυλ και το χρώμα της γραμματοσειράς για εντυπωσιακές παρουσιάσεις."
"linktitle": "Ιδιότητες γραμματοσειράς για γραφήματα σε διαφάνειες Java"
"second_title": "Aspose.Slides API επεξεργασίας Java PowerPoint"
"title": "Ιδιότητες γραμματοσειράς για γραφήματα σε διαφάνειες Java"
"url": "/el/java/customization-and-formatting/font-properties-for-chart-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ιδιότητες γραμματοσειράς για γραφήματα σε διαφάνειες Java


## Εισαγωγή στις Ιδιότητες Γραμματοσειράς για Διαφάνειες Γραφήματος σε Java

Αυτός ο οδηγός θα σας καθοδηγήσει στον ορισμό ιδιοτήτων γραμματοσειράς για ένα γράφημα σε Java Slides χρησιμοποιώντας το Aspose.Slides. Μπορείτε να προσαρμόσετε το μέγεθος και την εμφάνιση της γραμματοσειράς του κειμένου του γραφήματος για να βελτιώσετε την οπτική ελκυστικότητα των παρουσιάσεών σας.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε ενσωματώσει το Aspose.Slides για Java API στο έργο σας. Εάν δεν το έχετε κάνει ήδη, μπορείτε να το κατεβάσετε από το [Aspose.Slides για τεκμηρίωση Java](https://reference.aspose.com/slides/java/).

## Βήμα 1: Δημιουργήστε μια παρουσίαση

Αρχικά, δημιουργήστε μια νέα παρουσίαση χρησιμοποιώντας τον ακόλουθο κώδικα:

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Βήμα 2: Προσθήκη γραφήματος

Τώρα, ας προσθέσουμε ένα γράφημα ομαδοποιημένων στηλών στην παρουσίασή σας:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
```

Εδώ, προσθέτουμε ένα γράφημα ομαδοποιημένων στηλών στην πρώτη διαφάνεια στις συντεταγμένες (100, 100) με πλάτος 500 μονάδες και ύψος 400 μονάδες.

## Βήμα 3: Προσαρμογή ιδιοτήτων γραμματοσειράς

Στη συνέχεια, θα προσαρμόσουμε τις ιδιότητες γραμματοσειράς του γραφήματος. Σε αυτό το παράδειγμα, ορίζουμε το μέγεθος γραμματοσειράς σε 20 για όλο το κείμενο του γραφήματος:

```java
chart.getTextFormat().getPortionFormat().setFontHeight(20);
```

Αυτός ο κώδικας ορίζει το μέγεθος γραμματοσειράς σε 20 στιγμές για όλο το κείμενο μέσα στο γράφημα.

## Βήμα 4: Εμφάνιση ετικετών δεδομένων

Μπορείτε επίσης να εμφανίσετε ετικέτες δεδομένων στο γράφημα χρησιμοποιώντας τον ακόλουθο κώδικα:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

Αυτή η γραμμή κώδικα ενεργοποιεί τις ετικέτες δεδομένων για την πρώτη σειρά στο γράφημα, εμφανίζοντας τις τιμές στις στήλες του γραφήματος.

## Βήμα 5: Αποθήκευση της παρουσίασης

Τέλος, αποθηκεύστε την παρουσίαση με τις προσαρμοσμένες ιδιότητες γραμματοσειράς γραφήματος:

```java
pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
```

Αυτός ο κώδικας θα αποθηκεύσει την παρουσίαση στον καθορισμένο κατάλογο με το όνομα αρχείου "FontPropertiesForChart.pptx".

## Πλήρης πηγαίος κώδικας για ιδιότητες γραμματοσειράς για διαφάνειες γραφήματος σε Java

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
	chart.getTextFormat().getPortionFormat().setFontHeight(20);
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Σύναψη

Σε αυτό το σεμινάριο, μάθατε πώς να προσαρμόσετε τις ιδιότητες γραμματοσειράς για ένα γράφημα σε Java Slides χρησιμοποιώντας το Aspose.Slides για Java. Μπορείτε να εφαρμόσετε αυτές τις τεχνικές για να βελτιώσετε την εμφάνιση των γραφημάτων και των παρουσιάσεών σας. Εξερευνήστε περισσότερες επιλογές στο [Aspose.Slides για τεκμηρίωση Java](https://reference.aspose.com/slides/java/).

## Συχνές ερωτήσεις

### Πώς μπορώ να αλλάξω το χρώμα της γραμματοσειράς;

Για να αλλάξετε το χρώμα γραμματοσειράς για το κείμενο του γραφήματος, χρησιμοποιήστε το `chart.getTextFormat().getPortionFormat().setFontColor(Color.RED);`, αντικαθιστώντας `Color.RED` με το επιθυμητό χρώμα.

### Μπορώ να αλλάξω το στυλ γραμματοσειράς (έντονη, πλάγια, κ.λπ.);

Ναι, μπορείτε να αλλάξετε το στυλ γραμματοσειράς. Χρησιμοποιήστε `chart.getTextFormat().getPortionFormat().setFontBold(true);` για να κάνετε την γραμματοσειρά έντονη. Ομοίως, μπορείτε να χρησιμοποιήσετε `setFontItalic(true)` για να το κάνετε πλάγιο.

### Πώς μπορώ να προσαρμόσω τις ιδιότητες γραμματοσειράς για συγκεκριμένα στοιχεία γραφήματος;

Για να προσαρμόσετε τις ιδιότητες γραμματοσειράς για συγκεκριμένα στοιχεία γραφήματος, όπως ετικέτες αξόνων ή κείμενο υπομνήματος, μπορείτε να αποκτήσετε πρόσβαση σε αυτά τα στοιχεία και να ορίσετε τις ιδιότητες γραμματοσειράς τους χρησιμοποιώντας παρόμοιες μεθόδους όπως φαίνεται παραπάνω.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}