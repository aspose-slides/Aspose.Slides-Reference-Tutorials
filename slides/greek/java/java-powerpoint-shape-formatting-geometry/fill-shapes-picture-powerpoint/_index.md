---
title: Συμπληρώστε σχήματα με εικόνα στο PowerPoint
linktitle: Συμπληρώστε σχήματα με εικόνα στο PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: Μάθετε πώς να γεμίζετε σχήματα με εικόνες σε παρουσιάσεις PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Βελτιώστε την οπτική απήχηση χωρίς κόπο.
weight: 12
url: /el/java/java-powerpoint-shape-formatting-geometry/fill-shapes-picture-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Εισαγωγή
Οι παρουσιάσεις του PowerPoint απαιτούν συχνά οπτικά στοιχεία όπως σχήματα γεμάτα με εικόνες για να βελτιώσουν την ελκυστικότητά τους και να μεταδώσουν αποτελεσματικά τις πληροφορίες. Το Aspose.Slides για Java παρέχει ένα ισχυρό σύνολο εργαλείων για την απρόσκοπτη ολοκλήρωση αυτής της εργασίας. Σε αυτό το σεμινάριο, θα μάθουμε πώς να γεμίζουμε σχήματα με εικόνες χρησιμοποιώντας το Aspose.Slides για Java βήμα προς βήμα.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα εξής:
1. Το Java Development Kit (JDK) είναι εγκατεστημένο στο σύστημά σας.
2.  Λήψη Aspose.Slides για τη βιβλιοθήκη Java. Μπορείτε να το πάρετε από[εδώ](https://releases.aspose.com/slides/java/).
3. Βασικές γνώσεις προγραμματισμού Java.
## Εισαγωγή πακέτων
Στο έργο σας Java, εισαγάγετε τα απαραίτητα πακέτα:
```java
import com.aspose.slides.*;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Βήμα 1: Ρυθμίστε τον Κατάλογο Έργου
```java
String dataDir = "Your Document Directory";
boolean isExists = new File(dataDir).exists();
if (!isExists)
    new File(dataDir).mkdirs();
```
 Φροντίστε να αντικαταστήσετε`"Your Document Directory"` με τη διαδρομή προς τον κατάλογο του έργου σας.
## Βήμα 2: Δημιουργήστε μια παρουσίαση
```java
Presentation pres = new Presentation();
```
 Στιγμιότυπο το`Presentation` τάξη για να δημιουργήσετε μια νέα παρουσίαση PowerPoint.
## Βήμα 3: Προσθέστε μια διαφάνεια και ένα σχήμα
```java
ISlide sld = pres.getSlides().get_Item(0);
IShape shp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 150, 75, 150);
```
Προσθέστε μια διαφάνεια στην παρουσίαση και δημιουργήστε ένα ορθογώνιο σχήμα σε αυτήν.
## Βήμα 4: Ορίστε τον Τύπο πλήρωσης σε Εικόνα
```java
shp.getFillFormat().setFillType(FillType.Picture);
```
Ορίστε τον τύπο πλήρωσης του σχήματος σε εικόνα.
## Βήμα 5: Ορίστε τη λειτουργία πλήρωσης εικόνας
```java
shp.getFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Tile);
```
Ρυθμίστε τη λειτουργία πλήρωσης εικόνας του σχήματος.
## Βήμα 6: Ρύθμιση εικόνας
```java
BufferedImage img = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx = pres.getImages().addImage(img);
shp.getFillFormat().getPictureFillFormat().getPicture().setImage(imgx);
```
Φορτώστε την εικόνα και ορίστε την ως γέμισμα για το σχήμα.
## Βήμα 7: Αποθήκευση παρουσίασης
```java
pres.save(dataDir + "RectShpPic_out.pptx", SaveFormat.Pptx);
```
Αποθηκεύστε την τροποποιημένη παρουσίαση σε ένα αρχείο.

## συμπέρασμα
Με το Aspose.Slides για Java, η πλήρωση σχημάτων με εικόνες σε παρουσιάσεις PowerPoint γίνεται μια απλή διαδικασία. Ακολουθώντας τα βήματα που περιγράφονται σε αυτό το σεμινάριο, μπορείτε εύκολα να βελτιώσετε τις παρουσιάσεις σας με οπτικά ελκυστικά στοιχεία.

## Συχνές ερωτήσεις
### Μπορώ να γεμίσω διαφορετικά σχήματα με εικόνες χρησιμοποιώντας το Aspose.Slides για Java;
Ναι, το Aspose.Slides για Java υποστηρίζει τη συμπλήρωση διαφόρων σχημάτων με εικόνες, παρέχοντας ευελιξία στο σχεδιασμό.
### Είναι το Aspose.Slides για Java συμβατό με όλες τις εκδόσεις του PowerPoint;
Το Aspose.Slides για Java δημιουργεί παρουσιάσεις συμβατές με το PowerPoint 97 και νεότερες εκδόσεις, διασφαλίζοντας ευρεία συμβατότητα.
### Πώς μπορώ να αλλάξω το μέγεθος της εικόνας μέσα στο σχήμα;
Μπορείτε να αλλάξετε το μέγεθος της εικόνας μέσα στο σχήμα προσαρμόζοντας τις διαστάσεις του σχήματος ή κλιμακώνοντας ανάλογα την εικόνα πριν την ορίσετε ως γέμισμα.
### Υπάρχουν περιορισμοί στις μορφές εικόνας που υποστηρίζονται για τη συμπλήρωση σχημάτων;
Το Aspose.Slides για Java υποστηρίζει ένα ευρύ φάσμα μορφών εικόνας, όπως JPEG, PNG, GIF, BMP και TIFF, μεταξύ άλλων.
### Μπορώ να εφαρμόσω εφέ στα γεμισμένα σχήματα;
Ναι, το Aspose.Slides για Java παρέχει ολοκληρωμένα API για την εφαρμογή διαφόρων εφέ, όπως σκιές, αντανακλάσεις και τρισδιάστατες περιστροφές, σε γεμάτα σχήματα.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
