---
title: Εφαρμογή εφέ περιστροφής 3D σε σχήματα στο PowerPoint
linktitle: Εφαρμογή εφέ περιστροφής 3D σε σχήματα στο PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: Μάθετε πώς να εφαρμόζετε εφέ περιστροφής 3D σε σχήματα στο PowerPoint χρησιμοποιώντας το Aspose.Slides για Java με αυτόν τον περιεκτικό, βήμα προς βήμα σεμινάριο.
weight: 12
url: /el/java/java-powerpoint-animation-shape-manipulation/apply-3d-rotation-effect-shapes-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Εισαγωγή
Είστε έτοιμοι να μεταφέρετε τις παρουσιάσεις σας στο PowerPoint στο επόμενο επίπεδο; Η προσθήκη εφέ περιστροφής 3D μπορεί να κάνει τις διαφάνειές σας πιο δυναμικές και ελκυστικές. Είτε είστε έμπειρος προγραμματιστής είτε μόλις ξεκινάτε, αυτός ο αναλυτικός οδηγός θα σας δείξει πώς να εφαρμόζετε εφέ περιστροφής 3D σε σχήματα στο PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Ας βουτήξουμε αμέσως!
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα εξής:
1.  Java Development Kit (JDK): Βεβαιωθείτε ότι έχετε εγκαταστήσει το JDK στο σύστημά σας. Μπορείτε να το κατεβάσετε από το[Ιστοσελίδα Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides για Java: Κατεβάστε την πιο πρόσφατη έκδοση του Aspose.Slides για Java από το[σύνδεσμος λήψης](https://releases.aspose.com/slides/java/).
3. Ενσωματωμένο περιβάλλον ανάπτυξης (IDE): Χρησιμοποιήστε ένα IDE όπως το IntelliJ IDEA ή το Eclipse για κωδικοποίηση.
4.  Μια έγκυρη άδεια: Εάν δεν έχετε άδεια, μπορείτε να αποκτήσετε μια[προσωρινή άδεια](https://purchase.aspose.com/temporary-license/) για να δοκιμάσετε τις δυνατότητες.
## Εισαγωγή πακέτων
Αρχικά, ας εισάγουμε τα απαραίτητα πακέτα στο έργο σας Java. Αυτές οι εισαγωγές θα σας βοηθήσουν να χειριστείτε παρουσιάσεις και σχήματα με το Aspose.Slides.
```java
import com.aspose.slides.*;

```
## Βήμα 1: Ρύθμιση του έργου σας
Πριν βουτήξετε στον κώδικα, ρυθμίστε το περιβάλλον του έργου σας. Βεβαιωθείτε ότι έχετε προσθέσει Aspose.Slides για Java στις εξαρτήσεις του έργου σας.
Προσθέστε Aspose.Slides στο έργο σας:
1.  Κατεβάστε τα αρχεία JAR Aspose.Slides από το[σελίδα λήψης](https://releases.aspose.com/slides/java/).
2. Προσθέστε αυτά τα αρχεία JAR στη διαδρομή κατασκευής του έργου σας.
## Βήμα 2: Δημιουργήστε μια νέα παρουσίαση PowerPoint
Σε αυτό το βήμα, θα δημιουργήσουμε μια νέα παρουσίαση PowerPoint.
```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
// Δημιουργήστε μια παρουσία της κλάσης παρουσίασης
Presentation pres = new Presentation();
```
Αυτό το απόσπασμα κώδικα προετοιμάζει ένα νέο αντικείμενο παρουσίασης όπου θα προσθέσουμε τα σχήματά μας.
## Βήμα 3: Προσθέστε ένα σχήμα ορθογωνίου
Στη συνέχεια, ας προσθέσουμε ένα ορθογώνιο σχήμα στην πρώτη διαφάνεια.
```java
IShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 30, 30, 200, 200);
```
Αυτός ο κωδικός προσθέτει ένα ορθογώνιο σχήμα στην καθορισμένη θέση και μέγεθος στην πρώτη διαφάνεια.
## Βήμα 4: Εφαρμόστε Τρισδιάστατη Περιστροφή στο Ορθογώνιο
Τώρα, ας εφαρμόσουμε ένα εφέ περιστροφής 3D στο σχήμα του ορθογωνίου.
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(40, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
Εδώ, ορίζουμε το βάθος, τις γωνίες περιστροφής της κάμερας, τον τύπο κάμερας και τον τύπο φωτισμού για να δώσουμε στο ορθογώνιό μας μια τρισδιάστατη εμφάνιση.
## Βήμα 5: Προσθέστε ένα σχήμα γραμμής
Ας προσθέσουμε ένα άλλο σχήμα, αυτή τη φορά μια γραμμή, στη διαφάνεια.
```java
autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Line, 30, 300, 200, 200);
```
Αυτός ο κώδικας τοποθετεί ένα σχήμα γραμμής στη διαφάνεια.
## Βήμα 6: Εφαρμόστε Τρισδιάστατη Περιστροφή στη Γραμμή
Τέλος, θα εφαρμόσουμε ένα εφέ 3D περιστροφής στο σχήμα της γραμμής.
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(0, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
Παρόμοια με το ορθογώνιο, ορίσαμε τις τρισδιάστατες ιδιότητες για το σχήμα γραμμής.
## Βήμα 7: Αποθηκεύστε την Παρουσίαση
Αφού προσθέσετε και διαμορφώσετε τα σχήματά σας, αποθηκεύστε την παρουσίαση.
```java
pres.save(dataDir + "Rotation_out.pptx", SaveFormat.Pptx);
```
Αυτός ο κωδικός αποθηκεύει την παρουσίασή σας με το καθορισμένο όνομα αρχείου στην επιθυμητή μορφή.
## συμπέρασμα
 Συγχαρητήρια! Εφαρμόσατε με επιτυχία τρισδιάστατα εφέ περιστροφής σε σχήματα σε μια παρουσίαση PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Ακολουθώντας αυτά τα βήματα, μπορείτε να δημιουργήσετε οπτικά ελκυστικές και δυναμικές παρουσιάσεις. Για περαιτέρω προσαρμογή και πιο προηγμένες λειτουργίες, ανατρέξτε στο[Τεκμηρίωση Aspose.Slides](https://reference.aspose.com/slides/java/).
## Συχνές ερωτήσεις
### Τι είναι το Aspose.Slides για Java;
Το Aspose.Slides for Java είναι ένα ισχυρό API για τη δημιουργία, τροποποίηση και χειρισμό παρουσιάσεων του PowerPoint μέσω προγραμματισμού.
### Μπορώ να δοκιμάσω το Aspose.Slides για Java δωρεάν;
 Ναι, μπορείτε να πάρετε ένα[δωρεάν δοκιμή](https://releases.aspose.com/) ή α[προσωρινή άδεια](https://purchase.aspose.com/temporary-license/) για να δοκιμάσετε τα χαρακτηριστικά.
### Σε ποιους τύπους σχημάτων μπορώ να προσθέσω εφέ 3D στο Aspose.Slides;
Μπορείτε να προσθέσετε εφέ 3D σε διάφορα σχήματα, όπως ορθογώνια, γραμμές, ελλείψεις και προσαρμοσμένα σχήματα.
### Πώς μπορώ να λάβω υποστήριξη για το Aspose.Slides για Java;
 Μπορείτε να επισκεφθείτε το[φόρουμ υποστήριξης](https://forum.aspose.com/c/slides/11) για βοήθεια και για συζήτηση τυχόν ζητημάτων.
### Μπορώ να χρησιμοποιήσω το Aspose.Slides για Java σε εμπορικά έργα;
 Ναι, αλλά πρέπει να αγοράσετε άδεια. Μπορείτε να αγοράσετε ένα από το[σελίδα αγοράς](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
