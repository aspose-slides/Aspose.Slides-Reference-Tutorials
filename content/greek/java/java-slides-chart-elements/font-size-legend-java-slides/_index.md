---
title: Υπόμνημα μεγέθους γραμματοσειράς σε διαφάνειες Java
linktitle: Υπόμνημα μεγέθους γραμματοσειράς σε διαφάνειες Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Βελτιώστε τις παρουσιάσεις PowerPoint με το Aspose.Slides για Java. Μάθετε πώς να προσαρμόζετε τα μεγέθη γραμματοσειρών θρυλικών και πολλά άλλα στον αναλυτικό οδηγό μας.
type: docs
weight: 13
url: /el/java/chart-elements/font-size-legend-java-slides/
---

## Εισαγωγή στο Font Size Legend στις διαφάνειες Java

Σε αυτό το σεμινάριο, θα μάθετε πώς να προσαρμόζετε το μέγεθος γραμματοσειράς του μύθου σε μια διαφάνεια του PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Θα παρέχουμε οδηγίες βήμα προς βήμα και τον πηγαίο κώδικα για την επίτευξη αυτής της εργασίας.

## Προαπαιτούμενα

 Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε εγκαταστήσει και ρυθμίσει τη βιβλιοθήκη Aspose.Slides for Java στο έργο σας Java. Μπορείτε να κατεβάσετε τη βιβλιοθήκη από[εδώ](https://releases.aspose.com/slides/java/).

## Βήμα 1: Αρχικοποιήστε την Παρουσίαση

Πρώτα, εισαγάγετε τις απαραίτητες κλάσεις και αρχικοποιήστε την παρουσίασή σας στο PowerPoint.

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

 Αντικαθιστώ`"Your Document Directory"` με την πραγματική διαδρομή προς το αρχείο PowerPoint.

## Βήμα 2: Προσθέστε ένα γράφημα

Στη συνέχεια, θα προσθέσουμε ένα γράφημα στη διαφάνεια και θα ορίσουμε το μέγεθος γραμματοσειράς του υπόμνημα.

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
}
```

 Σε αυτόν τον κώδικα, δημιουργούμε ένα γράφημα στήλης ομαδοποίησης στην πρώτη διαφάνεια και ορίζουμε το μέγεθος γραμματοσειράς του κειμένου του υπόμνημα σε 20 σημεία. Μπορείτε να προσαρμόσετε το`setFontHeight`τιμή για να αλλάξετε το μέγεθος της γραμματοσειράς όπως απαιτείται.

## Βήμα 3: Προσαρμογή τιμών άξονα

Τώρα, ας προσαρμόσουμε τις τιμές κάθετου άξονα του γραφήματος.

```java
    chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
    chart.getAxes().getVerticalAxis().setMinValue(-5);
    chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
    chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Εδώ, ορίζουμε τις ελάχιστες και μέγιστες τιμές για τον κατακόρυφο άξονα. Μπορείτε να τροποποιήσετε τις τιμές σύμφωνα με τις απαιτήσεις δεδομένων σας.

## Βήμα 4: Αποθηκεύστε την Παρουσίαση

Τέλος, αποθηκεύστε την τροποποιημένη παρουσίαση σε νέο αρχείο.

```java
    pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

Αυτός ο κώδικας αποθηκεύει την τροποποιημένη παρουσίαση ως "output.pptx" στον καθορισμένο κατάλογο.

## Ολοκληρώστε τον πηγαίο κώδικα για το υπόμνημα μεγέθους γραμματοσειράς σε διαφάνειες Java

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

## συμπέρασμα

Προσαρμόσατε επιτυχώς το μέγεθος γραμματοσειράς του υπόμνημα σε μια διαφάνεια Java PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Μπορείτε να εξερευνήσετε περαιτέρω τις δυνατότητες του Aspose.Slides για να δημιουργήσετε διαδραστικές και οπτικά ελκυστικές παρουσιάσεις.

## Συχνές ερωτήσεις

### Πώς μπορώ να αλλάξω το μέγεθος της γραμματοσειράς του υπόμνημα κειμένου σε ένα γράφημα;

Για να αλλάξετε το μέγεθος γραμματοσειράς του κειμένου του υπόμνημα σε ένα γράφημα, μπορείτε να χρησιμοποιήσετε τον ακόλουθο κώδικα:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
```

 Σε αυτόν τον κώδικα, δημιουργούμε ένα γράφημα και ορίζουμε το μέγεθος της γραμματοσειράς του υπόμνημα σε 20 σημεία. Μπορείτε να προσαρμόσετε το`setFontHeight`τιμή για να αλλάξετε το μέγεθος της γραμματοσειράς.

### Μπορώ να προσαρμόσω άλλες ιδιότητες του υπόμνημα σε ένα γράφημα;

Ναι, μπορείτε να προσαρμόσετε διάφορες ιδιότητες του υπόμνημα σε ένα γράφημα χρησιμοποιώντας το Aspose.Slides. Ορισμένες από τις κοινές ιδιότητες που μπορείτε να προσαρμόσετε περιλαμβάνουν τη μορφοποίηση κειμένου, τη θέση, την ορατότητα και άλλα. Για παράδειγμα, για να αλλάξετε τη θέση του μύθου, μπορείτε να χρησιμοποιήσετε:

```java
chart.getLegend().setPosition(LegendPosition.Bottom);
```

Αυτός ο κωδικός ορίζει το υπόμνημα να εμφανίζεται στο κάτω μέρος του γραφήματος. Εξερευνήστε την τεκμηρίωση Aspose.Slides για περισσότερες επιλογές προσαρμογής.

### Πώς ορίζω ελάχιστες και μέγιστες τιμές για τον κατακόρυφο άξονα σε ένα γράφημα;

Για να ορίσετε ελάχιστες και μέγιστες τιμές για τον κατακόρυφο άξονα σε ένα γράφημα, μπορείτε να χρησιμοποιήσετε τον ακόλουθο κώδικα:

```java
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMinValue(-5);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Εδώ, απενεργοποιούμε την αυτόματη κλιμάκωση του άξονα και καθορίζουμε τις ελάχιστες και μέγιστες τιμές για τον κατακόρυφο άξονα. Προσαρμόστε τις τιμές όπως απαιτείται για τα δεδομένα του γραφήματος σας.

### Πού μπορώ να βρω περισσότερες πληροφορίες και τεκμηρίωση για το Aspose.Slides;

Μπορείτε να βρείτε ολοκληρωμένη τεκμηρίωση και αναφορές API για το Aspose.Slides για Java στον ιστότοπο τεκμηρίωσης του Aspose. Επίσκεψη[εδώ](https://reference.aspose.com/slides/java/) για λεπτομερείς πληροφορίες σχετικά με τη χρήση της βιβλιοθήκης.