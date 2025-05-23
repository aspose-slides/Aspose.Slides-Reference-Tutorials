---
"description": "Μάθετε πώς να συνδέετε σχήματα στο PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Αυτοματοποιήστε τις παρουσιάσεις σας χωρίς κόπο."
"linktitle": "Σύνδεση σχημάτων χρησιμοποιώντας τοποθεσίες σύνδεσης στο PowerPoint"
"second_title": "Aspose.Slides API επεξεργασίας Java PowerPoint"
"title": "Σύνδεση σχημάτων χρησιμοποιώντας τοποθεσίες σύνδεσης στο PowerPoint"
"url": "/el/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connection-sites-powerpoint/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Σύνδεση σχημάτων χρησιμοποιώντας τοποθεσίες σύνδεσης στο PowerPoint

## Εισαγωγή
Σε αυτό το σεμινάριο, θα εξερευνήσουμε πώς να συνδέουμε σχήματα χρησιμοποιώντας τοποθεσίες σύνδεσης στο PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Αυτή η ισχυρή βιβλιοθήκη μας επιτρέπει να χειριζόμαστε προγραμματιστικά παρουσιάσεις PowerPoint, κάνοντας εργασίες όπως η σύνδεση σχημάτων απρόσκοπτες και αποτελεσματικές.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα εξής:
1. Κιτ Ανάπτυξης Java (JDK): Βεβαιωθείτε ότι έχετε εγκαταστήσει την Java στο σύστημά σας. Μπορείτε να την κατεβάσετε και να την εγκαταστήσετε από το [δικτυακός τόπος](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2. Aspose.Slides για Java: Κατεβάστε και εγκαταστήστε το Aspose.Slides για Java από το [σελίδα λήψης](https://releases.aspose.com/slides/java/).
3. Ολοκληρωμένο Περιβάλλον Ανάπτυξης (IDE): Επιλέξτε ένα IDE για ανάπτυξη Java, όπως IntelliJ IDEA, Eclipse ή NetBeans.

## Εισαγωγή πακέτων
Για να ξεκινήσετε, εισαγάγετε τα απαραίτητα πακέτα στο έργο Java σας:
```java
import com.aspose.slides.*;

```
## Βήμα 1: Πρόσβαση στη Συλλογή Σχήματων
Πρόσβαση στη συλλογή σχημάτων για την επιλεγμένη διαφάνεια:
```java
// Η διαδρομή προς τον κατάλογο εγγράφων.                    
String dataDir = "Your Document Directory";
// Δημιουργία αρχικού στιγμιότυπου της κλάσης παρουσίασης που αντιπροσωπεύει το αρχείο PPTX
Presentation presentation = new Presentation();
IShapeCollection shapes = presentation.getSlides().get_Item(0).getShapes();
```
## Βήμα 2: Προσθήκη σχήματος σύνδεσης
Προσθήκη σχήματος σύνδεσης στη συλλογή σχημάτων διαφάνειας:
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector3, 0, 0, 10, 10);
```
## Βήμα 3: Προσθήκη Αυτόματων Σχήματων
Προσθέστε αυτόματα σχήματα όπως έλλειψη και ορθογώνιο:
```java
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 200, 100, 100);
```
## Βήμα 4: Ένωση σχημάτων με συνδέσμους
Ενώστε τα σχήματα στον σύνδεσμο:
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## Βήμα 5: Ρύθμιση ευρετηρίου τοποθεσίας σύνδεσης
Ορίστε τον επιθυμητό δείκτη τοποθεσίας σύνδεσης για τα σχήματα:
```java
long wantedIndex = 6;
if (ellipse.getConnectionSiteCount() > (wantedIndex & 0xFFFFFFFFL))
{
    connector.setStartShapeConnectionSiteIndex(wantedIndex);
}
```

## Σύναψη
Σε αυτό το σεμινάριο, μάθαμε πώς να συνδέουμε σχήματα χρησιμοποιώντας τοποθεσίες σύνδεσης στο PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Με αυτές τις γνώσεις, μπορείτε πλέον να αυτοματοποιήσετε και να προσαρμόσετε τις παρουσιάσεις του PowerPoint σας με ευκολία.
## Συχνές ερωτήσεις
### Μπορεί το Aspose.Slides για Java να χρησιμοποιηθεί για άλλες εργασίες χειρισμού του PowerPoint;
Ναι, το Aspose.Slides για Java παρέχει ένα ευρύ φάσμα λειτουργιών για τη δημιουργία, την επεξεργασία και τη μετατροπή παρουσιάσεων PowerPoint.
### Είναι το Aspose.Slides για Java δωρεάν στη χρήση;
Το Aspose.Slides για Java είναι μια εμπορική βιβλιοθήκη, αλλά μπορείτε να εξερευνήσετε τις δυνατότητές της με μια δωρεάν δοκιμαστική περίοδο. Επισκεφθείτε το [εδώ](https://releases.aspose.com/) για να ξεκινήσετε.
### Μπορώ να λάβω υποστήριξη εάν αντιμετωπίσω προβλήματα κατά τη χρήση του Aspose.Slides για Java;
Ναι, μπορείτε να λάβετε υποστήριξη από τα φόρουμ της κοινότητας Aspose [εδώ](https://forum.aspose.com/c/slides/11).
### Υπάρχουν διαθέσιμες προσωρινές άδειες χρήσης για το Aspose.Slides για Java;
Ναι, διατίθενται προσωρινές άδειες για σκοπούς δοκιμών και αξιολόγησης. Μπορείτε να αποκτήσετε μία [εδώ](https://purchase.aspose.com/temporary-license/).
### Πού μπορώ να αγοράσω μια άδεια χρήσης για το Aspose.Slides για Java;
Μπορείτε να αγοράσετε μια άδεια χρήσης από τον ιστότοπο της Aspose [εδώ](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}