---
title: Ιδιότητες γραμματοσειράς για γράφημα σε διαφάνειες Java
linktitle: Ιδιότητες γραμματοσειράς για γράφημα σε διαφάνειες Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Βελτιώστε τις ιδιότητες γραμματοσειράς γραφήματος σε διαφάνειες Java με το Aspose.Slides για Java. Προσαρμόστε το μέγεθος, το στυλ και το χρώμα γραμματοσειράς για εντυπωσιακές παρουσιάσεις.
weight: 11
url: /el/java/customization-and-formatting/font-properties-for-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Εισαγωγή στις ιδιότητες γραμματοσειράς για γράφημα σε διαφάνειες Java

Αυτός ο οδηγός θα σας καθοδηγήσει στη ρύθμιση των ιδιοτήτων γραμματοσειράς για ένα γράφημα σε διαφάνειες Java χρησιμοποιώντας το Aspose.Slides. Μπορείτε να προσαρμόσετε το μέγεθος της γραμματοσειράς και την εμφάνιση του κειμένου του γραφήματος για να βελτιώσετε την οπτική ελκυστικότητα των παρουσιάσεών σας.

## Προαπαιτούμενα

 Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε ενσωματωμένο το Aspose.Slides for Java API στο έργο σας. Εάν δεν το έχετε κάνει ήδη, μπορείτε να το κατεβάσετε από το[Aspose.Slides για τεκμηρίωση Java](https://reference.aspose.com/slides/java/).

## Βήμα 1: Δημιουργήστε μια παρουσίαση

Αρχικά, δημιουργήστε μια νέα παρουσίαση χρησιμοποιώντας τον ακόλουθο κώδικα:

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Βήμα 2: Προσθέστε ένα γράφημα

Τώρα, ας προσθέσουμε ένα γράφημα στηλών ομαδοποίησης στην παρουσίασή σας:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
```

Εδώ, προσθέτουμε ένα γράφημα ομαδοποιημένης στήλης στην πρώτη διαφάνεια στις συντεταγμένες (100, 100) με πλάτος 500 μονάδες και ύψος 400 μονάδες.

## Βήμα 3: Προσαρμογή των ιδιοτήτων γραμματοσειράς

Στη συνέχεια, θα προσαρμόσουμε τις ιδιότητες γραμματοσειράς του γραφήματος. Σε αυτό το παράδειγμα, ορίζουμε το μέγεθος της γραμματοσειράς σε 20 για όλο το κείμενο του γραφήματος:

```java
chart.getTextFormat().getPortionFormat().setFontHeight(20);
```

Αυτός ο κώδικας ορίζει το μέγεθος της γραμματοσειράς σε 20 σημεία για όλο το κείμενο εντός του γραφήματος.

## Βήμα 4: Εμφάνιση ετικετών δεδομένων

Μπορείτε επίσης να εμφανίσετε ετικέτες δεδομένων στο γράφημα χρησιμοποιώντας τον ακόλουθο κώδικα:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

Αυτή η γραμμή κώδικα ενεργοποιεί ετικέτες δεδομένων για την πρώτη σειρά στο γράφημα, εμφανίζοντας τις τιμές στις στήλες του γραφήματος.

## Βήμα 5: Αποθηκεύστε την Παρουσίαση

Τέλος, αποθηκεύστε την παρουσίαση με τις προσαρμοσμένες ιδιότητες γραμματοσειράς γραφήματος:

```java
pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
```

Αυτός ο κώδικας θα αποθηκεύσει την παρουσίαση στον καθορισμένο κατάλογο με το όνομα αρχείου "FontPropertiesForChart.pptx".

## Ολοκληρώστε τον πηγαίο κώδικα για τις ιδιότητες γραμματοσειράς για γράφημα σε διαφάνειες Java

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

## συμπέρασμα

Σε αυτό το σεμινάριο, μάθατε πώς να προσαρμόζετε τις ιδιότητες γραμματοσειράς για ένα γράφημα σε διαφάνειες Java χρησιμοποιώντας το Aspose.Slides για Java. Μπορείτε να εφαρμόσετε αυτές τις τεχνικές για να βελτιώσετε την εμφάνιση των διαγραμμάτων και των παρουσιάσεών σας. Εξερευνήστε περισσότερες επιλογές στο[Aspose.Slides για τεκμηρίωση Java](https://reference.aspose.com/slides/java/).

## Συχνές ερωτήσεις

### Πώς μπορώ να αλλάξω το χρώμα της γραμματοσειράς;

 Για να αλλάξετε το χρώμα της γραμματοσειράς για το κείμενο του γραφήματος, χρησιμοποιήστε το`chart.getTextFormat().getPortionFormat().setFontColor(Color.RED);` , αντικαθιστώντας`Color.RED` με το επιθυμητό χρώμα.

### Μπορώ να αλλάξω το στυλ γραμματοσειράς (έντονη, πλάγια γραφή, κ.λπ.);

 Ναι, μπορείτε να αλλάξετε το στυλ γραμματοσειράς. Χρήση`chart.getTextFormat().getPortionFormat().setFontBold(true);` για να γίνει έντονη η γραμματοσειρά. Ομοίως, μπορείτε να χρησιμοποιήσετε`setFontItalic(true)` για να το κάνετε πλάγιο.

### Πώς μπορώ να προσαρμόσω τις ιδιότητες γραμματοσειράς για συγκεκριμένα στοιχεία γραφήματος;

Για να προσαρμόσετε τις ιδιότητες γραμματοσειράς για συγκεκριμένα στοιχεία γραφήματος, όπως ετικέτες αξόνων ή κείμενο μύθου, μπορείτε να αποκτήσετε πρόσβαση σε αυτά τα στοιχεία και να ορίσετε τις ιδιότητες γραμματοσειράς τους χρησιμοποιώντας παρόμοιες μεθόδους όπως φαίνεται παραπάνω.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
