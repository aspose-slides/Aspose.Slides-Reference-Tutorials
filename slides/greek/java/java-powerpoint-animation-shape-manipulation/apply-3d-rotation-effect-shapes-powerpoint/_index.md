---
"description": "Μάθετε πώς να εφαρμόζετε εφέ περιστροφής 3D σε σχήματα στο PowerPoint χρησιμοποιώντας το Aspose.Slides για Java με αυτό το ολοκληρωμένο, βήμα προς βήμα σεμινάριο."
"linktitle": "Εφαρμογή εφέ περιστροφής 3D σε σχήματα στο PowerPoint"
"second_title": "Aspose.Slides API επεξεργασίας Java PowerPoint"
"title": "Εφαρμογή εφέ περιστροφής 3D σε σχήματα στο PowerPoint"
"url": "/el/java/java-powerpoint-animation-shape-manipulation/apply-3d-rotation-effect-shapes-powerpoint/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Εφαρμογή εφέ περιστροφής 3D σε σχήματα στο PowerPoint

## Εισαγωγή
Είστε έτοιμοι να αναβαθμίσετε τις παρουσιάσεις σας στο PowerPoint; Η προσθήκη εφέ περιστροφής 3D μπορεί να κάνει τις διαφάνειές σας πιο δυναμικές και ελκυστικές. Είτε είστε έμπειρος προγραμματιστής είτε μόλις ξεκινάτε, αυτό το βήμα προς βήμα σεμινάριο θα σας δείξει πώς να εφαρμόσετε εφέ περιστροφής 3D σε σχήματα στο PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Ας ξεκινήσουμε αμέσως!
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε θέσει τα εξής σε εφαρμογή:
1. Κιτ Ανάπτυξης Java (JDK): Βεβαιωθείτε ότι έχετε εγκαταστήσει το JDK στο σύστημά σας. Μπορείτε να το κατεβάσετε από το [Ιστότοπος Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).
2. Aspose.Slides για Java: Κατεβάστε την τελευταία έκδοση του Aspose.Slides για Java από το [σύνδεσμος λήψης](https://releases.aspose.com/slides/java/).
3. Ολοκληρωμένο Περιβάλλον Ανάπτυξης (IDE): Χρησιμοποιήστε ένα IDE όπως το IntelliJ IDEA ή το Eclipse για τον προγραμματισμό.
4. Μια έγκυρη άδεια: Εάν δεν έχετε άδεια, μπορείτε να αποκτήσετε μια [προσωρινή άδεια](https://purchase.aspose.com/temporary-license/) για να δοκιμάσετε τα χαρακτηριστικά.
## Εισαγωγή πακέτων
Αρχικά, ας εισαγάγουμε τα απαραίτητα πακέτα στο έργο Java σας. Αυτές οι εισαγωγές θα σας βοηθήσουν να χειριστείτε παρουσιάσεις και σχήματα με το Aspose.Slides.
```java
import com.aspose.slides.*;

```
## Βήμα 1: Ρύθμιση του έργου σας
Πριν ξεκινήσετε να ασχολείστε με τον κώδικα, ρυθμίστε το περιβάλλον του έργου σας. Βεβαιωθείτε ότι έχετε προσθέσει το Aspose.Slides για Java στις εξαρτήσεις του έργου σας.
Προσθέστε το Aspose.Slides στο έργο σας:
1. Κατεβάστε τα αρχεία JAR Aspose.Slides από το [σελίδα λήψης](https://releases.aspose.com/slides/java/).
2. Προσθέστε αυτά τα αρχεία JAR στη διαδρομή δημιουργίας του έργου σας.
## Βήμα 2: Δημιουργήστε μια νέα παρουσίαση PowerPoint
Σε αυτό το βήμα, θα δημιουργήσουμε μια νέα παρουσίαση PowerPoint.
```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
// Δημιουργήστε μια παρουσία της κλάσης Presentation
Presentation pres = new Presentation();
```
Αυτό το απόσπασμα κώδικα αρχικοποιεί ένα νέο αντικείμενο παρουσίασης όπου θα προσθέσουμε τα σχήματά μας.
## Βήμα 3: Προσθήκη ορθογωνίου σχήματος
Στη συνέχεια, ας προσθέσουμε ένα ορθογώνιο σχήμα στην πρώτη διαφάνεια.
```java
IShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 30, 30, 200, 200);
```
Αυτός ο κώδικας προσθέτει ένα ορθογώνιο σχήμα στην καθορισμένη θέση και μέγεθος στην πρώτη διαφάνεια.
## Βήμα 4: Εφαρμογή περιστροφής 3D στο ορθογώνιο
Τώρα, ας εφαρμόσουμε ένα εφέ περιστροφής 3D στο σχήμα ορθογωνίου.
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(40, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
Εδώ, ορίζουμε το βάθος, τις γωνίες περιστροφής της κάμερας, τον τύπο κάμερας και τον τύπο φωτισμού για να δώσουμε στο ορθογώνιό μας μια τρισδιάστατη εμφάνιση.
## Βήμα 5: Προσθήκη σχήματος γραμμής
Ας προσθέσουμε ένα ακόμη σχήμα, αυτή τη φορά μια γραμμή, στη διαφάνεια.
```java
autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Line, 30, 300, 200, 200);
```
Αυτός ο κώδικας τοποθετεί ένα σχήμα γραμμής στη διαφάνεια.
## Βήμα 6: Εφαρμογή περιστροφής 3D στη γραμμή
Τέλος, θα εφαρμόσουμε ένα εφέ τρισδιάστατης περιστροφής στο σχήμα της γραμμής.
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(0, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
Όπως και με το ορθογώνιο, ορίζουμε τις τρισδιάστατες ιδιότητες για το σχήμα της γραμμής.
## Βήμα 7: Αποθήκευση της παρουσίασης
Αφού προσθέσετε και ρυθμίσετε τα σχήματά σας, αποθηκεύστε την παρουσίαση.
```java
pres.save(dataDir + "Rotation_out.pptx", SaveFormat.Pptx);
```
Αυτός ο κώδικας αποθηκεύει την παρουσίασή σας με το καθορισμένο όνομα αρχείου στην επιθυμητή μορφή.
## Σύναψη
Συγχαρητήρια! Εφαρμόσατε με επιτυχία εφέ περιστροφής 3D σε σχήματα σε μια παρουσίαση PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Ακολουθώντας αυτά τα βήματα, μπορείτε να δημιουργήσετε οπτικά ελκυστικές και δυναμικές παρουσιάσεις. Για περαιτέρω προσαρμογή και πιο προηγμένες λειτουργίες, ανατρέξτε στο [Τεκμηρίωση Aspose.Slides](https://reference.aspose.com/slides/java/).
## Συχνές ερωτήσεις
### Τι είναι το Aspose.Slides για Java;
Το Aspose.Slides για Java είναι ένα ισχυρό API για τη δημιουργία, τροποποίηση και χειρισμό παρουσιάσεων PowerPoint μέσω προγραμματισμού.
### Μπορώ να δοκιμάσω το Aspose.Slides για Java δωρεάν;
Ναι, μπορείτε να αποκτήσετε ένα [δωρεάν δοκιμή](https://releases.aspose.com/) ή ένα [προσωρινή άδεια](https://purchase.aspose.com/temporary-license/) για να δοκιμάσετε τα χαρακτηριστικά.
### Σε τι είδους σχήματα μπορώ να προσθέσω εφέ 3D στο Aspose.Slides;
Μπορείτε να προσθέσετε τρισδιάστατα εφέ σε διάφορα σχήματα όπως ορθογώνια, γραμμές, ελλείψεις και προσαρμοσμένα σχήματα.
### Πώς μπορώ να λάβω υποστήριξη για το Aspose.Slides για Java;
Μπορείτε να επισκεφθείτε το [φόρουμ υποστήριξης](https://forum.aspose.com/c/slides/11) για βοήθεια και για να συζητήσουμε τυχόν προβλήματα.
### Μπορώ να χρησιμοποιήσω το Aspose.Slides για Java σε εμπορικά έργα;
Ναι, αλλά πρέπει να αγοράσετε μια άδεια χρήσης. Μπορείτε να αγοράσετε μία από το [σελίδα αγοράς](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}