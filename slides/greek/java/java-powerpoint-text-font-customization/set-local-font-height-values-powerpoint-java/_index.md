---
"description": "Μάθετε πώς να προσαρμόζετε το ύψος των γραμματοσειρών σε παρουσιάσεις PowerPoint χρησιμοποιώντας Java με Aspose.Slides. Βελτιώστε τη μορφοποίηση κειμένου στις διαφάνειές σας χωρίς κόπο."
"linktitle": "Ορισμός τιμών ύψους τοπικής γραμματοσειράς στο PowerPoint χρησιμοποιώντας Java"
"second_title": "Aspose.Slides API επεξεργασίας Java PowerPoint"
"title": "Ορισμός τιμών ύψους τοπικής γραμματοσειράς στο PowerPoint χρησιμοποιώντας Java"
"url": "/el/java/java-powerpoint-text-font-customization/set-local-font-height-values-powerpoint-java/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ορισμός τιμών ύψους τοπικής γραμματοσειράς στο PowerPoint χρησιμοποιώντας Java

## Εισαγωγή
Σε αυτό το σεμινάριο, θα μάθετε πώς να χειρίζεστε τα ύψη γραμματοσειρών σε διάφορα επίπεδα σε παρουσιάσεις PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Ο έλεγχος των μεγεθών γραμματοσειρών είναι ζωτικής σημασίας για τη δημιουργία οπτικά ελκυστικών και δομημένων παρουσιάσεων. Θα δούμε αναλυτικά παραδείγματα για να δείξουμε πώς να ορίσετε ύψη γραμματοσειράς για διαφορετικά στοιχεία κειμένου.
## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα εξής:
- Κιτ Ανάπτυξης Java (JDK) εγκατεστημένο στο σύστημά σας
- Aspose.Slides για τη βιβλιοθήκη Java. Μπορείτε να το κατεβάσετε. [εδώ](https://releases.aspose.com/slides/java/).
- Βασική κατανόηση προγραμματισμού Java και παρουσιάσεων PowerPoint
## Εισαγωγή πακέτων
Βεβαιωθείτε ότι έχετε συμπεριλάβει τα απαραίτητα πακέτα Aspose.Slides στο αρχείο Java σας:
```java
import com.aspose.slides.*;
```
## Βήμα 1: Αρχικοποίηση ενός αντικειμένου παρουσίασης
Αρχικά, δημιουργήστε ένα νέο αντικείμενο παρουσίασης PowerPoint:
```java
Presentation pres = new Presentation();
```
## Βήμα 2: Προσθήκη σχήματος και πλαισίου κειμένου
Προσθήκη αυτόματου σχήματος με πλαίσιο κειμένου στην πρώτη διαφάνεια:
```java
IAutoShape newShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 400, 75, false);
newShape.addTextFrame("");
```
## Βήμα 3: Δημιουργία τμημάτων κειμένου
Ορίστε τμήματα κειμένου με διαφορετικά ύψη γραμματοσειράς:
```java
IPortion portion0 = new Portion("Sample text with first portion");
IPortion portion1 = new Portion(" and second portion.");
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion0);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion1);
```
## Βήμα 4: Ορισμός ύψους γραμματοσειράς
Ορίστε ύψη γραμματοσειράς σε διαφορετικά επίπεδα:
```java
pres.getDefaultTextStyle().getLevel(0).getDefaultPortionFormat().setFontHeight(24);
newShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().getDefaultPortionFormat().setFontHeight(40);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(55);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(1).getPortionFormat().setFontHeight(18);
```
## Βήμα 5: Αποθήκευση της παρουσίασης
Αποθηκεύστε την τροποποιημένη παρουσίαση σε ένα αρχείο:
```java
pres.save("YourOutputDirectory/SetLocalFontHeightValues.pptx", SaveFormat.Pptx);
```

## Σύναψη
Αυτό το σεμινάριο έδειξε πώς να προσαρμόσετε τα ύψη των γραμματοσειρών σε διαφάνειες του PowerPoint μέσω προγραμματισμού χρησιμοποιώντας το Aspose.Slides για Java. Χειριζόμενοι τα μεγέθη των γραμματοσειρών σε διαφορετικά επίπεδα (σε ολόκληρη την παρουσίαση, σε παράγραφο και σε τμήμα), μπορείτε να επιτύχετε ακριβή έλεγχο της μορφοποίησης κειμένου στις παρουσιάσεις σας.
## Συχνές ερωτήσεις
### Τι είναι το Aspose.Slides για Java;
Το Aspose.Slides για Java είναι ένα ισχυρό API για τον προγραμματισμό παρουσιάσεων PowerPoint.
### Πού μπορώ να βρω τεκμηρίωση για το Aspose.Slides για Java;
Μπορείτε να βρείτε την τεκμηρίωση [εδώ](https://reference.aspose.com/slides/java/).
### Μπορώ να δοκιμάσω το Aspose.Slides για Java πριν το αγοράσω;
Ναι, μπορείτε να λάβετε μια δωρεάν δοκιμή [εδώ](https://releases.aspose.com/).
### Πώς μπορώ να λάβω υποστήριξη για το Aspose.Slides για Java;
Για υποστήριξη, επισκεφθείτε την [Φόρουμ Aspose.Slides](https://forum.aspose.com/c/slides/11).
### Πού μπορώ να αγοράσω μια άδεια χρήσης για το Aspose.Slides για Java;
Μπορείτε να αγοράσετε μια άδεια χρήσης [εδώ](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}