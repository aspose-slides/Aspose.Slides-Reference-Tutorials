---
"description": "Βελτιώστε τις παρουσιάσεις PowerPoint με το Aspose.Slides για Java. Μάθετε πώς να προσαρμόζετε τα μεγέθη γραμματοσειρών υπομνημάτων και πολλά άλλα στον αναλυτικό μας οδηγό."
"linktitle": "Υπόμνημα μεγέθους γραμματοσειράς σε διαφάνειες Java"
"second_title": "Aspose.Slides API επεξεργασίας Java PowerPoint"
"title": "Υπόμνημα μεγέθους γραμματοσειράς σε διαφάνειες Java"
"url": "/el/java/chart-elements/font-size-legend-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Υπόμνημα μεγέθους γραμματοσειράς σε διαφάνειες Java


## Εισαγωγή στον Υπόμνημα Μεγέθους Γραμματοσειράς σε Διαφάνειες Java

Σε αυτό το σεμινάριο, θα μάθετε πώς να προσαρμόσετε το μέγεθος της γραμματοσειράς του υπομνήματος σε μια διαφάνεια PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Θα παρέχουμε οδηγίες βήμα προς βήμα και πηγαίο κώδικα για να ολοκληρώσετε αυτήν την εργασία.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε εγκαταστήσει και ρυθμίσει τη βιβλιοθήκη Aspose.Slides για Java στο έργο Java σας. Μπορείτε να κατεβάσετε τη βιβλιοθήκη από [εδώ](https://releases.aspose.com/slides/java/).

## Βήμα 1: Αρχικοποίηση της παρουσίασης

Αρχικά, εισαγάγετε τις απαραίτητες κλάσεις και αρχικοποιήστε την παρουσίαση του PowerPoint.

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

Αντικαθιστώ `"Your Document Directory"` με την πραγματική διαδρομή προς το αρχείο PowerPoint σας.

## Βήμα 2: Προσθήκη γραφήματος

Στη συνέχεια, θα προσθέσουμε ένα γράφημα στη διαφάνεια και θα ορίσουμε το μέγεθος γραμματοσειράς του υπομνήματος.

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
}
```

Σε αυτόν τον κώδικα, δημιουργούμε ένα γράφημα ομαδοποιημένων στηλών στην πρώτη διαφάνεια και ορίζουμε το μέγεθος γραμματοσειράς του κειμένου του υπομνήματος σε 20 στιγμές. Μπορείτε να προσαρμόσετε το `setFontHeight` τιμή για να αλλάξετε το μέγεθος της γραμματοσειράς όπως απαιτείται.

## Βήμα 3: Προσαρμογή τιμών άξονα

Τώρα, ας προσαρμόσουμε τις τιμές του κατακόρυφου άξονα του γραφήματος.

```java
    chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
    chart.getAxes().getVerticalAxis().setMinValue(-5);
    chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
    chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Εδώ, ορίζουμε τις ελάχιστες και μέγιστες τιμές για τον κατακόρυφο άξονα. Μπορείτε να τροποποιήσετε τις τιμές σύμφωνα με τις απαιτήσεις δεδομένων σας.

## Βήμα 4: Αποθήκευση της παρουσίασης

Τέλος, αποθηκεύστε την τροποποιημένη παρουσίαση σε ένα νέο αρχείο.

```java
    pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

Αυτός ο κώδικας αποθηκεύει την τροποποιημένη παρουσίαση ως "output.pptx" στον καθορισμένο κατάλογο.

## Πλήρης πηγαίος κώδικας για υπόμνημα μεγέθους γραμματοσειράς σε διαφάνειες Java

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMinValue(-5);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(10);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Σύναψη

Έχετε προσαρμόσει με επιτυχία το μέγεθος γραμματοσειράς του υπομνήματος σε μια διαφάνεια PowerPoint σε Java χρησιμοποιώντας το Aspose.Slides για Java. Μπορείτε να εξερευνήσετε περαιτέρω τις δυνατότητες του Aspose.Slides για να δημιουργήσετε διαδραστικές και οπτικά ελκυστικές παρουσιάσεις.

## Συχνές ερωτήσεις

### Πώς μπορώ να αλλάξω το μέγεθος γραμματοσειράς του κειμένου υπομνήματος σε ένα γράφημα;

Για να αλλάξετε το μέγεθος γραμματοσειράς του κειμένου του υπομνήματος σε ένα γράφημα, μπορείτε να χρησιμοποιήσετε τον ακόλουθο κώδικα:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
```

Σε αυτόν τον κώδικα, δημιουργούμε ένα γράφημα και ορίζουμε το μέγεθος γραμματοσειράς του κειμένου του υπομνήματος σε 20 στιγμές. Μπορείτε να προσαρμόσετε το `setFontHeight` τιμή για να αλλάξετε το μέγεθος της γραμματοσειράς.

### Μπορώ να προσαρμόσω άλλες ιδιότητες του υπομνήματος σε ένα γράφημα;

Ναι, μπορείτε να προσαρμόσετε διάφορες ιδιότητες του υπομνήματος σε ένα γράφημα χρησιμοποιώντας το Aspose.Slides. Ορισμένες από τις συνήθεις ιδιότητες που μπορείτε να προσαρμόσετε περιλαμβάνουν τη μορφοποίηση κειμένου, τη θέση, την ορατότητα και άλλα. Για παράδειγμα, για να αλλάξετε τη θέση του υπομνήματος, μπορείτε να χρησιμοποιήσετε:

```java
chart.getLegend().setPosition(LegendPosition.Bottom);
```

Αυτός ο κώδικας ορίζει τον υπόμνημα ώστε να εμφανίζεται στο κάτω μέρος του γραφήματος. Εξερευνήστε την τεκμηρίωση του Aspose.Slides για περισσότερες επιλογές προσαρμογής.

### Πώς μπορώ να ορίσω ελάχιστες και μέγιστες τιμές για τον κατακόρυφο άξονα σε ένα γράφημα;

Για να ορίσετε ελάχιστες και μέγιστες τιμές για τον κατακόρυφο άξονα σε ένα γράφημα, μπορείτε να χρησιμοποιήσετε τον ακόλουθο κώδικα:

```java
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMinValue(-5);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Εδώ, απενεργοποιούμε την αυτόματη κλιμάκωση άξονα και καθορίζουμε τις ελάχιστες και μέγιστες τιμές για τον κατακόρυφο άξονα. Προσαρμόστε τις τιμές όπως απαιτείται για τα δεδομένα του γραφήματος σας.

### Πού μπορώ να βρω περισσότερες πληροφορίες και τεκμηρίωση για το Aspose.Slides;

Μπορείτε να βρείτε ολοκληρωμένη τεκμηρίωση και αναφορές API για το Aspose.Slides για Java στον ιστότοπο τεκμηρίωσης του Aspose. Επισκεφθείτε [εδώ](https://reference.aspose.com/slides/java/) για λεπτομερείς πληροφορίες σχετικά με τη χρήση της βιβλιοθήκης.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}