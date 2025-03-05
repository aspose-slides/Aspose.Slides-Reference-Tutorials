---
title: Αλλαγή δεδομένων αντικειμένου OLE στο PowerPoint
linktitle: Αλλαγή δεδομένων αντικειμένου OLE στο PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: Μάθετε πώς μπορείτε να αλλάξετε τα δεδομένα αντικειμένου OLE στο PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Ένας οδηγός βήμα προς βήμα για αποτελεσματικές και εύκολες ενημερώσεις.
type: docs
weight: 14
url: /el/java/java-powerpoint-animation-shape-manipulation/change-ole-object-data-powerpoint/
---
## Εισαγωγή
Η αλλαγή των δεδομένων αντικειμένων OLE σε παρουσιάσεις PowerPoint μπορεί να είναι μια κρίσιμη εργασία όταν χρειάζεται να ενημερώσετε το ενσωματωμένο περιεχόμενο χωρίς να κάνετε μη αυτόματη επεξεργασία κάθε διαφάνειας. Αυτός ο περιεκτικός οδηγός θα σας καθοδηγήσει στη διαδικασία χρησιμοποιώντας το Aspose.Slides για Java, μια ισχυρή βιβλιοθήκη που έχει σχεδιαστεί για το χειρισμό παρουσιάσεων PowerPoint. Είτε είστε έμπειρος προγραμματιστής είτε μόλις ξεκινάτε, θα βρείτε αυτό το σεμινάριο χρήσιμο και εύκολο στην παρακολούθηση.
## Προαπαιτούμενα
Πριν βουτήξουμε στον κώδικα, ας βεβαιωθούμε ότι έχετε όλα όσα χρειάζεστε για να ξεκινήσετε.
1.  Java Development Kit (JDK): Βεβαιωθείτε ότι έχετε εγκαταστήσει το JDK στο σύστημά σας. Μπορείτε να το κατεβάσετε από[Ο ιστότοπος της Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides για Java: Κάντε λήψη της πιο πρόσφατης έκδοσης από το[Σελίδα λήψης Aspose.Slides](https://releases.aspose.com/slides/java/).
3. Ενσωματωμένο περιβάλλον ανάπτυξης (IDE): Μπορείτε να χρησιμοποιήσετε οποιοδήποτε Java IDE όπως το IntelliJ IDEA, το Eclipse ή το NetBeans.
4.  Aspose.Cells για Java: Απαιτείται για την τροποποίηση των ενσωματωμένων δεδομένων στο αντικείμενο OLE. Κατεβάστε το από[Σελίδα λήψης Aspose.Cells](https://releases.aspose.com/cells/java/).
5.  Αρχείο παρουσίασης: Έχετε έτοιμο ένα αρχείο PowerPoint με ένα ενσωματωμένο αντικείμενο OLE. Για αυτό το σεμινάριο, ας το ονομάσουμε`ChangeOLEObjectData.pptx`.
## Εισαγωγή πακέτων
Αρχικά, ας εισάγουμε τα απαραίτητα πακέτα στο έργο σας Java.
```java
import com.aspose.cells.OoxmlSaveOptions;
import com.aspose.cells.Workbook;
import com.aspose.slides.*;

import java.io.ByteArrayInputStream;
import java.io.ByteArrayOutputStream;
```

Τώρα, ας αναλύσουμε τη διαδικασία σε απλά, διαχειρίσιμα βήματα.
## Βήμα 1: Φορτώστε την παρουσίαση του PowerPoint
Για να ξεκινήσετε, πρέπει να φορτώσετε την παρουσίαση του PowerPoint που περιέχει το αντικείμενο OLE.
```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx");
```
## Βήμα 2: Πρόσβαση στη διαφάνεια που περιέχει το αντικείμενο OLE
Στη συνέχεια, λάβετε τη διαφάνεια όπου είναι ενσωματωμένο το αντικείμενο OLE.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Βήμα 3: Βρείτε το αντικείμενο OLE στη Διαφάνεια
Επαναλάβετε τα σχήματα στη διαφάνεια για να εντοπίσετε το αντικείμενο OLE.
```java
OleObjectFrame ole = null;
// Διασχίζοντας όλα τα σχήματα για πλαίσιο Ole
for (IShape shape : slide.getShapes()) {
    if (shape instanceof OleObjectFrame) {
        ole = (OleObjectFrame) shape;
        break;
    }
}
```
## Βήμα 4: Εξαγωγή των ενσωματωμένων δεδομένων από το αντικείμενο OLE
Εάν βρεθεί το αντικείμενο OLE, εξάγετε τα ενσωματωμένα δεδομένα του.
```java
if (ole != null) {
    ByteArrayInputStream msln = new ByteArrayInputStream(ole.getEmbeddedData().getEmbeddedFileData());
```
## Βήμα 5: Τροποποιήστε τα ενσωματωμένα δεδομένα χρησιμοποιώντας το Aspose.Cells
Τώρα, χρησιμοποιήστε το Aspose.Cells για να διαβάσετε και να τροποποιήσετε τα ενσωματωμένα δεδομένα, τα οποία σε αυτήν την περίπτωση είναι πιθανό ένα βιβλίο εργασίας του Excel.
```java
    Workbook wb = new Workbook(msln);
    // Τροποποιήστε τα δεδομένα του βιβλίου εργασίας
    wb.getWorksheets().get(0).getCells().get(0, 4).putValue("E");
    wb.getWorksheets().get(0).getCells().get(1, 4).putValue(12);
    wb.getWorksheets().get(0).getCells().get(2, 4).putValue(14);
    wb.getWorksheets().get(0).getCells().get(3, 4).putValue(15);
```
## Βήμα 6: Αποθηκεύστε τα τροποποιημένα δεδομένα πίσω στο αντικείμενο OLE
Αφού κάνετε τις απαραίτητες αλλαγές, αποθηκεύστε το τροποποιημένο βιβλίο εργασίας ξανά στο αντικείμενο OLE.
```java
    ByteArrayOutputStream msout = new ByteArrayOutputStream();
    OoxmlSaveOptions so1 = new OoxmlSaveOptions(SaveFormat.XLSX);
    wb.save(msout, so1);
    IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.toByteArray(), ole.getEmbeddedData().getEmbeddedFileExtension());
    ole.setEmbeddedData(newData);
```
## Βήμα 7: Αποθηκεύστε την ενημερωμένη παρουσίαση
Τέλος, αποθηκεύστε την ενημερωμένη παρουσίαση του PowerPoint.
```java
    pres.save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## συμπέρασμα
Η ενημέρωση των δεδομένων αντικειμένων OLE σε παρουσιάσεις του PowerPoint με χρήση του Aspose.Slides για Java είναι μια απλή διαδικασία αφού τα αναλύσετε σε απλά βήματα. Αυτός ο οδηγός σάς καθοδήγησε στη φόρτωση μιας παρουσίασης, την πρόσβαση και την τροποποίηση των ενσωματωμένων δεδομένων OLE και την αποθήκευση της ενημερωμένης παρουσίασης. Με αυτά τα βήματα, μπορείτε να διαχειριστείτε και να ενημερώσετε αποτελεσματικά το ενσωματωμένο περιεχόμενο στις διαφάνειες του PowerPoint μέσω προγραμματισμού.
## Συχνές ερωτήσεις
### Τι είναι ένα αντικείμενο OLE στο PowerPoint;
Ένα αντικείμενο OLE (Σύνδεση και ενσωμάτωση αντικειμένων) επιτρέπει την ενσωμάτωση περιεχομένου από άλλες εφαρμογές, όπως υπολογιστικά φύλλα Excel, σε διαφάνειες του PowerPoint.
### Μπορώ να χρησιμοποιήσω το Aspose.Slides με άλλες γλώσσες προγραμματισμού;
Ναι, το Aspose.Slides υποστηρίζει πολλές γλώσσες, συμπεριλαμβανομένων των .NET, Python και C++.
### Χρειάζομαι το Aspose.Cells για να τροποποιήσω αντικείμενα OLE στο PowerPoint;
Ναι, εάν το αντικείμενο OLE είναι υπολογιστικό φύλλο του Excel, θα χρειαστείτε το Aspose.Cells για να το τροποποιήσετε.
### Υπάρχει δοκιμαστική έκδοση του Aspose.Slides;
 Ναι, μπορείτε να πάρετε ένα[δωρεάν δοκιμή](https://releases.aspose.com/) για να δοκιμάσετε τις δυνατότητες του Aspose.Slides.
### Πού μπορώ να βρω την τεκμηρίωση για το Aspose.Slides;
 Μπορείτε να βρείτε αναλυτική τεκμηρίωση στο[Σελίδα τεκμηρίωσης Aspose.Slides](https://reference.aspose.com/slides/java/).