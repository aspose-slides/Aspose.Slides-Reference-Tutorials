---
"description": "Μάθετε πώς να ορίσετε τη μορφή συμπλήρωσης κουκκίδων στο SmartArt χρησιμοποιώντας Java με το Aspose.Slides. Οδηγός βήμα προς βήμα για αποτελεσματικό χειρισμό παρουσιάσεων."
"linktitle": "Ορισμός μορφής γεμίσματος κουκκίδων στο SmartArt χρησιμοποιώντας Java"
"second_title": "Aspose.Slides API επεξεργασίας Java PowerPoint"
"title": "Ορισμός μορφής γεμίσματος κουκκίδων στο SmartArt χρησιμοποιώντας Java"
"url": "/el/java/java-powerpoint-smartart-manipulation/set-bullet-fill-format-smartart-java/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ορισμός μορφής γεμίσματος κουκκίδων στο SmartArt χρησιμοποιώντας Java

## Εισαγωγή
Στον τομέα του προγραμματισμού Java, ο αποτελεσματικός χειρισμός παρουσιάσεων είναι μια κοινή απαίτηση, ειδικά όταν πρόκειται για στοιχεία SmartArt. Το Aspose.Slides για Java αναδεικνύεται σε ένα ισχυρό εργαλείο για τέτοιες εργασίες, προσφέροντας μια σειρά από λειτουργίες για τον προγραμματισμό παρουσιάσεων. Σε αυτό το σεμινάριο, θα εμβαθύνουμε στη διαδικασία ορισμού της μορφής συμπλήρωσης κουκκίδων στο SmartArt χρησιμοποιώντας Java με το Aspose.Slides, βήμα προς βήμα.
## Προαπαιτούμενα
Πριν ξεκινήσουμε αυτό το σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
### Κιτ ανάπτυξης Java (JDK)
Πρέπει να έχετε εγκατεστημένο το JDK στο σύστημά σας. Μπορείτε να το κατεβάσετε από το [δικτυακός τόπος](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) και ακολουθήστε τις οδηγίες εγκατάστασης.
### Aspose.Slides για Java
Κατεβάστε και εγκαταστήστε το Aspose.Slides για Java από το [σύνδεσμος λήψης](https://releases.aspose.com/slides/java/)Ακολουθήστε τις οδηγίες εγκατάστασης που παρέχονται στην τεκμηρίωση για το συγκεκριμένο λειτουργικό σας σύστημα.

## Εισαγωγή πακέτων
Για να ξεκινήσετε, εισαγάγετε τα απαραίτητα πακέτα στο έργο Java σας:
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
#Ας αναλύσουμε το παράδειγμα που παρέχεται σε πολλά βήματα για να κατανοήσουμε καλύτερα τον τρόπο ορισμού της μορφής συμπλήρωσης κουκκίδων στο SmartArt χρησιμοποιώντας Java με Aspose.Slides.
## Βήμα 1: Δημιουργία αντικειμένου παρουσίασης
```java
Presentation presentation = new Presentation();
```
Αρχικά, δημιουργήστε μια νέα παρουσία της κλάσης Presentation, η οποία αντιπροσωπεύει μια παρουσίαση PowerPoint.
## Βήμα 2: Προσθήκη SmartArt
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 500, 400, SmartArtLayoutType.VerticalPictureList);
```
Στη συνέχεια, προσθέστε ένα σχήμα SmartArt στη διαφάνεια. Αυτή η γραμμή κώδικα αρχικοποιεί ένα νέο σχήμα SmartArt με καθορισμένες διαστάσεις και διάταξη.
## Βήμα 3: Πρόσβαση στον κόμβο SmartArt
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
Τώρα, αποκτήστε πρόσβαση στον πρώτο κόμβο (ή σε οποιονδήποτε επιθυμητό κόμβο) μέσα στο σχήμα SmartArt για να τροποποιήσετε τις ιδιότητές του.
## Βήμα 4: Ορισμός μορφής γεμίσματος με κουκκίδες
```java
if (node.getBulletFillFormat() != null) {
    BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
    IPPImage image = presentation.getImages().addImage(img);
    node.getBulletFillFormat().setFillType(FillType.Picture);
    node.getBulletFillFormat().getPictureFillFormat().getPicture().setImage(image);
    node.getBulletFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
}
```
Εδώ, ελέγχουμε αν υποστηρίζεται η μορφή συμπλήρωσης κουκκίδων. Εάν ναι, φορτώνουμε ένα αρχείο εικόνας και το ορίζουμε ως συμπλήρωση κουκκίδων για τον κόμβο SmartArt.
## Βήμα 5: Αποθήκευση παρουσίασης
```java
presentation.save(dataDir + "out.pptx", SaveFormat.Pptx);
```
Τέλος, αποθηκεύστε την τροποποιημένη παρουσίαση σε μια καθορισμένη τοποθεσία.

## Σύναψη
Συγχαρητήρια! Μάθατε με επιτυχία πώς να ορίσετε τη μορφή συμπλήρωσης κουκκίδων στο SmartArt χρησιμοποιώντας Java με το Aspose.Slides. Αυτή η δυνατότητα ανοίγει έναν κόσμο δυνατοτήτων για δυναμικές και οπτικά ελκυστικές παρουσιάσεις σε εφαρμογές Java.
## Συχνές ερωτήσεις
### Μπορώ να χρησιμοποιήσω το Aspose.Slides για Java για να δημιουργήσω παρουσιάσεις από την αρχή;
Απολύτως! Το Aspose.Slides παρέχει ολοκληρωμένα API για τη δημιουργία, την τροποποίηση και τον χειρισμό παρουσιάσεων εξ ολοκλήρου μέσω κώδικα.
### Είναι το Aspose.Slides συμβατό με διαφορετικές εκδόσεις του PowerPoint;
Ναι, το Aspose.Slides διασφαλίζει συμβατότητα με διάφορες εκδόσεις του Microsoft PowerPoint, επιτρέποντας την απρόσκοπτη ενσωμάτωση στη ροή εργασίας σας.
### Μπορώ να προσαρμόσω στοιχεία SmartArt πέρα από τη μορφή συμπλήρωσης κουκκίδων;
Πράγματι, το Aspose.Slides σάς δίνει τη δυνατότητα να προσαρμόσετε κάθε πτυχή των σχημάτων SmartArt, συμπεριλαμβανομένης της διάταξης, του στυλ, του περιεχομένου και άλλων.
### Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το Aspose.Slides για Java;
Ναι, μπορείτε να εξερευνήσετε τις δυνατότητες του Aspose.Slides με μια δωρεάν δοκιμαστική περίοδο. Απλώς κατεβάστε το από το [δικτυακός τόπος](https://releases.aspose.com/slides/java/) και ξεκινήστε την εξερεύνηση.
### Πού μπορώ να βρω υποστήριξη για το Aspose.Slides για Java;
Για οποιεσδήποτε ερωτήσεις ή βοήθεια, μπορείτε να επισκεφθείτε το φόρουμ Aspose.Slides στη διεύθυνση [αυτός ο σύνδεσμος](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}