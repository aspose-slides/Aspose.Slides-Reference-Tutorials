---
"description": "Μάθετε πώς να ορίζετε προσαρμοσμένες επιλογές υπομνήματος σε διαφάνειες Java χρησιμοποιώντας το Aspose.Slides για Java. Προσαρμόστε τη θέση και το μέγεθος του υπομνήματος στα γραφήματα PowerPoint."
"linktitle": "Ορισμός προσαρμοσμένων επιλογών υπομνήματος σε διαφάνειες Java"
"second_title": "Aspose.Slides API επεξεργασίας Java PowerPoint"
"title": "Ορισμός προσαρμοσμένων επιλογών υπομνήματος σε διαφάνειες Java"
"url": "/el/java/customization-and-formatting/set-legend-custom-options-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ορισμός προσαρμοσμένων επιλογών υπομνήματος σε διαφάνειες Java


## Εισαγωγή στις προσαρμοσμένες επιλογές ορισμού υπομνήματος σε διαφάνειες Java

Σε αυτό το σεμινάριο, θα δείξουμε πώς να προσαρμόσετε τις ιδιότητες του υπομνήματος ενός γραφήματος σε μια παρουσίαση PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Μπορείτε να τροποποιήσετε τη θέση, το μέγεθος και άλλα χαρακτηριστικά του υπομνήματος ώστε να ταιριάζουν στις ανάγκες της παρουσίασής σας.

## Προαπαιτούμενα

Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα εξής:

- Εγκατεστημένο το Aspose.Slides για το Java API.
- Ρύθμιση περιβάλλοντος ανάπτυξης Java.

## Βήμα 1: Εισαγωγή απαραίτητων κλάσεων:

```java
// Εισαγωγή Aspose.Slides για κλάσεις Java
import com.aspose.slides.*;
```

## Βήμα 2: Καθορίστε τη διαδρομή προς τον κατάλογο εγγράφων σας:

```java
String dataDir = "Your Document Directory";
```

## Βήμα 3: Δημιουργήστε μια παρουσία του `Presentation` τάξη:

```java
Presentation presentation = new Presentation();
```

## Βήμα 4: Προσθήκη διαφάνειας στην παρουσίαση:

```java
try {
    ISlide slide = presentation.getSlides().get_Item(0);
```

## Βήμα 5: Προσθέστε ένα γράφημα ομαδοποιημένων στηλών στη διαφάνεια:

```java
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
```

## Βήμα 6. Ορισμός ιδιοτήτων υπομνήματος:

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

## Βήμα 7: Αποθήκευση της παρουσίασης στο δίσκο:

```java
    presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```

Αυτό ήταν! Προσαρμόσατε με επιτυχία τις ιδιότητες υπομνήματος ενός γραφήματος σε μια παρουσίαση PowerPoint χρησιμοποιώντας το Aspose.Slides για Java.

## Πλήρης πηγαίος κώδικας για προσαρμοσμένες επιλογές ορισμού υπομνήματος σε διαφάνειες Java

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
// Δημιουργήστε μια παρουσία της κλάσης Presentation
Presentation presentation = new Presentation();
try
{
	// Λήψη αναφοράς της διαφάνειας
	ISlide slide = presentation.getSlides().get_Item(0);
	// Προσθήκη γραφήματος ομαδοποιημένων στηλών στη διαφάνεια
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
	// Ορισμός ιδιοτήτων υπομνήματος
	chart.getLegend().setX(50 / chart.getWidth());
	chart.getLegend().setY(50 / chart.getHeight());
	chart.getLegend().setWidth(100 / chart.getWidth());
	chart.getLegend().setHeight(100 / chart.getHeight());
	// Εγγραφή παρουσίασης σε δίσκο
	presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```
## Σύναψη

Σε αυτό το σεμινάριο, μάθαμε πώς να προσαρμόζουμε τις ιδιότητες του υπομνήματος ενός γραφήματος σε μια παρουσίαση PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Μπορείτε να τροποποιήσετε τη θέση, το μέγεθος και άλλα χαρακτηριστικά του υπομνήματος για να δημιουργήσετε οπτικά ελκυστικές και ενημερωτικές παρουσιάσεις.

## Συχνές ερωτήσεις

## Πώς μπορώ να αλλάξω τη θέση του υπομνήματος;

Για να αλλάξετε τη θέση του υπομνήματος, χρησιμοποιήστε το `setX` και `setY` μέθοδοι του αντικειμένου υπομνήματος. Οι τιμές καθορίζονται σε σχέση με το πλάτος και το ύψος του γραφήματος.

## Πώς μπορώ να προσαρμόσω το μέγεθος του υπομνήματος;

Μπορείτε να προσαρμόσετε το μέγεθος του υπομνήματος χρησιμοποιώντας το `setWidth` και `setHeight` μεθόδους του αντικειμένου υπομνήματος. Αυτές οι τιμές είναι επίσης σχετικές με το πλάτος και το ύψος του γραφήματος.

## Μπορώ να προσαρμόσω άλλα χαρακτηριστικά υπομνήματος;

Ναι, μπορείτε να προσαρμόσετε διάφορα χαρακτηριστικά του υπομνήματος, όπως το στυλ γραμματοσειράς, το περίγραμμα, το χρώμα φόντου και άλλα. Εξερευνήστε την τεκμηρίωση του Aspose.Slides για λεπτομερείς πληροφορίες σχετικά με την προσαρμογή των υπομνημάτων.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}