---
title: Προσθήκη πλαισίου εικόνας σχετικής κλίμακας ύψους στο PowerPoint
linktitle: Προσθήκη πλαισίου εικόνας σχετικής κλίμακας ύψους στο PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: Μάθετε πώς να προσθέτετε κορνίζες εικόνων σε σχετική κλίμακα ύψους σε παρουσιάσεις PowerPoint χρησιμοποιώντας το Aspose.Slides για Java, βελτιώνοντας το οπτικό σας περιεχόμενο.
weight: 15
url: /el/java/java-powerpoint-shape-media-insertion/add-relative-scale-height-picture-frame-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Προσθήκη πλαισίου εικόνας σχετικής κλίμακας ύψους στο PowerPoint

## Εισαγωγή
Σε αυτό το σεμινάριο, θα μάθετε πώς να προσθέτετε μια κορνίζα με σχετικό ύψος κλίμακας σε παρουσιάσεις PowerPoint χρησιμοποιώντας το Aspose.Slides για Java.
## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα ακόλουθα:
1. Το Java Development Kit (JDK) είναι εγκατεστημένο στο σύστημά σας.
2. Η βιβλιοθήκη Aspose.Slides for Java έγινε λήψη και προσθήκη στο έργο σας Java.

## Εισαγωγή πακέτων
Για να ξεκινήσετε, εισαγάγετε τα απαραίτητα πακέτα στο έργο σας Java:
```java
import com.aspose.slides.*;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Βήμα 1: Ρύθμιση του έργου σας
Πρώτα, βεβαιωθείτε ότι έχετε ρυθμίσει έναν κατάλογο για το έργο σας και ότι το περιβάλλον Java σας έχει ρυθμιστεί σωστά.
## Βήμα 2: Δημιουργία αντικειμένου παρουσίασης
Δημιουργήστε ένα νέο αντικείμενο παρουσίασης χρησιμοποιώντας το Aspose.Slides:
```java
Presentation presentation = new Presentation();
```
## Βήμα 3: Φόρτωση εικόνας που θα προστεθεί
Φορτώστε την εικόνα που θέλετε να προσθέσετε στην παρουσίαση:
```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage image = presentation.getImages().addImage(img);
```
## Βήμα 4: Προσθέστε το πλαίσιο εικόνας στη διαφάνεια
Προσθέστε μια κορνίζα σε μια διαφάνεια της παρουσίασης:
```java
IPictureFrame pf = presentation.getSlides().get_Item(0).getShapes().addPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
## Βήμα 5: Ορίστε το πλάτος και το ύψος της σχετικής κλίμακας
Ορίστε το σχετικό πλάτος και ύψος της κλίμακας για την κορνίζα:
```java
pf.setRelativeScaleHeight(0.8f);
pf.setRelativeScaleWidth(1.35f);
```
## Βήμα 6: Αποθήκευση παρουσίασης
Αποθηκεύστε την παρουσίαση με την προστιθέμενη κορνίζα:
```java
presentation.save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```

## συμπέρασμα
Ακολουθώντας αυτά τα βήματα, μπορείτε εύκολα να προσθέσετε μια κορνίζα με σχετική κλίμακα σε παρουσιάσεις PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Πειραματιστείτε με διαφορετικές τιμές κλίμακας για να επιτύχετε την επιθυμητή εμφάνιση για τις εικόνες σας.

## Συχνές ερωτήσεις
### Μπορώ να προσθέσω πολλαπλές κορνίζες σε μία διαφάνεια χρησιμοποιώντας αυτήν τη μέθοδο;
Ναι, μπορείτε να προσθέσετε πολλαπλές κορνίζες σε μια διαφάνεια επαναλαμβάνοντας τη διαδικασία για κάθε εικόνα.
### Είναι το Aspose.Slides για Java συμβατό με όλες τις εκδόσεις του PowerPoint;
Το Aspose.Slides για Java είναι συμβατό με διάφορες εκδόσεις του PowerPoint, εξασφαλίζοντας ευελιξία στη δημιουργία παρουσιάσεων.
### Μπορώ να προσαρμόσω τη θέση και το μέγεθος της κορνίζας;
 Οπωσδήποτε, μπορείτε να προσαρμόσετε τις παραμέτρους θέσης και μεγέθους στο`addPictureFrame` μέθοδος που ταιριάζει στις απαιτήσεις σας.
### Το Aspose.Slides για Java υποστηρίζει άλλες μορφές εικόνας εκτός από το JPEG;
Ναι, το Aspose.Slides για Java υποστηρίζει διάφορες μορφές εικόνας, συμπεριλαμβανομένων των PNG, GIF, BMP και άλλων.
### Υπάρχει κάποιο φόρουμ κοινότητας ή κανάλι υποστήριξης διαθέσιμο για τους χρήστες του Aspose.Slides;
Ναι, μπορείτε να επισκεφτείτε το φόρουμ Aspose.Slides για τυχόν ερωτήσεις, συζητήσεις ή βοήθεια σχετικά με τη βιβλιοθήκη.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
