---
title: Διαχείριση κουκκίδων εικόνων παραγράφου σε Java PowerPoint
linktitle: Διαχείριση κουκκίδων εικόνων παραγράφου σε Java PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: Μάθετε πώς να προσθέτετε προσαρμοσμένες κουκκίδες εικόνας σε διαφάνειες του PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Ακολουθήστε αυτόν τον λεπτομερή, βήμα προς βήμα οδηγό για απρόσκοπτη ενσωμάτωση.
weight: 11
url: /el/java/java-powerpoint-advanced-paragraph-font-properties/manage-paragraph-picture-bullets-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Διαχείριση κουκκίδων εικόνων παραγράφου σε Java PowerPoint

## Εισαγωγή
Η δημιουργία ελκυστικών και οπτικά ελκυστικών παρουσιάσεων είναι μια κρίσιμη δεξιότητα στον σύγχρονο επιχειρηματικό κόσμο. Οι προγραμματιστές Java μπορούν να αξιοποιήσουν το Aspose.Slides για να βελτιώσουν τις παρουσιάσεις τους με προσαρμοσμένες κουκκίδες εικόνας σε διαφάνειες PowerPoint. Αυτό το σεμινάριο θα σας καθοδηγήσει στη διαδικασία βήμα προς βήμα, διασφαλίζοντας ότι μπορείτε να προσθέσετε με σιγουριά κουκκίδες εικόνων στις παρουσιάσεις σας.
## Προαπαιτούμενα
Πριν ξεκινήσετε το σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
- Εγκαταστάθηκε το Java Development Kit (JDK).
- Ολοκληρωμένο περιβάλλον ανάπτυξης (IDE) όπως το Eclipse ή το IntelliJ IDEA
- Aspose.Slides για βιβλιοθήκη Java
- Βασικές γνώσεις προγραμματισμού Java
- Αρχείο εικόνας για την εικόνα με κουκκίδες
 Για να πραγματοποιήσετε λήψη της βιβλιοθήκης Aspose.Slides for Java, επισκεφτείτε το[σελίδα λήψης](https://releases.aspose.com/slides/java/) . Για τεκμηρίωση, ελέγξτε το[τεκμηρίωση](https://reference.aspose.com/slides/java/).
## Εισαγωγή πακέτων
Αρχικά, βεβαιωθείτε ότι έχετε εισαγάγει τα απαραίτητα πακέτα για το έργο σας. Προσθέστε τις ακόλουθες εισαγωγές στην αρχή του αρχείου Java:
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
Ας αναλύσουμε τη διαδικασία σε διαχειρίσιμα βήματα.
## Βήμα 1: Ρυθμίστε τον κατάλογο του έργου σας
Δημιουργήστε έναν νέο κατάλογο για το έργο σας. Αυτός ο κατάλογος θα περιέχει το αρχείο Java, τη βιβλιοθήκη Aspose.Slides και το αρχείο εικόνας για τη κουκκίδα.
```java
String dataDir = "Your Document Directory";
```
## Βήμα 2: Αρχικοποιήστε την Παρουσίαση
 Αρχικοποιήστε μια νέα παρουσία του`Presentation` τάξη. Αυτό το αντικείμενο αντιπροσωπεύει την παρουσίασή σας στο PowerPoint.
```java
Presentation presentation = new Presentation();
```
## Βήμα 3: Πρόσβαση στην Πρώτη Διαφάνεια
Αποκτήστε πρόσβαση στην πρώτη διαφάνεια της παρουσίασης. Οι διαφάνειες έχουν μηδενικό ευρετήριο, επομένως η πρώτη διαφάνεια βρίσκεται στο δείκτη 0.
```java
ISlide slide = presentation.getSlides().get_Item(0);
```
## Βήμα 4: Φορτώστε την εικόνα Bullet
Φορτώστε την εικόνα που θέλετε να χρησιμοποιήσετε για τις κουκκίδες. Αυτή η εικόνα πρέπει να τοποθετηθεί στον κατάλογο του έργου σας.
```java
BufferedImage image = ImageIO.read(new File(dataDir + "bullets.png"));
IPPImage ippxImage = presentation.getImages().addImage(image);
```
## Βήμα 5: Προσθέστε ένα AutoShape στη Διαφάνεια
Προσθέστε ένα AutoShape στη διαφάνεια. Το σχήμα θα περιέχει το κείμενο με τις προσαρμοσμένες κουκκίδες.
```java
IAutoShape autoShape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
```
## Βήμα 6: Πρόσβαση στο Πλαίσιο κειμένου
Αποκτήστε πρόσβαση στο πλαίσιο κειμένου του AutoShape για να χειριστείτε τις παραγράφους του.
```java
ITextFrame textFrame = autoShape.getTextFrame();
```
## Βήμα 7: Καταργήστε την προεπιλεγμένη παράγραφο
Καταργήστε την προεπιλεγμένη παράγραφο που προστίθεται αυτόματα στο πλαίσιο κειμένου.
```java
textFrame.getParagraphs().removeAt(0);
```
## Βήμα 8: Δημιουργήστε μια νέα παράγραφο
Δημιουργήστε μια νέα παράγραφο και ορίστε το κείμενό της. Αυτή η παράγραφος θα περιέχει τις προσαρμοσμένες κουκκίδες εικόνας.
```java
Paragraph paragraph = new Paragraph();
paragraph.setText("Welcome to Aspose.Slides");
```
## Βήμα 9: Ορισμός στυλ και εικόνας κουκκίδων
Ρυθμίστε το στυλ κουκκίδας για χρήση της προσαρμοσμένης εικόνας που φορτώθηκε νωρίτερα.
```java
paragraph.getParagraphFormat().getBullet().setType(BulletType.Picture);
paragraph.getParagraphFormat().getBullet().getPicture().setImage(ippxImage);
```
## Βήμα 10: Προσαρμόστε το ύψος της σφαίρας
Ρυθμίστε το ύψος της σφαίρας για να βεβαιωθείτε ότι φαίνεται καλά στην παρουσίαση.
```java
paragraph.getParagraphFormat().getBullet().setHeight(100);
```
## Βήμα 11: Προσθέστε την παράγραφο στο πλαίσιο κειμένου
Προσθέστε τη νέα παράγραφο που δημιουργήθηκε στο πλαίσιο κειμένου του AutoShape.
```java
textFrame.getParagraphs().add(paragraph);
```
## Βήμα 12: Αποθηκεύστε την παρουσίαση
Τέλος, αποθηκεύστε την παρουσίαση ως αρχείο PPTX και PPT.
```java
presentation.save(dataDir + "ParagraphPictureBulletsPPTX_out.pptx", SaveFormat.Pptx);
presentation.save(dataDir + "ParagraphPictureBulletsPPT_out.ppt", SaveFormat.Ppt);
```
## συμπέρασμα
 Και εκεί το έχετε! Ακολουθώντας αυτά τα βήματα, μπορείτε εύκολα να προσθέσετε προσαρμοσμένες κουκκίδες εικόνας στις παρουσιάσεις σας στο PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Αυτή η ισχυρή βιβλιοθήκη προσφέρει ένα ευρύ φάσμα δυνατοτήτων για να σας βοηθήσει να δημιουργήσετε επαγγελματικές και οπτικά ελκυστικές παρουσιάσεις. Μην ξεχάσετε να εξερευνήσετε το[τεκμηρίωση](https://reference.aspose.com/slides/java/)για πιο προηγμένες δυνατότητες και επιλογές προσαρμογής.
## Συχνές ερωτήσεις
### Τι είναι το Aspose.Slides για Java;
Το Aspose.Slides for Java είναι μια ισχυρή βιβλιοθήκη που επιτρέπει στους προγραμματιστές Java να δημιουργούν, να τροποποιούν και να χειρίζονται παρουσιάσεις PowerPoint μέσω προγραμματισμού.
### Μπορώ να χρησιμοποιήσω οποιαδήποτε εικόνα για τις κουκκίδες εικόνας;
Ναι, μπορείτε να χρησιμοποιήσετε οποιαδήποτε εικόνα για τις κουκκίδες εικόνας, αρκεί να είναι προσβάσιμη από τον κατάλογο του έργου σας.
### Χρειάζομαι άδεια χρήσης για να χρησιμοποιήσω το Aspose.Slides για Java;
 Το Aspose.Slides για Java απαιτεί άδεια χρήσης για πλήρη λειτουργικότητα. Μπορείτε να αποκτήσετε προσωρινή άδεια από[εδώ](https://purchase.aspose.com/temporary-license/) ή αγοράστε μια πλήρη άδεια[εδώ](https://purchase.aspose.com/buy).
### Μπορώ να προσθέσω πολλές παραγράφους με διαφορετικά στυλ κουκκίδων σε ένα AutoShape;
Ναι, μπορείτε να προσθέσετε πολλές παραγράφους με διαφορετικά στυλ κουκκίδων σε ένα μεμονωμένο AutoShape δημιουργώντας και διαμορφώνοντας κάθε παράγραφο ξεχωριστά.
### Πού μπορώ να βρω περισσότερα παραδείγματα και υποστήριξη;
 Μπορείτε να βρείτε περισσότερα παραδείγματα στο[τεκμηρίωση](https://reference.aspose.com/slides/java/) και λάβετε υποστήριξη από την κοινότητα Aspose στο[φόρουμ](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
