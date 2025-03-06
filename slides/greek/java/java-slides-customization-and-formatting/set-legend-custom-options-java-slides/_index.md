---
title: Ορισμός προσαρμοσμένων επιλογών Legend στις διαφάνειες Java
linktitle: Ορισμός προσαρμοσμένων επιλογών Legend στις διαφάνειες Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Μάθετε πώς να ορίζετε προσαρμοσμένες επιλογές υπομνήματος σε διαφάνειες Java χρησιμοποιώντας το Aspose.Slides για Java. Προσαρμόστε τη θέση και το μέγεθος του υπομνήματος στα γραφήματα του PowerPoint.
weight: 14
url: /el/java/customization-and-formatting/set-legend-custom-options-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Εισαγωγή στο Set Legend Custom Options σε Java Slides

Σε αυτό το σεμινάριο, θα δείξουμε πώς μπορείτε να προσαρμόσετε τις ιδιότητες υπομνήματος ενός γραφήματος σε μια παρουσίαση PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Μπορείτε να τροποποιήσετε τη θέση, το μέγεθος και άλλα χαρακτηριστικά του μύθου για να ταιριάζουν στις ανάγκες παρουσίασής σας.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα ακόλουθα:

- Το Aspose.Slides for Java API έχει εγκατασταθεί.
- Ρύθμιση περιβάλλοντος ανάπτυξης Java.

## Βήμα 1: Εισαγάγετε τις απαραίτητες τάξεις:

```java
// Εισαγωγή Aspose.Slides για κλάσεις Java
import com.aspose.slides.*;
```

## Βήμα 2: Καθορίστε τη διαδρομή προς τον κατάλογο εγγράφων σας:

```java
String dataDir = "Your Document Directory";
```

##  Βήμα 3: Δημιουργήστε μια παρουσία του`Presentation` class:

```java
Presentation presentation = new Presentation();
```

## Βήμα 4: Προσθέστε μια διαφάνεια στην παρουσίαση:

```java
try {
    ISlide slide = presentation.getSlides().get_Item(0);
```

## Βήμα 5: Προσθέστε ένα γράφημα ομαδοποιημένης στήλης στη διαφάνεια:

```java
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
```

## Βήμα 6. Ορισμός ιδιοτήτων Legend:

- Ορίστε τη θέση X του υπομνήματος (σε σχέση με το πλάτος του γραφήματος):

```java
chart.getLegend().setX(50 / chart.getWidth());
```

- Ορίστε τη θέση Y του υπομνήματος (σε σχέση με το ύψος του γραφήματος):

```java
chart.getLegend().setY(50 / chart.getHeight());
```

- Ορίστε το πλάτος του υπομνήματος (σε σχέση με το πλάτος του γραφήματος):

```java
chart.getLegend().setWidth(100 / chart.getWidth());
```

- Ορίστε το ύψος του υπομνήματος (σε σχέση με το ύψος του γραφήματος):

```java
chart.getLegend().setHeight(100 / chart.getHeight());
```

## Βήμα 7: Αποθηκεύστε την παρουσίαση στο δίσκο:

```java
    presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```

Αυτό είναι! Προσαρμόσατε με επιτυχία τις ιδιότητες υπομνήματος ενός γραφήματος σε μια παρουσίαση PowerPoint χρησιμοποιώντας το Aspose.Slides για Java.

## Ολοκληρώστε τον πηγαίο κώδικα για το Set Legend Custom Options σε Java Slides

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
// Δημιουργήστε μια παρουσία της κλάσης παρουσίασης
Presentation presentation = new Presentation();
try
{
	// Λάβετε αναφορά για τη διαφάνεια
	ISlide slide = presentation.getSlides().get_Item(0);
	// Προσθέστε ένα γράφημα ομαδοποιημένης στήλης στη διαφάνεια
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
	// Ορισμός ιδιοτήτων μύθου
	chart.getLegend().setX(50 / chart.getWidth());
	chart.getLegend().setY(50 / chart.getHeight());
	chart.getLegend().setWidth(100 / chart.getWidth());
	chart.getLegend().setHeight(100 / chart.getHeight());
	// Γράψτε την παρουσίαση στο δίσκο
	presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```
## συμπέρασμα

Σε αυτό το σεμινάριο, μάθαμε πώς να προσαρμόζουμε τις ιδιότητες υπόμνημα ενός γραφήματος σε μια παρουσίαση PowerPoint χρησιμοποιώντας Aspose.Slides για Java. Μπορείτε να τροποποιήσετε τη θέση, το μέγεθος και άλλα χαρακτηριστικά του μύθου για να δημιουργήσετε οπτικά ελκυστικές και ενημερωτικές παρουσιάσεις.

## Συχνές ερωτήσεις

## Πώς μπορώ να αλλάξω τη θέση του θρύλου;

 Για να αλλάξετε τη θέση του μύθου, χρησιμοποιήστε το`setX` και`setY` μεθόδους του θρύλου αντικειμένου. Οι τιμές καθορίζονται σε σχέση με το πλάτος και το ύψος του γραφήματος.

## Πώς μπορώ να προσαρμόσω το μέγεθος του μύθου;

 Μπορείτε να προσαρμόσετε το μέγεθος του μύθου χρησιμοποιώντας το`setWidth` και`setHeight` μεθόδους του θρύλου αντικειμένου. Αυτές οι τιμές σχετίζονται επίσης με το πλάτος και το ύψος του γραφήματος.

## Μπορώ να προσαρμόσω άλλα χαρακτηριστικά μύθου;

Ναι, μπορείτε να προσαρμόσετε διάφορα χαρακτηριστικά του μύθου, όπως στυλ γραμματοσειράς, περίγραμμα, χρώμα φόντου και άλλα. Εξερευνήστε την τεκμηρίωση του Aspose.Slides για λεπτομερείς πληροφορίες σχετικά με την περαιτέρω προσαρμογή των μύθων.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
