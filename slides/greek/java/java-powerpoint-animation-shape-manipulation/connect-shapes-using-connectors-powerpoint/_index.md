---
title: Συνδέστε σχήματα χρησιμοποιώντας συνδέσμους στο PowerPoint
linktitle: Συνδέστε σχήματα χρησιμοποιώντας συνδέσμους στο PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: Μάθετε πώς να συνδέετε σχήματα χρησιμοποιώντας συνδέσμους σε παρουσιάσεις PowerPoint με το Aspose.Slides για Java. Βήμα προς βήμα μάθημα για αρχάριους.
weight: 18
url: /el/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connectors-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Συνδέστε σχήματα χρησιμοποιώντας συνδέσμους στο PowerPoint

## Εισαγωγή
Σε αυτό το σεμινάριο, θα εξερευνήσουμε πώς να συνδέουμε σχήματα χρησιμοποιώντας συνδέσμους σε παρουσιάσεις PowerPoint με τη βοήθεια του Aspose.Slides για Java. Ακολουθήστε αυτές τις οδηγίες βήμα προς βήμα για να συνδέσετε αποτελεσματικά σχήματα και να δημιουργήσετε οπτικά ελκυστικές διαφάνειες.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
- Βασικές γνώσεις γλώσσας προγραμματισμού Java.
- Εγκατεστημένο Java Development Kit (JDK) στο σύστημά σας.
-  Έγινε λήψη και ρύθμιση του Aspose.Slides για Java. Εάν δεν το έχετε εγκαταστήσει ακόμα, μπορείτε να το κατεβάσετε από[εδώ](https://releases.aspose.com/slides/java/).
- Ένα πρόγραμμα επεξεργασίας κώδικα όπως το Eclipse ή το IntelliJ IDEA.

## Εισαγωγή πακέτων
Αρχικά, εισαγάγετε τα απαραίτητα πακέτα για την εργασία με το Aspose.Slides στο έργο σας Java.
```java
import com.aspose.slides.*;

```
## Βήμα 1: Τάξη Instantiate Presentation
 Στιγμιότυπο το`Presentation`κλάση, η οποία αντιπροσωπεύει το αρχείο PPTX στο οποίο εργάζεστε.
```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
Presentation input = new Presentation();
```
## Βήμα 2: Πρόσβαση στη Συλλογή Σχημάτων
Αποκτήστε πρόσβαση στη συλλογή σχημάτων για την επιλεγμένη διαφάνεια όπου θέλετε να προσθέσετε σχήματα και συνδέσμους.
```java
IShapeCollection shapes = input.getSlides().get_Item(0).getShapes();
```
## Βήμα 3: Προσθέστε σχήματα
Προσθέστε τα απαιτούμενα σχήματα στη διαφάνεια. Σε αυτό το παράδειγμα, θα προσθέσουμε μια έλλειψη και ένα ορθογώνιο.
```java
// Προσθέστε αυτόματο σχήμα Ellipse
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
// Προσθέστε αυτόματο σχήμα Ορθογώνιο
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## Βήμα 4: Προσθήκη εφαρμογής σύνδεσης
Προσθέστε ένα σχήμα σύνδεσης στη συλλογή σχημάτων διαφανειών.
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## Βήμα 5: Συνδέστε Shapes σε Connectors
Συνδέστε τα σχήματα στον σύνδεσμο.
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## Βήμα 6: Επαναδρομολόγηση της σύνδεσης
Κλήση αναδρομολόγησης για να ορίσετε την αυτόματη συντομότερη διαδρομή μεταξύ των σχημάτων.
```java
connector.reroute();
```
## Βήμα 7: Αποθήκευση παρουσίασης
Αποθηκεύστε την παρουσίαση αφού συνδέσετε σχήματα χρησιμοποιώντας συνδέσμους.
```java
input.save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
Τέλος, μην ξεχάσετε να πετάξετε το αντικείμενο Παρουσίασης.
```java
if (input != null) input.dispose();
```
Τώρα έχετε συνδέσει με επιτυχία σχήματα χρησιμοποιώντας συνδέσμους στο PowerPoint χρησιμοποιώντας το Aspose.Slides για Java.

## συμπέρασμα
Σε αυτό το σεμινάριο, μάθαμε πώς να συνδέουμε σχήματα χρησιμοποιώντας συνδέσμους σε παρουσιάσεις PowerPoint με το Aspose.Slides για Java. Ακολουθώντας αυτά τα απλά βήματα, μπορείτε να βελτιώσετε τις παρουσιάσεις σας με οπτικά ελκυστικά διαγράμματα και διαγράμματα ροής.
## Συχνές ερωτήσεις
### Μπορώ να προσαρμόσω την εμφάνιση των συνδέσεων στο Aspose.Slides για Java;
Ναι, μπορείτε να προσαρμόσετε διάφορες ιδιότητες των συνδέσμων, όπως το χρώμα, το στυλ γραμμής και το πάχος, ώστε να ταιριάζουν στις ανάγκες της παρουσίασής σας.
### Είναι το Aspose.Slides για Java συμβατό με όλες τις εκδόσεις του PowerPoint;
Το Aspose.Slides για Java υποστηρίζει διάφορες μορφές PowerPoint, συμπεριλαμβανομένων των PPTX, PPT και ODP.
### Μπορώ να συνδέσω περισσότερα από δύο σχήματα με έναν μόνο σύνδεσμο;
Ναι, μπορείτε να συνδέσετε πολλά σχήματα χρησιμοποιώντας σύνθετες συνδέσεις που παρέχονται από το Aspose.Slides για Java.
### Το Aspose.Slides για Java προσφέρει υποστήριξη για την προσθήκη κειμένου σε σχήματα;
Οπωσδήποτε, μπορείτε εύκολα να προσθέσετε κείμενο σε σχήματα και συνδέσμους μέσω προγραμματισμού χρησιμοποιώντας το Aspose.Slides για Java.
### Υπάρχει κάποιο φόρουμ κοινότητας ή κανάλι υποστήριξης διαθέσιμο για το Aspose.Slides για χρήστες Java;
 Ναι, μπορείτε να βρείτε χρήσιμους πόρους, να κάνετε ερωτήσεις και να αλληλεπιδράσετε με άλλους χρήστες στο φόρουμ Aspose.Slides[εδώ](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
