---
title: Μορφοποίηση Join Styles στο PowerPoint
linktitle: Μορφοποίηση Join Styles στο PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: Μάθετε πώς να βελτιώσετε τις παρουσιάσεις σας στο PowerPoint ορίζοντας διαφορετικά στυλ σύνδεσης γραμμών για σχήματα χρησιμοποιώντας το Aspose.Slides για Java. Ακολουθήστε τον βήμα προς βήμα οδηγό μας.
type: docs
weight: 15
url: /el/java/java-powerpoint-shape-formatting-geometry/format-join-styles-powerpoint/
---
## Εισαγωγή
Η δημιουργία οπτικά ελκυστικών παρουσιάσεων PowerPoint μπορεί να είναι μια τρομακτική εργασία, ειδικά όταν θέλετε κάθε λεπτομέρεια να είναι τέλεια. Εδώ είναι χρήσιμο το Aspose.Slides για Java. Είναι ένα ισχυρό API που σας επιτρέπει να δημιουργείτε, να χειρίζεστε και να διαχειρίζεστε παρουσιάσεις μέσω προγραμματισμού. Ένα από τα χαρακτηριστικά που μπορείτε να χρησιμοποιήσετε είναι να ορίσετε διαφορετικά στυλ σύνδεσης γραμμής για σχήματα, τα οποία μπορούν να βελτιώσουν σημαντικά την αισθητική των διαφανειών σας. Σε αυτό το σεμινάριο, θα εξετάσουμε πώς μπορείτε να χρησιμοποιήσετε το Aspose.Slides για Java για να ορίσετε στυλ σύνδεσης για σχήματα σε παρουσιάσεις PowerPoint. 
## Προαπαιτούμενα
Πριν ξεκινήσουμε, υπάρχουν μερικές προϋποθέσεις που πρέπει να έχετε:
1.  Java Development Kit (JDK): Βεβαιωθείτε ότι έχετε εγκαταστήσει το JDK στον υπολογιστή σας. Μπορείτε να το κατεβάσετε από[Ο ιστότοπος της Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Slides for Java Library: Πρέπει να κατεβάσετε και να συμπεριλάβετε το Aspose.Slides για Java στο έργο σας. Μπορείτε να το πάρετε από[εδώ](https://releases.aspose.com/slides/java/).
3. Ενσωματωμένο περιβάλλον ανάπτυξης (IDE): Χρησιμοποιήστε ένα IDE όπως το IntelliJ IDEA, το Eclipse ή το NetBeans για να γράψετε και να εκτελέσετε τον κώδικα Java σας.
4. Βασική γνώση Java: Η θεμελιώδης κατανόηση του προγραμματισμού Java θα σας βοηθήσει να ακολουθήσετε το σεμινάριο.
## Εισαγωγή πακέτων
Αρχικά, πρέπει να εισαγάγετε τα απαραίτητα πακέτα για το Aspose.Slides. Αυτό είναι απαραίτητο για την πρόσβαση στις κλάσεις και τις μεθόδους που απαιτούνται για τους χειρισμούς της παρουσίασής μας.
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.awt.*;
import java.io.File;
```
## Βήμα 1: Ρύθμιση του καταλόγου έργου
Ας ξεκινήσουμε δημιουργώντας έναν κατάλογο για την αποθήκευση των αρχείων παρουσίασής μας. Αυτό διασφαλίζει ότι όλα τα αρχεία μας είναι οργανωμένα και εύκολα προσβάσιμα.
```java
String dataDir = "Your Document Directory";
// Δημιουργήστε κατάλογο εάν δεν υπάρχει ήδη.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
Σε αυτό το βήμα, ορίζουμε μια διαδρομή καταλόγου και ελέγχουμε αν υπάρχει. Αν όχι, δημιουργούμε τον κατάλογο. Αυτός είναι ένας απλός αλλά αποτελεσματικός τρόπος για να διατηρείτε τα αρχεία σας οργανωμένα.
## Βήμα 2: Αρχικοποιήστε την Παρουσίαση
 Στη συνέχεια, στιγμιοποιούμε το`Presentation`κλάση, η οποία αντιπροσωπεύει το αρχείο PowerPoint μας. Αυτό είναι το θεμέλιο πάνω στο οποίο θα χτίσουμε τις διαφάνειες και τα σχήματά μας.
```java
Presentation pres = new Presentation();
```
Αυτή η γραμμή κώδικα δημιουργεί μια νέα παρουσίαση. Σκεφτείτε το σαν να ανοίγετε ένα κενό αρχείο PowerPoint όπου θα προσθέσετε όλο το περιεχόμενό σας.
## Βήμα 3: Προσθέστε σχήματα στη διαφάνεια
### Αποκτήστε την Πρώτη Διαφάνεια
Πριν προσθέσουμε σχήματα, πρέπει να λάβουμε μια αναφορά στην πρώτη διαφάνεια της παρουσίασής μας. Από προεπιλογή, μια νέα παρουσίαση περιέχει μια κενή διαφάνεια.
```java
ISlide sld = pres.getSlides().get_Item(0);
```
### Προσθέστε σχήματα ορθογωνίου
Τώρα, ας προσθέσουμε τρία ορθογώνια σχήματα στη διαφάνεια μας. Αυτά τα σχήματα θα δείξουν τα διαφορετικά στυλ σύνδεσης γραμμών.
```java
IShape shp1 = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 100, 150, 75);
IShape shp2 = sld.getShapes().addAutoShape(ShapeType.Rectangle, 300, 100, 150, 75);
IShape shp3 = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 250, 150, 75);
```
Σε αυτό το βήμα, προσθέτουμε τρία ορθογώνια σε καθορισμένες θέσεις στη διαφάνεια. Κάθε ορθογώνιο αργότερα θα διαμορφωθεί διαφορετικά για να παρουσιάσει διάφορα στυλ ένωσης.
## Βήμα 4: Δώστε στυλ στα σχήματα
### Ορίστε το χρώμα πλήρωσης
Θέλουμε τα παραλληλόγραμμά μας να γεμίσουν με ένα μονόχρωμο. Εδώ, επιλέγουμε μαύρο για το χρώμα γεμίσματος.
```java
shp1.getFillFormat().setFillType(FillType.Solid);
shp1.getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp2.getFillFormat().setFillType(FillType.Solid);
shp2.getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp3.getFillFormat().setFillType(FillType.Solid);
shp3.getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```
### Ορίστε το πλάτος και το χρώμα γραμμής
Στη συνέχεια, ορίζουμε το πλάτος της γραμμής και το χρώμα για κάθε ορθογώνιο. Αυτό βοηθά στην οπτική διαφοροποίηση των στυλ σύνδεσης.
```java
shp1.getLineFormat().setWidth(15);
shp2.getLineFormat().setWidth(15);
shp3.getLineFormat().setWidth(15);
shp1.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp1.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
shp2.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp2.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
shp3.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp3.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```
## Βήμα 5: Εφαρμογή Join Styles
Το κύριο σημείο αυτού του σεμιναρίου είναι η ρύθμιση των στυλ σύνδεσης γραμμής. Θα χρησιμοποιήσουμε τρία διαφορετικά στυλ: Mitre, Bevel και Round.
```java
shp1.getLineFormat().setJoinStyle(LineJoinStyle.Miter);
shp2.getLineFormat().setJoinStyle(LineJoinStyle.Bevel);
shp3.getLineFormat().setJoinStyle(LineJoinStyle.Round);
```
Κάθε στυλ ένωσης γραμμής δίνει στα σχήματα μια μοναδική εμφάνιση στις γωνίες όπου συναντώνται οι γραμμές. Αυτό μπορεί να είναι ιδιαίτερα χρήσιμο για τη δημιουργία οπτικά διακριτών διαγραμμάτων ή απεικονίσεων.
## Βήμα 6: Προσθήκη κειμένου στα σχήματα
Για να καταστεί σαφές τι αντιπροσωπεύει κάθε σχήμα, προσθέτουμε κείμενο σε κάθε ορθογώνιο που περιγράφει το στυλ ένωσης που χρησιμοποιείται.
```java
((IAutoShape) shp1).getTextFrame().setText("This is Miter Join Style");
((IAutoShape) shp2).getTextFrame().setText("This is Bevel Join Style");
((IAutoShape) shp3).getTextFrame().setText("This is Round Join Style");
```
Η προσθήκη κειμένου βοηθά στον εντοπισμό των διαφορετικών στυλ όταν παρουσιάζετε ή μοιράζεστε τη διαφάνεια.
## Βήμα 7: Αποθηκεύστε την Παρουσίαση
Τέλος, αποθηκεύουμε την παρουσίασή μας στον καθορισμένο κατάλογο.
```java
pres.save(dataDir + "RectShpLnJoin_out.pptx", SaveFormat.Pptx);
```
Αυτή η εντολή εγγράφει την παρουσίαση σε ένα αρχείο PPTX, το οποίο μπορείτε να ανοίξετε με το Microsoft PowerPoint ή οποιοδήποτε άλλο συμβατό λογισμικό.
## συμπέρασμα
Και εκεί το έχετε! Μόλις δημιουργήσατε μια διαφάνεια PowerPoint με τρία ορθογώνια, το καθένα από τα οποία εμφανίζει διαφορετικό στυλ σύνδεσης γραμμής χρησιμοποιώντας το Aspose.Slides για Java. Αυτό το σεμινάριο όχι μόνο σας βοηθά να κατανοήσετε τα βασικά του Aspose.Slides αλλά δείχνει επίσης πώς να βελτιώσετε τις παρουσιάσεις σας με μοναδικά στυλ. Καλή παρουσίαση!
## Συχνές ερωτήσεις
### Τι είναι το Aspose.Slides για Java;
Το Aspose.Slides για Java είναι ένα ισχυρό API για τη δημιουργία, τον χειρισμό και τη διαχείριση παρουσιάσεων του PowerPoint μέσω προγραμματισμού.
### Μπορώ να χρησιμοποιήσω το Aspose.Slides για Java σε οποιοδήποτε IDE;
Ναι, μπορείτε να χρησιμοποιήσετε το Aspose.Slides για Java σε οποιοδήποτε IDE που υποστηρίζεται από Java όπως το IntelliJ IDEA, το Eclipse ή το NetBeans.
### Υπάρχει δωρεάν δοκιμή για το Aspose.Slides για Java;
 Ναι, μπορείτε να λάβετε δωρεάν δοκιμή από[εδώ](https://releases.aspose.com/).
### Τι είναι τα στυλ σύνδεσης γραμμής στο PowerPoint;
Τα στυλ σύνδεσης γραμμής αναφέρονται στο σχήμα των γωνιών όπου συναντώνται δύο γραμμές. Τα κοινά στυλ περιλαμβάνουν Mitre, Bevel και Round.
### Πού μπορώ να βρω περισσότερη τεκμηρίωση για το Aspose.Slides for Java;
 Μπορείτε να βρείτε αναλυτική τεκμηρίωση[εδώ](https://reference.aspose.com/slides/java/).