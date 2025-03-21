---
title: Προσθέστε κόμβους σε συγκεκριμένη θέση στο SmartArt χρησιμοποιώντας Java
linktitle: Προσθέστε κόμβους σε συγκεκριμένη θέση στο SmartArt χρησιμοποιώντας Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ανακαλύψτε πώς μπορείτε να προσθέσετε κόμβους σε συγκεκριμένες θέσεις στο SmartArt χρησιμοποιώντας Java με Aspose.Slides. Δημιουργήστε δυναμικές παρουσιάσεις χωρίς κόπο.
weight: 16
url: /el/java/java-powerpoint-smartart-manipulation/add-nodes-specific-position-smartart-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Προσθέστε κόμβους σε συγκεκριμένη θέση στο SmartArt χρησιμοποιώντας Java

## Εισαγωγή
Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία προσθήκης κόμβων σε συγκεκριμένες θέσεις στο SmartArt χρησιμοποιώντας Java με Aspose.Slides. Το SmartArt είναι μια δυνατότητα στο PowerPoint που σας επιτρέπει να δημιουργείτε οπτικά ελκυστικά διαγράμματα και γραφήματα.
## Προαπαιτούμενα
Πριν ξεκινήσετε, βεβαιωθείτε ότι έχετε τα εξής:
1. Το Java Development Kit (JDK) είναι εγκατεστημένο στο σύστημά σας.
2.  Λήψη Aspose.Slides για τη βιβλιοθήκη Java. Μπορείτε να το κατεβάσετε από[εδώ](https://releases.aspose.com/slides/java/).
3. Βασικές γνώσεις γλώσσας προγραμματισμού Java.

## Εισαγωγή πακέτων
Αρχικά, ας εισάγουμε τα απαραίτητα πακέτα στον κώδικα Java:
```java
import com.aspose.slides.*;
import java.io.File;
```
## Βήμα 1: Δημιουργήστε μια παρουσία παρουσίασης
Ξεκινήστε δημιουργώντας μια παρουσία της κλάσης Presentation:
```java
Presentation pres = new Presentation();
```
## Βήμα 2: Πρόσβαση στη Διαφάνεια παρουσίασης
Μεταβείτε στη διαφάνεια όπου θέλετε να προσθέσετε το SmartArt:
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Βήμα 3: Προσθέστε SmartArt Shape
Προσθέστε ένα σχήμα SmartArt στη διαφάνεια:
```java
ISmartArt smart = slide.getShapes().addSmartArt(0, 0, 400, 400, SmartArtLayoutType.StackedList);
```
## Βήμα 4: Πρόσβαση στο SmartArt Node
Πρόσβαση στον κόμβο SmartArt στο επιθυμητό ευρετήριο:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
## Βήμα 5: Προσθήκη θυγατρικού κόμβου σε συγκεκριμένη θέση
Προσθέστε έναν νέο θυγατρικό κόμβο σε μια συγκεκριμένη θέση στον γονικό κόμβο:
```java
SmartArtNode chNode = (SmartArtNode) ((SmartArtNodeCollection) node.getChildNodes()).addNodeByPosition(2);
```
## Βήμα 6: Προσθήκη κειμένου στον κόμβο
Ορίστε το κείμενο για τον κόμβο που προστέθηκε πρόσφατα:
```java
chNode.getTextFrame().setText("Sample Text Added");
```
## Βήμα 7: Αποθηκεύστε την Παρουσίαση
Αποθηκεύστε την τροποποιημένη παρουσίαση:
```java
pres.save(dataDir + "AddSmartArtNodeByPosition_out.pptx", SaveFormat.Pptx);
```

## συμπέρασμα
Σε αυτό το σεμινάριο, μάθατε πώς να προσθέτετε κόμβους σε συγκεκριμένες θέσεις στο SmartArt χρησιμοποιώντας Java με Aspose.Slides. Ακολουθώντας αυτά τα βήματα, μπορείτε να χειριστείτε τα σχήματα SmartArt μέσω προγραμματισμού για να δημιουργήσετε δυναμικές παρουσιάσεις.
## Συχνές ερωτήσεις
### Μπορώ να προσθέσω πολλούς κόμβους ταυτόχρονα;
Ναι, μπορείτε να προσθέσετε πολλαπλούς κόμβους μέσω προγραμματισμού επαναλαμβάνοντας τις επιθυμητές θέσεις.
### Είναι το Aspose.Slides συμβατό με όλες τις εκδόσεις του PowerPoint;
Το Aspose.Slides υποστηρίζει διάφορες μορφές PowerPoint, διασφαλίζοντας τη συμβατότητα με τις περισσότερες εκδόσεις.
### Μπορώ να προσαρμόσω την εμφάνιση των κόμβων SmartArt;
Ναι, μπορείτε να προσαρμόσετε την εμφάνιση των κόμβων, συμπεριλαμβανομένου του μεγέθους, του χρώματος και του στυλ τους.
### Το Aspose.Slides προσφέρει υποστήριξη για άλλες γλώσσες προγραμματισμού;
Ναι, το Aspose.Slides παρέχει βιβλιοθήκες για πολλές γλώσσες προγραμματισμού, συμπεριλαμβανομένων των .NET και Python.
### Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το Aspose.Slides;
 Ναι, μπορείτε να κάνετε λήψη μιας δωρεάν δοκιμαστικής έκδοσης από[εδώ](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
