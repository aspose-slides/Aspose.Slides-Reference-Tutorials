---
title: Ιδιότητες γραμματοσειράς για Individual Legend σε διαφάνειες Java
linktitle: Ιδιότητες γραμματοσειράς για Individual Legend σε διαφάνειες Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Βελτιώστε τις παρουσιάσεις PowerPoint με προσαρμοσμένα στυλ γραμματοσειράς, μεγέθη και χρώματα για μεμονωμένους θρύλους σε διαφάνειες Java χρησιμοποιώντας το Aspose.Slides για Java.
weight: 12
url: /el/java/customization-and-formatting/font-properties-individual-legend-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Εισαγωγή στις ιδιότητες γραμματοσειράς για μεμονωμένο υπόμνημα σε διαφάνειες Java

Σε αυτό το σεμινάριο, θα εξερευνήσουμε τον τρόπο ρύθμισης των ιδιοτήτων γραμματοσειράς για ένα μεμονωμένο υπόμνημα σε Java Slides χρησιμοποιώντας το Aspose.Slides για Java. Προσαρμόζοντας τις ιδιότητες γραμματοσειράς, μπορείτε να κάνετε τους θρύλους σας πιο ελκυστικούς οπτικά και ενημερωτικούς στις παρουσιάσεις σας στο PowerPoint.

## Προαπαιτούμενα

 Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε ενσωματωμένη στο έργο σας τη βιβλιοθήκη Aspose.Slides for Java. Μπορείτε να το κατεβάσετε από το[Aspose.Slides for Java Documentation](https://reference.aspose.com/slides/java/).

## Βήμα 1: Αρχικοποίηση παρουσίασης και προσθήκη γραφήματος

Αρχικά, ας ξεκινήσουμε αρχικοποιώντας μια παρουσίαση PowerPoint και προσθέτοντας ένα γράφημα σε αυτήν. Σε αυτό το παράδειγμα, θα χρησιμοποιήσουμε ένα γράφημα ομαδοποιημένης στήλης ως απεικόνιση.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");

try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    // Ο υπόλοιπος κώδικας πηγαίνει εδώ
} finally {
    if (pres != null) pres.dispose();
}
```

 Αντικαθιστώ`"Your Document Directory"` με τον πραγματικό κατάλογο όπου βρίσκεται το έγγραφο PowerPoint σας.

## Βήμα 2: Προσαρμόστε τις ιδιότητες γραμματοσειράς για το Legend

Τώρα, ας προσαρμόσουμε τις ιδιότητες γραμματοσειράς για μια μεμονωμένη καταχώρηση λεζάντα μέσα στο γράφημα. Σε αυτό το παράδειγμα, στοχεύουμε τη δεύτερη καταχώρηση υπομνήματος (ευρετήριο 1), αλλά μπορείτε να προσαρμόσετε το ευρετήριο σύμφωνα με τις συγκεκριμένες απαιτήσεις σας.

```java
IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
tf.getPortionFormat().setFontBold(NullableBool.True);
tf.getPortionFormat().setFontHeight(20);
tf.getPortionFormat().setFontItalic(NullableBool.True);
tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```

Δείτε τι κάνει κάθε γραμμή κώδικα:

- `get_Item(1)` ανακτά τη δεύτερη καταχώρηση υπομνήματος (ευρετήριο 1). Μπορείτε να αλλάξετε το ευρετήριο για να στοχεύσετε μια διαφορετική καταχώρηση υπομνήματος.
- `setFontBold(NullableBool.True)` ορίζει τη γραμματοσειρά σε έντονη γραφή.
- `setFontHeight(20)` ορίζει το μέγεθος της γραμματοσειράς σε 20 σημεία.
- `setFontItalic(NullableBool.True)` ορίζει τη γραμματοσειρά σε πλάγια γραφή.
- `setFillType(FillType.Solid)` καθορίζει ότι το κείμενο της καταχώρησης του υπόμνημα θα πρέπει να έχει σταθερό γέμισμα.
- `getSolidFillColor().setColor(Color.BLUE)` ορίζει το χρώμα πλήρωσης σε μπλε. Μπορείτε να αντικαταστήσετε`Color.BLUE` με το χρώμα που επιθυμείτε.

## Βήμα 3: Αποθηκεύστε την Τροποποιημένη Παρουσίαση

Τέλος, αποθηκεύστε την τροποποιημένη παρουσίαση σε ένα νέο αρχείο για να διατηρήσετε τις αλλαγές σας.

```java
pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
```

 Αντικαθιστώ`"output.pptx"` με το όνομα του αρχείου εξόδου που προτιμάτε.

Αυτό είναι! Προσαρμόσατε επιτυχώς τις ιδιότητες γραμματοσειράς για μια μεμονωμένη καταχώρηση υπομνήματος σε μια παρουσίαση διαφανειών Java χρησιμοποιώντας το Aspose.Slides για Java.

## Ολοκληρωμένος πηγαίος κώδικας για ιδιότητες γραμματοσειράς για μεμονωμένο υπόμνημα σε διαφάνειες Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
	tf.getPortionFormat().setFontBold(NullableBool.True);
	tf.getPortionFormat().setFontHeight(20);
	tf.getPortionFormat().setFontItalic(NullableBool.True);
	tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## συμπέρασμα

Σε αυτό το σεμινάριο, μάθαμε πώς να προσαρμόζουμε τις ιδιότητες γραμματοσειράς για ένα μεμονωμένο υπόμνημα σε Java Slides χρησιμοποιώντας το Aspose.Slides για Java. Προσαρμόζοντας τα στυλ γραμματοσειράς, τα μεγέθη και τα χρώματα, μπορείτε να βελτιώσετε την οπτική ελκυστικότητα και τη σαφήνεια των παρουσιάσεών σας στο PowerPoint.

## Συχνές ερωτήσεις

### Πώς μπορώ να αλλάξω το χρώμα της γραμματοσειράς;

 Για να αλλάξετε το χρώμα της γραμματοσειράς, χρησιμοποιήστε`tf.getPortionFormat().getFontColor().setColor(yourColor)` αντί να αλλάξετε το χρώμα πλήρωσης. Αντικαθιστώ`yourColor` με το επιθυμητό χρώμα γραμματοσειράς.

### Πώς μπορώ να τροποποιήσω άλλες ιδιότητες υπόμνημα;

Μπορείτε να τροποποιήσετε διάφορες άλλες ιδιότητες του υπόμνημα, όπως θέση, μέγεθος και μορφή. Ανατρέξτε στην τεκμηρίωση Aspose.Slides for Java για λεπτομερείς πληροφορίες σχετικά με την εργασία με θρύλους.

### Μπορώ να εφαρμόσω αυτές τις αλλαγές σε πολλές καταχωρήσεις υπομνημάτων;

 Ναι, μπορείτε να κάνετε βρόχο μέσω των καταχωρήσεων μύθου και να εφαρμόσετε αυτές τις αλλαγές σε πολλές καταχωρήσεις προσαρμόζοντας το ευρετήριο σε`get_Item(index)` και επανάληψη του κώδικα προσαρμογής.

Θυμηθείτε να απορρίψετε το αντικείμενο παρουσίασης όταν ολοκληρώσετε την απελευθέρωση πόρων:

```java
if (pres != null) pres.dispose();
```
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
