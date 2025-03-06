---
title: Ορίστε τιμές ύψους τοπικής γραμματοσειράς στο PowerPoint χρησιμοποιώντας Java
linktitle: Ορίστε τιμές ύψους τοπικής γραμματοσειράς στο PowerPoint χρησιμοποιώντας Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Μάθετε πώς να προσαρμόζετε τα ύψη γραμματοσειράς σε παρουσιάσεις PowerPoint χρησιμοποιώντας Java με Aspose.Slides. Βελτιώστε τη μορφοποίηση κειμένου στις διαφάνειές σας χωρίς κόπο.
weight: 17
url: /el/java/java-powerpoint-text-font-customization/set-local-font-height-values-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ορίστε τιμές ύψους τοπικής γραμματοσειράς στο PowerPoint χρησιμοποιώντας Java

## Εισαγωγή
Σε αυτό το σεμινάριο, θα μάθετε πώς να χειρίζεστε τα ύψη γραμματοσειράς σε διάφορα επίπεδα στις παρουσιάσεις του PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Ο έλεγχος των μεγεθών γραμματοσειρών είναι ζωτικής σημασίας για τη δημιουργία οπτικά ελκυστικών και δομημένων παρουσιάσεων. Θα περιηγηθούμε σε παραδείγματα βήμα προς βήμα για να δείξουμε πώς να ορίσετε ύψη γραμματοσειράς για διαφορετικά στοιχεία κειμένου.
## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα εξής:
- Το Java Development Kit (JDK) είναι εγκατεστημένο στο σύστημά σας
-  Aspose.Slides για βιβλιοθήκη Java. Μπορείτε να το κατεβάσετε[εδώ](https://releases.aspose.com/slides/java/).
- Βασική κατανόηση προγραμματισμού Java και παρουσιάσεων PowerPoint
## Εισαγωγή πακέτων
Φροντίστε να συμπεριλάβετε τα απαραίτητα πακέτα Aspose.Slides στο αρχείο Java σας:
```java
import com.aspose.slides.*;
```
## Βήμα 1: Αρχικοποίηση ενός αντικειμένου παρουσίασης
Αρχικά, δημιουργήστε ένα νέο αντικείμενο παρουσίασης PowerPoint:
```java
Presentation pres = new Presentation();
```
## Βήμα 2: Προσθέστε ένα πλαίσιο σχήματος και κειμένου
Προσθέστε ένα αυτόματο σχήμα με ένα πλαίσιο κειμένου στην πρώτη διαφάνεια:
```java
IAutoShape newShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 400, 75, false);
newShape.addTextFrame("");
```
## Βήμα 3: Δημιουργήστε τμήματα κειμένου
Ορίστε τμήματα κειμένου με διαφορετικά ύψη γραμματοσειράς:
```java
IPortion portion0 = new Portion("Sample text with first portion");
IPortion portion1 = new Portion(" and second portion.");
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion0);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion1);
```
## Βήμα 4: Ορίστε ύψη γραμματοσειράς
Ορίστε ύψη γραμματοσειράς σε διαφορετικά επίπεδα:
```java
pres.getDefaultTextStyle().getLevel(0).getDefaultPortionFormat().setFontHeight(24);
newShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().getDefaultPortionFormat().setFontHeight(40);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(55);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(1).getPortionFormat().setFontHeight(18);
```
## Βήμα 5: Αποθηκεύστε την Παρουσίαση
Αποθηκεύστε την τροποποιημένη παρουσίαση σε ένα αρχείο:
```java
pres.save("YourOutputDirectory/SetLocalFontHeightValues.pptx", SaveFormat.Pptx);
```

## συμπέρασμα
Αυτό το σεμινάριο έδειξε πώς να προσαρμόζετε τα ύψη γραμματοσειράς στις διαφάνειες του PowerPoint μέσω προγραμματισμού χρησιμοποιώντας το Aspose.Slides για Java. Με το χειρισμό μεγεθών γραμματοσειρών σε διαφορετικά επίπεδα (σε όλη την παρουσίαση, παράγραφο και τμήμα), μπορείτε να επιτύχετε ακριβή έλεγχο της μορφοποίησης κειμένου στις παρουσιάσεις σας.
## Συχνές ερωτήσεις
### Τι είναι το Aspose.Slides για Java;
Το Aspose.Slides για Java είναι ένα ισχυρό API για τον προγραμματισμό των παρουσιάσεων του PowerPoint.
### Πού μπορώ να βρω τεκμηρίωση για το Aspose.Slides για Java;
 Μπορείτε να βρείτε την τεκμηρίωση[εδώ](https://reference.aspose.com/slides/java/).
### Μπορώ να δοκιμάσω το Aspose.Slides για Java πριν το αγοράσω;
 Ναι, μπορείτε να λάβετε μια δωρεάν δοκιμή[εδώ](https://releases.aspose.com/).
### Πώς μπορώ να λάβω υποστήριξη για το Aspose.Slides για Java;
 Για υποστήριξη, επισκεφθείτε το[Φόρουμ Aspose.Slides](https://forum.aspose.com/c/slides/11).
### Πού μπορώ να αγοράσω άδεια χρήσης για το Aspose.Slides για Java;
 Μπορείτε να αγοράσετε μια άδεια[εδώ](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
