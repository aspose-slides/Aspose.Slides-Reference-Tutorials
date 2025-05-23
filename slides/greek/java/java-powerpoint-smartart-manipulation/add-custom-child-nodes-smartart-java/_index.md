---
"description": "Μάθετε πώς να προσθέτετε προσαρμοσμένους θυγατρικούς κόμβους στο SmartArt σε παρουσιάσεις PowerPoint χρησιμοποιώντας Java με Aspose.Slides. Βελτιώστε τις διαφάνειές σας με επαγγελματικά γραφικά χωρίς κόπο."
"linktitle": "Προσθήκη προσαρμοσμένων θυγατρικών κόμβων στο SmartArt χρησιμοποιώντας Java"
"second_title": "Aspose.Slides API επεξεργασίας Java PowerPoint"
"title": "Προσθήκη προσαρμοσμένων θυγατρικών κόμβων στο SmartArt χρησιμοποιώντας Java"
"url": "/el/java/java-powerpoint-smartart-manipulation/add-custom-child-nodes-smartart-java/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Προσθήκη προσαρμοσμένων θυγατρικών κόμβων στο SmartArt χρησιμοποιώντας Java

## Εισαγωγή
Το SmartArt είναι μια ισχυρή λειτουργία στο PowerPoint που επιτρέπει στους χρήστες να δημιουργούν γραφικά επαγγελματικής εμφάνισης γρήγορα και εύκολα. Σε αυτό το σεμινάριο, θα μάθουμε πώς να προσθέτουμε προσαρμοσμένους θυγατρικούς κόμβους στο SmartArt χρησιμοποιώντας Java με Aspose.Slides.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα εξής:
1. Κιτ ανάπτυξης Java (JDK): Βεβαιωθείτε ότι έχετε εγκαταστήσει την Java στο σύστημά σας.
2. Aspose.Slides για Java: Λήψη και εγκατάσταση του Aspose.Slides για Java από [εδώ](https://releases.aspose.com/slides/java/).

## Εισαγωγή πακέτων
Για να ξεκινήσετε, εισαγάγετε τα απαραίτητα πακέτα στο έργο Java σας:
```java
import com.aspose.slides.*;
```
## Βήμα 1: Φόρτωση της παρουσίασης
Φορτώστε την παρουσίαση PowerPoint όπου θέλετε να προσθέσετε προσαρμοσμένους θυγατρικούς κόμβους στο SmartArt:
```java
String dataDir = "Your Document Directory";
// Φόρτωση της επιθυμητής παρουσίασης
Presentation pres = new Presentation(dataDir + "YourPresentation.pptx");
```
## Βήμα 2: Προσθήκη SmartArt σε διαφάνεια
Τώρα, ας προσθέσουμε το SmartArt στη διαφάνεια:
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(20, 20, 600, 500, SmartArtLayoutType.OrganizationChart);
```
## Βήμα 3: Μετακίνηση σχήματος SmartArt
Μετακινήστε το σχήμα SmartArt σε μια νέα θέση:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(1);
ISmartArtShape shape = node.getShapes().get_Item(1);
shape.setX(shape.getX() + (shape.getWidth() * 2));
shape.setY(shape.getY() - (shape.getHeight() / 2));
```
## Βήμα 4: Αλλαγή πλάτους σχήματος
Αλλάξτε το πλάτος του σχήματος SmartArt:
```java
node = smart.getAllNodes().get_Item(2);
shape = node.getShapes().get_Item(1);
shape.setWidth(shape.getWidth() + (shape.getWidth() / 2));
```
## Βήμα 5: Αλλαγή ύψους σχήματος
Αλλάξτε το ύψος του σχήματος SmartArt:
```java
node = smart.getAllNodes().get_Item(3);
shape = node.getShapes().get_Item(1);
shape.setHeight(shape.getHeight() + (shape.getHeight() / 2));
```
## Βήμα 6: Περιστροφή του σχήματος
Περιστροφή του σχήματος SmartArt:
```java
node = smart.getAllNodes().get_Item(4);
shape = node.getShapes().get_Item(1);
shape.setRotation(90);
```
## Βήμα 7: Αποθήκευση της παρουσίασης
Τέλος, αποθηκεύστε την τροποποιημένη παρουσίαση:
```java
pres.save(dataDir + "ModifiedPresentation.pptx", SaveFormat.Pptx);
```

## Σύναψη
Σε αυτό το σεμινάριο, μάθαμε πώς να προσθέτουμε προσαρμοσμένους θυγατρικούς κόμβους στο SmartArt χρησιμοποιώντας Java με Aspose.Slides. Ακολουθώντας αυτά τα βήματα, μπορείτε να βελτιώσετε τις παρουσιάσεις σας με προσαρμοσμένα γραφικά, κάνοντάς τες πιο ελκυστικές και επαγγελματικές.
## Συχνές ερωτήσεις
### Μπορώ να προσθέσω διαφορετικούς τύπους διατάξεων SmartArt χρησιμοποιώντας το Aspose.Slides για Java;
Ναι, το Aspose.Slides για Java υποστηρίζει διάφορες διατάξεις SmartArt, επιτρέποντάς σας να επιλέξετε αυτήν που ταιριάζει καλύτερα στις ανάγκες της παρουσίασής σας.
### Είναι το Aspose.Slides για Java συμβατό με διαφορετικές εκδόσεις του PowerPoint;
Το Aspose.Slides για Java έχει σχεδιαστεί για να λειτουργεί άψογα με διαφορετικές εκδόσεις του PowerPoint, διασφαλίζοντας συμβατότητα και συνέπεια σε όλες τις πλατφόρμες.
### Μπορώ να προσαρμόσω την εμφάνιση των σχημάτων SmartArt μέσω προγραμματισμού;
Απολύτως! Με το Aspose.Slides για Java, μπορείτε να προσαρμόσετε μέσω προγραμματισμού την εμφάνιση, το μέγεθος, το χρώμα και τη διάταξη των σχημάτων SmartArt ώστε να ταιριάζουν στις προτιμήσεις σχεδίασης.
### Παρέχει το Aspose.Slides για Java τεκμηρίωση και υποστήριξη;
Ναι, μπορείτε να βρείτε ολοκληρωμένη τεκμηρίωση και πρόσβαση σε φόρουμ υποστήριξης της κοινότητας στον ιστότοπο Aspose.
### Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το Aspose.Slides για Java;
Ναι, μπορείτε να κατεβάσετε μια δωρεάν δοκιμαστική έκδοση του Aspose.Slides για Java από τον ιστότοπο για να εξερευνήσετε τις δυνατότητες και τις δυνατότητές του πριν κάνετε μια αγορά. [εδώ](https://releases.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}