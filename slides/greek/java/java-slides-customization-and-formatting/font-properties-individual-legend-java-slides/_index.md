---
"description": "Βελτιώστε τις παρουσιάσεις PowerPoint με προσαρμοσμένα στυλ γραμματοσειράς, μεγέθη και χρώματα για μεμονωμένους υπότιτλους σε διαφάνειες Java χρησιμοποιώντας το Aspose.Slides για Java."
"linktitle": "Ιδιότητες γραμματοσειράς για μεμονωμένο υπόμνημα σε διαφάνειες Java"
"second_title": "Aspose.Slides API επεξεργασίας Java PowerPoint"
"title": "Ιδιότητες γραμματοσειράς για μεμονωμένο υπόμνημα σε διαφάνειες Java"
"url": "/el/java/customization-and-formatting/font-properties-individual-legend-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ιδιότητες γραμματοσειράς για μεμονωμένο υπόμνημα σε διαφάνειες Java


## Εισαγωγή στις Ιδιότητες Γραμματοσειράς για Μεμονωμένο Υπόμνημα σε Διαφάνειες Java

Σε αυτό το σεμινάριο, θα εξερευνήσουμε πώς να ορίσετε ιδιότητες γραμματοσειράς για έναν μεμονωμένο υπόμνημα σε Java Slides χρησιμοποιώντας το Aspose.Slides for Java. Προσαρμόζοντας τις ιδιότητες γραμματοσειράς, μπορείτε να κάνετε τους υπόμνημές σας πιο οπτικά ελκυστικούς και ενημερωτικούς στις παρουσιάσεις του PowerPoint.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε ενσωματωμένη στο έργο σας τη βιβλιοθήκη Aspose.Slides για Java. Μπορείτε να την κατεβάσετε από το [Aspose.Slides για τεκμηρίωση Java](https://reference.aspose.com/slides/java/).

## Βήμα 1: Αρχικοποίηση παρουσίασης και προσθήκη γραφήματος

Αρχικά, ας ξεκινήσουμε αρχικοποιώντας μια παρουσίαση PowerPoint και προσθέτοντας ένα γράφημα σε αυτήν. Σε αυτό το παράδειγμα, θα χρησιμοποιήσουμε ένα γράφημα ομαδοποιημένων στηλών ως παράδειγμα.

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

Αντικαθιστώ `"Your Document Directory"` με τον πραγματικό κατάλογο όπου βρίσκεται το έγγραφο PowerPoint σας.

## Βήμα 2: Προσαρμόστε τις ιδιότητες γραμματοσειράς για το υπόμνημα

Τώρα, ας προσαρμόσουμε τις ιδιότητες γραμματοσειράς για μια μεμονωμένη καταχώρηση υπομνήματος μέσα στο γράφημα. Σε αυτό το παράδειγμα, στοχεύουμε στη δεύτερη καταχώρηση υπομνήματος (ευρετήριο 1), αλλά μπορείτε να προσαρμόσετε το ευρετήριο σύμφωνα με τις συγκεκριμένες απαιτήσεις σας.

```java
IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
tf.getPortionFormat().setFontBold(NullableBool.True);
tf.getPortionFormat().setFontHeight(20);
tf.getPortionFormat().setFontItalic(NullableBool.True);
tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```

Να τι κάνει κάθε γραμμή κώδικα:

- `get_Item(1)` ανακτά τη δεύτερη καταχώρηση υπομνήματος (ευρετήριο 1). Μπορείτε να αλλάξετε το ευρετήριο για να στοχεύσετε μια διαφορετική καταχώρηση υπομνήματος.
- `setFontBold(NullableBool.True)` ορίζει τη γραμματοσειρά σε έντονη γραφή.
- `setFontHeight(20)` ορίζει το μέγεθος της γραμματοσειράς σε 20 στιγμές.
- `setFontItalic(NullableBool.True)` ορίζει τη γραμματοσειρά σε πλάγια γραφή.
- `setFillType(FillType.Solid)` Καθορίζει ότι το κείμενο καταχώρησης υπομνήματος θα πρέπει να έχει συμπαγές γέμισμα.
- `getSolidFillColor().setColor(Color.BLUE)` ορίζει το χρώμα γεμίσματος σε μπλε. Μπορείτε να αντικαταστήσετε `Color.BLUE` με το επιθυμητό χρώμα.

## Βήμα 3: Αποθήκευση της τροποποιημένης παρουσίασης

Τέλος, αποθηκεύστε την τροποποιημένη παρουσίαση σε ένα νέο αρχείο για να διατηρήσετε τις αλλαγές σας.

```java
pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
```

Αντικαθιστώ `"output.pptx"` με το όνομα αρχείου εξόδου που προτιμάτε.

Αυτό ήταν! Προσαρμόσατε με επιτυχία τις ιδιότητες γραμματοσειράς για μια μεμονωμένη καταχώρηση υπομνήματος σε μια παρουσίαση Java Slides χρησιμοποιώντας το Aspose.Slides για Java.

## Πλήρης πηγαίος κώδικας για ιδιότητες γραμματοσειράς για μεμονωμένο υπόμνημα σε διαφάνειες Java

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

## Σύναψη

Σε αυτό το σεμινάριο, μάθαμε πώς να προσαρμόζουμε τις ιδιότητες γραμματοσειράς για έναν μεμονωμένο υπόμνημα σε Java Slides χρησιμοποιώντας το Aspose.Slides για Java. Προσαρμόζοντας τα στυλ, τα μεγέθη και τα χρώματα γραμματοσειρών, μπορείτε να βελτιώσετε την οπτική ελκυστικότητα και τη σαφήνεια των παρουσιάσεών σας στο PowerPoint.

## Συχνές ερωτήσεις

### Πώς μπορώ να αλλάξω το χρώμα της γραμματοσειράς;

Για να αλλάξετε το χρώμα της γραμματοσειράς, χρησιμοποιήστε `tf.getPortionFormat().getFontColor().setColor(yourColor)` αντί να αλλάξετε το χρώμα γεμίσματος. Αντικαταστήστε `yourColor` με το επιθυμητό χρώμα γραμματοσειράς.

### Πώς μπορώ να τροποποιήσω άλλες ιδιότητες υπομνήματος;

Μπορείτε να τροποποιήσετε διάφορες άλλες ιδιότητες του υπομνήματος, όπως τη θέση, το μέγεθος και τη μορφή. Ανατρέξτε στην τεκμηρίωση του Aspose.Slides για Java για λεπτομερείς πληροφορίες σχετικά με την εργασία με υπομνήματα.

### Μπορώ να εφαρμόσω αυτές τις αλλαγές σε πολλαπλές καταχωρήσεις υπομνήματος;

Ναι, μπορείτε να κάνετε επανάληψη στις καταχωρίσεις υπομνήματος και να εφαρμόσετε αυτές τις αλλαγές σε πολλαπλές καταχωρίσεις προσαρμόζοντας το ευρετήριο στο `get_Item(index)` και επαναλαμβάνοντας τον κώδικα προσαρμογής.

Θυμηθείτε να απορρίψετε το αντικείμενο παρουσίασης όταν τελειώσετε για να απελευθερώσετε πόρους:

```java
if (pres != null) pres.dispose();
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}