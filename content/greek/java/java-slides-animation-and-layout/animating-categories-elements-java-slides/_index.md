---
title: Κινούμενη κίνηση στοιχείων κατηγοριών σε διαφάνειες Java
linktitle: Κινούμενη κίνηση στοιχείων κατηγοριών σε διαφάνειες Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Βελτιστοποιήστε τις παρουσιάσεις σας Java με το Aspose.Slides for Java. Μάθετε πώς να κάνετε κίνηση στοιχείων κατηγορίας στις διαφάνειες του PowerPoint βήμα προς βήμα.
type: docs
weight: 10
url: /el/java/animation-and-layout/animating-categories-elements-java-slides/
---

## Εισαγωγή στην Κινούμενη Στοιχεία Κατηγοριών σε Διαφάνειες Java

Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία της κίνησης στοιχείων κατηγορίας σε διαφάνειες Java χρησιμοποιώντας το Aspose.Slides για Java. Αυτός ο αναλυτικός οδηγός θα σας παρέχει τον πηγαίο κώδικα και εξηγήσεις που θα σας βοηθήσουν να επιτύχετε αυτό το εφέ κινούμενης εικόνας.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα ακόλουθα:

- Το Aspose.Slides for Java API έχει εγκατασταθεί.
- Μια υπάρχουσα παρουσίαση PowerPoint που περιέχει ένα γράφημα. Θα δημιουργήσετε κίνηση στα στοιχεία κατηγορίας αυτού του γραφήματος.

## Βήμα 1: Εισαγάγετε τη Βιβλιοθήκη Aspose.Slides

Για να ξεκινήσετε, εισαγάγετε τη βιβλιοθήκη Aspose.Slides στο έργο σας Java. Μπορείτε να κάνετε λήψη και να προσθέσετε τη βιβλιοθήκη στη διαδρομή τάξης του έργου σας. Βεβαιωθείτε ότι έχετε ρυθμίσει τις απαραίτητες εξαρτήσεις.

## Βήμα 2: Φορτώστε την παρουσίαση

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
```

 Σε αυτόν τον κώδικα, φορτώνουμε μια υπάρχουσα παρουσίαση PowerPoint που περιέχει το γράφημα που θέλετε να κάνετε κίνηση. Αντικαθιστώ`"Your Document Directory"` με την πραγματική διαδρομή προς τον κατάλογο εγγράφων σας.

## Βήμα 3: Λάβετε μια αναφορά στο αντικείμενο του γραφήματος

```java
ISlide slide = presentation.getSlides().get_Item(0);
IShapeCollection shapes = slide.getShapes();
IChart chart = (IChart) shapes.get_Item(0);
```

Λαμβάνουμε μια αναφορά στο αντικείμενο του γραφήματος στην πρώτη διαφάνεια της παρουσίασης. Προσαρμόστε το ευρετήριο διαφανειών (`get_Item(0)`) και ευρετήριο σχήματος (`get_Item(0)`) όπως απαιτείται για να αποκτήσετε πρόσβαση στο συγκεκριμένο γράφημά σας.

## Βήμα 4: Κινούμενη εικόνα των στοιχείων των κατηγοριών

```java
slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

for (int i = 0; i < chart.getChartData().getCategories().size(); i++) {
    for (int j = 0; j < chart.getChartData().getSeries().size(); j++) {
        ((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, i, j, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
    }
}
```

Εμψυχώνουμε τα στοιχεία των κατηγοριών μέσα στο γράφημα. Αυτός ο κώδικας προσθέτει ένα εφέ εξασθένισης σε ολόκληρο το γράφημα και στη συνέχεια προσθέτει ένα εφέ "Εμφάνιση" σε κάθε στοιχείο σε κάθε κατηγορία. Προσαρμόστε τον τύπο και τον υποτύπο εφέ όπως απαιτείται.

## Βήμα 5: Αποθηκεύστε την Παρουσίαση

```java
presentation.save(dataDir + "AnimatingCategoriesElements_out.pptx", SaveFormat.Pptx);
```

 Τέλος, αποθηκεύστε την τροποποιημένη παρουσίαση με το κινούμενο γράφημα σε ένα νέο αρχείο. Αντικαθιστώ`"AnimatingCategoriesElements_out.pptx"` με το επιθυμητό όνομα αρχείου εξόδου.


## Πλήρης Πηγαίος Κώδικας για Κίνηση Στοιχείων Κατηγοριών σε Διαφάνειες Java
```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
try
{
	// Λάβετε αναφορά για το αντικείμενο του γραφήματος
	ISlide slide = presentation.getSlides().get_Item(0);
	IShapeCollection shapes = slide.getShapes();
	IChart chart = (IChart) shapes.get_Item(0);
	// Εμψύχωση στοιχείων κατηγοριών
	slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	// Γράψτε το αρχείο παρουσίασης στο δίσκο
	presentation.save(dataDir + "AnimatingCategoriesElements_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## συμπέρασμα

Έχετε κινήσει επιτυχώς τα στοιχεία κατηγορίας σε μια διαφάνεια Java χρησιμοποιώντας το Aspose.Slides για Java. Αυτός ο οδηγός βήμα προς βήμα σάς παρείχε τον απαραίτητο πηγαίο κώδικα και επεξηγήσεις για να επιτύχετε αυτό το εφέ κινούμενης εικόνας στις παρουσιάσεις σας στο PowerPoint. Πειραματιστείτε με διαφορετικά εφέ και ρυθμίσεις για να προσαρμόσετε περαιτέρω τα κινούμενα σχέδια σας.

## Συχνές ερωτήσεις

### Πώς μπορώ να προσαρμόσω τα εφέ κινούμενων εικόνων;

 Μπορείτε να προσαρμόσετε τα εφέ κίνησης αλλάζοντας το`EffectType` και`EffectSubtype` παραμέτρους κατά την προσθήκη εφέ στα στοιχεία του γραφήματος. Ανατρέξτε στην τεκμηρίωση Aspose.Slides for Java για περισσότερες λεπτομέρειες σχετικά με τα διαθέσιμα εφέ κινούμενων εικόνων.

### Μπορώ να εφαρμόσω αυτά τα κινούμενα σχέδια σε άλλους τύπους γραφημάτων;

Ναι, μπορείτε να εφαρμόσετε παρόμοια κινούμενα σχέδια σε άλλους τύπους γραφημάτων τροποποιώντας τον κώδικα για να στοχεύσετε τα συγκεκριμένα στοιχεία γραφήματος που θέλετε να κάνετε κίνηση. Προσαρμόστε τη δομή και τις παραμέτρους του βρόχου ανάλογα.

### Πώς μπορώ να μάθω περισσότερα για το Aspose.Slides για Java;

 Για πλήρη τεκμηρίωση και πρόσθετους πόρους, επισκεφθείτε τη διεύθυνση[Aspose.Slides for Java API Reference](https://reference.aspose.com/slides/java/) . Μπορείτε επίσης να κατεβάσετε τη βιβλιοθήκη από[εδώ](https://releases.aspose.com/slides/java/).
