---
title: Προσθήκη στήλης σε πλαίσια κειμένου με το Aspose.Slides για Java
linktitle: Προσθήκη στήλης σε πλαίσια κειμένου με το Aspose.Slides για Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Μάθετε πώς να προσθέτετε στήλες σε πλαίσια κειμένου στο PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Βελτιώστε τις παρουσιάσεις σας με αυτόν τον οδηγό βήμα προς βήμα.
weight: 10
url: /el/java/java-powerpoint-text-box-manipulation/add-column-in-text-boxes/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Εισαγωγή
Σε αυτό το σεμινάριο, θα διερευνήσουμε πώς να βελτιώσουμε τα πλαίσια κειμένου προσθέτοντας στήλες χρησιμοποιώντας το Aspose.Slides για Java. Το Aspose.Slides είναι μια ισχυρή βιβλιοθήκη Java που επιτρέπει στους προγραμματιστές να δημιουργούν, να χειρίζονται και να μετατρέπουν παρουσιάσεις PowerPoint μέσω προγραμματισμού χωρίς να απαιτείται το Microsoft Office. Η προσθήκη στηλών σε πλαίσια κειμένου μπορεί να βελτιώσει σημαντικά την αναγνωσιμότητα και την οργάνωση του περιεχομένου μέσα στις διαφάνειες, κάνοντας τις παρουσιάσεις σας πιο ελκυστικές και επαγγελματικές.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
- Βασικές γνώσεις προγραμματισμού Java.
- Το JDK (Java Development Kit) είναι εγκατεστημένο στο μηχάνημά σας.
-  Aspose.Slides για βιβλιοθήκη Java. Μπορείτε να το κατεβάσετε από[εδώ](https://releases.aspose.com/slides/java/).

## Εισαγωγή πακέτων
Για να ξεκινήσετε, πρέπει να εισαγάγετε τις απαραίτητες κλάσεις Aspose.Slides στο αρχείο Java σας. Δείτε πώς μπορείτε να το κάνετε:
```java
import com.aspose.slides.*;
```
## Βήμα 1: Αρχικοποίηση παρουσίασης και διαφάνειας
Αρχικά, δημιουργήστε μια νέα παρουσίαση PowerPoint και αρχικοποιήστε την πρώτη διαφάνεια.
```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try {
    // Λάβετε την πρώτη διαφάνεια της παρουσίασης
    ISlide slide = presentation.getSlides().get_Item(0);
```
## Βήμα 2: Προσθήκη AutoShape (Ορθογώνιο)
Στη συνέχεια, προσθέστε έναν τύπο AutoShape of Rectangle στη διαφάνεια.
```java
    // Προσθέστε ένα AutoShape τύπου Rectangle
    IAutoShape aShape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 300, 300);
```
## Βήμα 3: Προσθέστε το TextFrame στο ορθογώνιο
Τώρα, προσθέστε ένα TextFrame στο Rectangle AutoShape και ορίστε το αρχικό του κείμενο.
```java
    // Προσθέστε το TextFrame στο ορθογώνιο
    aShape.addTextFrame("All these columns are limited to be within a single text container -- " +
            "you can add or delete text and the new or remaining text automatically adjusts " +
            "itself to flow within the container. You cannot have text flow from one container " +
            "to other though -- we told you PowerPoint's column options for text are limited!");
```
## Βήμα 4: Ορίστε τον αριθμό στηλών
Καθορίστε τον αριθμό των στηλών μέσα στο TextFrame.
```java
    // Λάβετε τη μορφή κειμένου του TextFrame
    ITextFrameFormat format = aShape.getTextFrame().getTextFrameFormat();
    // Καθορίστε τον αριθμό των στηλών στο TextFrame
    format.setColumnCount(3);
```
## Βήμα 5: Προσαρμόστε το διάστημα στηλών
Ορίστε την απόσταση μεταξύ των στηλών στο TextFrame.
```java
    // Καθορίστε την απόσταση μεταξύ των στηλών
    format.setColumnSpacing(10);
```
## Βήμα 6: Αποθηκεύστε την παρουσίαση
Τέλος, αποθηκεύστε την τροποποιημένη παρουσίαση σε αρχείο PowerPoint.
```java
    // Αποθηκεύστε την παρουσίαση που δημιουργήθηκε
    presentation.save(dataDir + "ColumnCount.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```

## συμπέρασμα
Ακολουθώντας αυτά τα βήματα, μπορείτε εύκολα να προσθέσετε στήλες σε πλαίσια κειμένου σε παρουσιάσεις PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Αυτή η δυνατότητα σάς επιτρέπει να βελτιώσετε τη δομή και την αναγνωσιμότητα των διαφανειών σας, καθιστώντας τις πιο ελκυστικές και επαγγελματικές.
## Συχνές ερωτήσεις
### Μπορώ να προσθέσω περισσότερες από τρεις στήλες σε ένα πλαίσιο κειμένου;
Ναι, μπορείτε να καθορίσετε οποιονδήποτε αριθμό στηλών μέσω προγραμματισμού χρησιμοποιώντας το Aspose.Slides.
### Είναι το Aspose.Slides συμβατό με Java 11;
Ναι, το Aspose.Slides υποστηρίζει Java 11 και νεότερες εκδόσεις.
### Πώς μπορώ να αποκτήσω μια προσωρινή άδεια για το Aspose.Slides;
 Μπορείτε να αποκτήσετε μια προσωρινή άδεια[εδώ](https://purchase.aspose.com/temporary-license/).
### Απαιτείται εγκατάσταση του Microsoft Office για Aspose.Slides;
Όχι, το Aspose.Slides δεν απαιτεί εγκατάσταση του Microsoft Office στο μηχάνημα.
### Πού μπορώ να βρω περισσότερη τεκμηρίωση σχετικά με το Aspose.Slides για Java;
 Λεπτομερής τεκμηρίωση είναι διαθέσιμη[εδώ](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
