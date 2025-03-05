---
title: Προσθέστε προσαρμοσμένους θυγατρικούς κόμβους στο SmartArt χρησιμοποιώντας Java
linktitle: Προσθέστε προσαρμοσμένους θυγατρικούς κόμβους στο SmartArt χρησιμοποιώντας Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Μάθετε πώς να προσθέτετε προσαρμοσμένους θυγατρικούς κόμβους στο SmartArt σε παρουσιάσεις PowerPoint χρησιμοποιώντας Java με Aspose.Slides. Βελτιώστε τις διαφάνειές σας με επαγγελματικά γραφικά χωρίς κόπο.
type: docs
weight: 11
url: /el/java/java-powerpoint-smartart-manipulation/add-custom-child-nodes-smartart-java/
---
## Εισαγωγή
Το SmartArt είναι μια ισχυρή δυνατότητα στο PowerPoint που επιτρέπει στους χρήστες να δημιουργούν γραφικά με επαγγελματική εμφάνιση γρήγορα και εύκολα. Σε αυτό το σεμινάριο, θα μάθουμε πώς να προσθέτουμε προσαρμοσμένους θυγατρικούς κόμβους στο SmartArt χρησιμοποιώντας Java με Aspose.Slides.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα εξής:
1. Java Development Kit (JDK): Βεβαιωθείτε ότι έχετε εγκαταστήσει Java στο σύστημά σας.
2.  Aspose.Slides για Java: Κατεβάστε και εγκαταστήστε το Aspose.Slides για Java από[εδώ](https://releases.aspose.com/slides/java/).

## Εισαγωγή πακέτων
Για να ξεκινήσετε, εισαγάγετε τα απαραίτητα πακέτα στο έργο σας Java:
```java
import com.aspose.slides.*;
```
## Βήμα 1: Φορτώστε την παρουσίαση
Φορτώστε την παρουσίαση του PowerPoint όπου θέλετε να προσθέσετε προσαρμοσμένους θυγατρικούς κόμβους στο SmartArt:
```java
String dataDir = "Your Document Directory";
// Φορτώστε την επιθυμητή παρουσίαση
Presentation pres = new Presentation(dataDir + "YourPresentation.pptx");
```
## Βήμα 2: Προσθήκη SmartArt στη Διαφάνεια
Τώρα, ας προσθέσουμε το SmartArt στη διαφάνεια:
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(20, 20, 600, 500, SmartArtLayoutType.OrganizationChart);
```
## Βήμα 3: Μετακινήστε το SmartArt Shape
Μετακινήστε το σχήμα SmartArt σε μια νέα θέση:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(1);
ISmartArtShape shape = node.getShapes().get_Item(1);
shape.setX(shape.getX() + (shape.getWidth() * 2));
shape.setY(shape.getY() - (shape.getHeight() / 2));
```
## Βήμα 4: Αλλάξτε το πλάτος σχήματος
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
## Βήμα 6: Περιστρέψτε το σχήμα
Περιστρέψτε το σχήμα SmartArt:
```java
node = smart.getAllNodes().get_Item(4);
shape = node.getShapes().get_Item(1);
shape.setRotation(90);
```
## Βήμα 7: Αποθηκεύστε την Παρουσίαση
Τέλος, αποθηκεύστε την τροποποιημένη παρουσίαση:
```java
pres.save(dataDir + "ModifiedPresentation.pptx", SaveFormat.Pptx);
```

## συμπέρασμα
Σε αυτό το σεμινάριο, μάθαμε πώς να προσθέτουμε προσαρμοσμένους θυγατρικούς κόμβους στο SmartArt χρησιμοποιώντας Java με Aspose.Slides. Ακολουθώντας αυτά τα βήματα, μπορείτε να βελτιώσετε τις παρουσιάσεις σας με προσαρμοσμένα γραφικά, καθιστώντας τις πιο ελκυστικές και επαγγελματικές.
## Συχνές ερωτήσεις
### Μπορώ να προσθέσω διαφορετικούς τύπους διατάξεων SmartArt χρησιμοποιώντας το Aspose.Slides για Java;
Ναι, το Aspose.Slides για Java υποστηρίζει διάφορες διατάξεις SmartArt, επιτρέποντάς σας να επιλέξετε αυτό που ταιριάζει καλύτερα στις ανάγκες παρουσίασής σας.
### Είναι το Aspose.Slides για Java συμβατό με διαφορετικές εκδόσεις του PowerPoint;
Το Aspose.Slides για Java έχει σχεδιαστεί για να λειτουργεί απρόσκοπτα με διαφορετικές εκδόσεις του PowerPoint, διασφαλίζοντας συμβατότητα και συνέπεια σε όλες τις πλατφόρμες.
### Μπορώ να προσαρμόσω την εμφάνιση των σχημάτων SmartArt μέσω προγραμματισμού;
Απολύτως! Με το Aspose.Slides για Java, μπορείτε να προσαρμόσετε μέσω προγραμματισμού την εμφάνιση, το μέγεθος, το χρώμα και τη διάταξη των σχημάτων SmartArt ώστε να ταιριάζουν στις σχεδιαστικές προτιμήσεις σας.
### Το Aspose.Slides για Java παρέχει τεκμηρίωση και υποστήριξη;
Ναι, μπορείτε να βρείτε ολοκληρωμένη τεκμηρίωση και πρόσβαση σε φόρουμ υποστήριξης κοινότητας στον ιστότοπο Aspose.
### Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το Aspose.Slides για Java;
 Ναι, μπορείτε να κατεβάσετε μια δωρεάν δοκιμαστική έκδοση του Aspose.Slides για Java από τον ιστότοπο για να εξερευνήσετε τις δυνατότητες και τις δυνατότητές του πριν κάνετε μια αγορά[εδώ](https://releases.aspose.com/slides/java/).