---
title: Προσθέστε κείμενο εκθέτη και δευτερεύοντος κειμένου στο Java PowerPoint
linktitle: Προσθέστε κείμενο εκθέτη και δευτερεύοντος κειμένου στο Java PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: Μάθετε πώς να προσθέτετε κείμενο εκθέτη και δείκτη σε παρουσιάσεις Java PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Ιδανικό για τη βελτίωση των διαφανειών σας.
weight: 13
url: /el/java/java-powerpoint-text-box-manipulation/add-superscript-subscript-text-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Εισαγωγή
Η δημιουργία συναρπαστικών και ενημερωτικών παρουσιάσεων του PowerPoint απαιτεί συχνά τη χρήση χαρακτηριστικών μορφοποίησης, όπως το εκθέτη και το υπόδειγμα κειμένου. Αυτό το σεμινάριο θα σας καθοδηγήσει στη διαδικασία ενσωμάτωσης κειμένου εκθέτη και δείκτη στις παρουσιάσεις Java PowerPoint χρησιμοποιώντας το Aspose.Slides για Java.
## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα εξής:
- Το Java Development Kit (JDK) είναι εγκατεστημένο στο σύστημά σας.
-  Aspose.Slides για βιβλιοθήκη Java. Μπορείτε να το κατεβάσετε από[εδώ](https://releases.aspose.com/slides/java/).
- Ένα ολοκληρωμένο περιβάλλον ανάπτυξης (IDE) όπως το IntelliJ IDEA ή το Eclipse που έχει ρυθμιστεί για ανάπτυξη Java.
- Βασική εξοικείωση με προγραμματισμό Java και παρουσιάσεις PowerPoint.

## Εισαγωγή πακέτων
Αρχικά, εισαγάγετε τα απαραίτητα πακέτα από το Aspose.Slides για Java:
```java
import com.aspose.slides.*;
```
## Βήμα 1: Ρυθμίστε την παρουσίαση
```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## Βήμα 2: Πρόσβαση στη Διαφάνεια
```java
// Αποκτήστε την πρώτη διαφάνεια
ISlide slide = presentation.getSlides().get_Item(0);
```
## Βήμα 3: Δημιουργήστε ένα πλαίσιο κειμένου
```java
// Δημιουργήστε ένα AutoShape για να χρησιμεύσει ως πλαίσιο κειμένου
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
ITextFrame textFrame = shape.getTextFrame();
textFrame.getParagraphs().clear();
```
## Βήμα 4: Προσθήκη εκθέτη κειμένου
```java
// Δημιουργήστε μια παράγραφο για το κύριο κείμενο
IParagraph mainParagraph = new Paragraph();
IPortion mainPortion = new Portion();
mainPortion.setText("SlideTitle");
mainParagraph.getPortions().add(mainPortion);
// Δημιουργήστε ένα τμήμα για το κείμενο του εκθέτη
IPortion superPortion = new Portion();
superPortion.getPortionFormat().setEscapement(30); // Ορισμός διαφυγής για εκθέτη
superPortion.setText("TM");
mainParagraph.getPortions().add(superPortion);
//Προσθέστε την κύρια παράγραφο με τον εκθέτη στο πλαίσιο κειμένου
textFrame.getParagraphs().add(mainParagraph);
```
## Βήμα 5: Προσθέστε κείμενο συνδρομής
```java
// Δημιουργήστε μια άλλη παράγραφο για κείμενο δείκτη
IParagraph subscriptParagraph = new Paragraph();
IPortion subscriptPortion = new Portion();
subscriptPortion.setText("a");
subscriptParagraph.getPortions().add(subscriptPortion);
// Δημιουργήστε ένα τμήμα για το κείμενο του δείκτη
IPortion subPortion = new Portion();
subPortion.getPortionFormat().setEscapement(-25); // Ορισμός διαφυγής για δείκτη
subPortion.setText("i");
subscriptParagraph.getPortions().add(subPortion);
// Προσθέστε τη δευτερεύουσα παράγραφο στο πλαίσιο κειμένου
textFrame.getParagraphs().add(subscriptParagraph);
```
## Βήμα 6: Αποθηκεύστε την παρουσίαση
```java
// Αποθηκεύστε την παρουσίαση
presentation.save(dataDir + "TestOut.pptx", SaveFormat.Pptx);
```

## συμπέρασμα
Σε αυτό το σεμινάριο, εξερευνήσαμε πώς να βελτιώσετε τις παρουσιάσεις Java PowerPoint με κείμενο εκθέτη και δείκτη χρησιμοποιώντας το Aspose.Slides για Java. Ακολουθώντας αυτά τα βήματα, μπορείτε να δημιουργήσετε πιο ελκυστικές και ενημερωτικές διαφάνειες που επικοινωνούν αποτελεσματικά το περιεχόμενό σας.

## Συχνές ερωτήσεις
### Τι είναι το Aspose.Slides για Java;
Το Aspose.Slides for Java είναι μια ισχυρή βιβλιοθήκη που επιτρέπει στους προγραμματιστές να δημιουργούν, να χειρίζονται και να μετατρέπουν παρουσιάσεις PowerPoint μέσω προγραμματισμού.
### Πού μπορώ να βρω περισσότερη τεκμηρίωση για το Aspose.Slides for Java;
 Μπορείτε να βρείτε αναλυτική τεκμηρίωση[εδώ](https://reference.aspose.com/slides/java/).
### Πώς μπορώ να αποκτήσω μια προσωρινή άδεια χρήσης για το Aspose.Slides για Java;
 Μπορείτε να πάρετε μια προσωρινή άδεια[εδώ](https://purchase.aspose.com/temporary-license/).
### Μπορώ να δοκιμάσω το Aspose.Slides για Java δωρεάν;
 Ναι, μπορείτε να κάνετε λήψη μιας δωρεάν δοκιμαστικής έκδοσης από[εδώ](https://releases.aspose.com/).
### Πού μπορώ να λάβω υποστήριξη για το Aspose.Slides για Java;
 Για υποστήριξη και συζητήσεις, επισκεφτείτε το[Φόρουμ Aspose.Slides](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
