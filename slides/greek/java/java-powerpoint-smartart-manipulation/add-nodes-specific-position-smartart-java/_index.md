---
"description": "Ανακαλύψτε πώς να προσθέτετε κόμβους σε συγκεκριμένες θέσεις στο SmartArt χρησιμοποιώντας Java με το Aspose.Slides. Δημιουργήστε δυναμικές παρουσιάσεις χωρίς κόπο."
"linktitle": "Προσθήκη κόμβων σε συγκεκριμένη θέση στο SmartArt χρησιμοποιώντας Java"
"second_title": "Aspose.Slides API επεξεργασίας Java PowerPoint"
"title": "Προσθήκη κόμβων σε συγκεκριμένη θέση στο SmartArt χρησιμοποιώντας Java"
"url": "/el/java/java-powerpoint-smartart-manipulation/add-nodes-specific-position-smartart-java/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Προσθήκη κόμβων σε συγκεκριμένη θέση στο SmartArt χρησιμοποιώντας Java

## Εισαγωγή
Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία προσθήκης κόμβων σε συγκεκριμένες θέσεις στο SmartArt χρησιμοποιώντας Java με Aspose.Slides. Το SmartArt είναι μια λειτουργία στο PowerPoint που σας επιτρέπει να δημιουργείτε οπτικά ελκυστικά διαγράμματα και γραφήματα.
## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα εξής:
1. Το Java Development Kit (JDK) είναι εγκατεστημένο στο σύστημά σας.
2. Λήψη Aspose.Slides για τη βιβλιοθήκη Java. Μπορείτε να το κατεβάσετε από [εδώ](https://releases.aspose.com/slides/java/).
3. Βασική γνώση της γλώσσας προγραμματισμού Java.

## Εισαγωγή πακέτων
Αρχικά, ας εισαγάγουμε τα απαραίτητα πακέτα στον κώδικα Java μας:
```java
import com.aspose.slides.*;
import java.io.File;
```
## Βήμα 1: Δημιουργία μιας παρουσίας παρουσίασης
Ξεκινήστε δημιουργώντας μια παρουσία της κλάσης Presentation:
```java
Presentation pres = new Presentation();
```
## Βήμα 2: Πρόσβαση στη διαφάνεια παρουσίασης
Αποκτήστε πρόσβαση στη διαφάνεια όπου θέλετε να προσθέσετε το SmartArt:
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Βήμα 3: Προσθήκη σχήματος SmartArt
Προσθήκη ενός σχήματος SmartArt στη διαφάνεια:
```java
ISmartArt smart = slide.getShapes().addSmartArt(0, 0, 400, 400, SmartArtLayoutType.StackedList);
```
## Βήμα 4: Πρόσβαση στον κόμβο SmartArt
Αποκτήστε πρόσβαση στον κόμβο SmartArt στο επιθυμητό ευρετήριο:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
## Βήμα 5: Προσθήκη θυγατρικού κόμβου σε συγκεκριμένη θέση
Προσθήκη νέου θυγατρικού κόμβου σε μια συγκεκριμένη θέση στον γονικό κόμβο:
```java
SmartArtNode chNode = (SmartArtNode) ((SmartArtNodeCollection) node.getChildNodes()).addNodeByPosition(2);
```
## Βήμα 6: Προσθήκη κειμένου στον κόμβο
Ορίστε το κείμενο για τον κόμβο που προστέθηκε πρόσφατα:
```java
chNode.getTextFrame().setText("Sample Text Added");
```
## Βήμα 7: Αποθήκευση της παρουσίασης
Αποθήκευση της τροποποιημένης παρουσίασης:
```java
pres.save(dataDir + "AddSmartArtNodeByPosition_out.pptx", SaveFormat.Pptx);
```

## Σύναψη
Σε αυτό το σεμινάριο, μάθατε πώς να προσθέτετε κόμβους σε συγκεκριμένες θέσεις στο SmartArt χρησιμοποιώντας Java με το Aspose.Slides. Ακολουθώντας αυτά τα βήματα, μπορείτε να χειριστείτε σχήματα SmartArt μέσω προγραμματισμού για να δημιουργήσετε δυναμικές παρουσιάσεις.
## Συχνές ερωτήσεις
### Μπορώ να προσθέσω πολλαπλούς κόμβους ταυτόχρονα;
Ναι, μπορείτε να προσθέσετε πολλούς κόμβους μέσω προγραμματισμού, επαναλαμβάνοντας τις επιθυμητές θέσεις.
### Είναι το Aspose.Slides συμβατό με όλες τις εκδόσεις του PowerPoint;
Το Aspose.Slides υποστηρίζει διάφορες μορφές PowerPoint, εξασφαλίζοντας συμβατότητα με τις περισσότερες εκδόσεις.
### Μπορώ να προσαρμόσω την εμφάνιση των κόμβων SmartArt;
Ναι, μπορείτε να προσαρμόσετε την εμφάνιση των κόμβων, συμπεριλαμβανομένου του μεγέθους, του χρώματος και του στυλ τους.
### Προσφέρει το Aspose.Slides υποστήριξη για άλλες γλώσσες προγραμματισμού;
Ναι, το Aspose.Slides παρέχει βιβλιοθήκες για πολλές γλώσσες προγραμματισμού, συμπεριλαμβανομένων των .NET και Python.
### Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το Aspose.Slides;
Ναι, μπορείτε να κατεβάσετε μια δωρεάν δοκιμαστική έκδοση από [εδώ](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}