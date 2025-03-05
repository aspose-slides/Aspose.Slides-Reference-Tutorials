---
title: Ορίστε τη μορφή Bullet Fill στο SmartArt χρησιμοποιώντας Java
linktitle: Ορίστε τη μορφή Bullet Fill στο SmartArt χρησιμοποιώντας Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Μάθετε πώς να ορίζετε τη μορφή γεμίσματος κουκκίδων στο SmartArt χρησιμοποιώντας Java με το Aspose.Slides. Βήμα-βήμα οδηγός για αποτελεσματικό χειρισμό παρουσίασης.
type: docs
weight: 18
url: /el/java/java-powerpoint-smartart-manipulation/set-bullet-fill-format-smartart-java/
---
## Εισαγωγή
Στη σφαίρα του προγραμματισμού Java, ο αποτελεσματικός χειρισμός των παρουσιάσεων είναι μια κοινή απαίτηση, ειδικά όταν πρόκειται για στοιχεία SmartArt. Το Aspose.Slides για Java αναδεικνύεται ως ένα ισχυρό εργαλείο για τέτοιες εργασίες, προσφέροντας μια σειρά λειτουργιών για το χειρισμό των παρουσιάσεων μέσω προγραμματισμού. Σε αυτό το σεμινάριο, θα εμβαθύνουμε στη διαδικασία ρύθμισης της μορφής συμπλήρωσης κουκκίδων στο SmartArt χρησιμοποιώντας Java με Aspose.Slides, βήμα προς βήμα.
## Προαπαιτούμενα
Πριν ξεκινήσουμε αυτό το σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
### Java Development Kit (JDK)
 Πρέπει να έχετε εγκαταστήσει το JDK στο σύστημά σας. Μπορείτε να το κατεβάσετε από το[δικτυακός τόπος](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) και ακολουθήστε τις οδηγίες εγκατάστασης.
### Aspose.Slides για Java
 Κατεβάστε και εγκαταστήστε το Aspose.Slides για Java από το[σύνδεσμος λήψης](https://releases.aspose.com/slides/java/). Ακολουθήστε τις οδηγίες εγκατάστασης που παρέχονται στην τεκμηρίωση για το συγκεκριμένο λειτουργικό σας σύστημα.

## Εισαγωγή πακέτων
Για να ξεκινήσετε, εισαγάγετε τα απαραίτητα πακέτα στο έργο σας Java:
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
#Ας αναλύσουμε το παράδειγμα που παρέχεται σε πολλά βήματα για μια σαφή κατανόηση του τρόπου ρύθμισης της μορφής συμπλήρωσης κουκκίδων στο SmartArt χρησιμοποιώντας Java με Aspose.Slides.
## Βήμα 1: Δημιουργία αντικειμένου παρουσίασης
```java
Presentation presentation = new Presentation();
```
Αρχικά, δημιουργήστε μια νέα παρουσία της κλάσης Presentation, η οποία αντιπροσωπεύει μια παρουσίαση PowerPoint.
## Βήμα 2: Προσθήκη SmartArt
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 500, 400, SmartArtLayoutType.VerticalPictureList);
```
Στη συνέχεια, προσθέστε ένα σχήμα SmartArt στη διαφάνεια. Αυτή η γραμμή κώδικα προετοιμάζει ένα νέο σχήμα SmartArt με καθορισμένες διαστάσεις και διάταξη.
## Βήμα 3: Πρόσβαση στο SmartArt Node
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
Τώρα, αποκτήστε πρόσβαση στον πρώτο κόμβο (ή οποιονδήποτε επιθυμητό κόμβο) εντός του σχήματος SmartArt για να τροποποιήσετε τις ιδιότητές του.
## Βήμα 4: Ορίστε τη μορφή πλήρωσης κουκκίδων
```java
if (node.getBulletFillFormat() != null) {
    BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
    IPPImage image = presentation.getImages().addImage(img);
    node.getBulletFillFormat().setFillType(FillType.Picture);
    node.getBulletFillFormat().getPictureFillFormat().getPicture().setImage(image);
    node.getBulletFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
}
```
Εδώ, ελέγχουμε αν υποστηρίζεται η μορφή συμπλήρωσης κουκκίδων. Εάν είναι, φορτώνουμε ένα αρχείο εικόνας και το ορίζουμε ως το γέμισμα κουκκίδων για τον κόμβο SmartArt.
## Βήμα 5: Αποθήκευση παρουσίασης
```java
presentation.save(dataDir + "out.pptx", SaveFormat.Pptx);
```
Τέλος, αποθηκεύστε την τροποποιημένη παρουσίαση σε μια καθορισμένη τοποθεσία.

## συμπέρασμα
Συγχαρητήρια! Μάθατε με επιτυχία πώς να ορίζετε τη μορφή γεμίσματος κουκκίδων στο SmartArt χρησιμοποιώντας Java με το Aspose.Slides. Αυτή η δυνατότητα ανοίγει έναν κόσμο δυνατοτήτων για δυναμικές και οπτικά ελκυστικές παρουσιάσεις σε εφαρμογές Java.
## Συχνές ερωτήσεις
### Μπορώ να χρησιμοποιήσω το Aspose.Slides για Java για να δημιουργήσω παρουσιάσεις από την αρχή;
Απολύτως! Το Aspose.Slides παρέχει ολοκληρωμένα API για δημιουργία, τροποποίηση και χειρισμό παρουσιάσεων εξ ολοκλήρου μέσω κώδικα.
### Είναι το Aspose.Slides συμβατό με διαφορετικές εκδόσεις του PowerPoint;
Ναι, το Aspose.Slides διασφαλίζει τη συμβατότητα με διάφορες εκδόσεις του Microsoft PowerPoint, επιτρέποντας την απρόσκοπτη ενσωμάτωση στη ροή εργασίας σας.
### Μπορώ να προσαρμόσω στοιχεία SmartArt πέρα από τη μορφή γεμίσματος κουκκίδων;
Πράγματι, το Aspose.Slides σάς δίνει τη δυνατότητα να προσαρμόσετε κάθε πτυχή των σχημάτων SmartArt, συμπεριλαμβανομένης της διάταξης, του στυλ, του περιεχομένου και άλλων.
### Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το Aspose.Slides για Java;
 Ναι, μπορείτε να εξερευνήσετε τις δυνατότητες του Aspose.Slides με μια δωρεάν δοκιμή. Απλώς κατεβάστε το από το[δικτυακός τόπος](https://releases.aspose.com/slides/java/) και ξεκινήστε την εξερεύνηση.
### Πού μπορώ να βρω υποστήριξη για το Aspose.Slides για Java;
 Για οποιαδήποτε απορία ή βοήθεια, μπορείτε να επισκεφτείτε το φόρουμ Aspose.Slides στη διεύθυνση[αυτός ο σύνδεσμος](https://forum.aspose.com/c/slides/11).