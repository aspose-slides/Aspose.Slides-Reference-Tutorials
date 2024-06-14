---
title: Διαίρεση κελιών σε πίνακα PowerPoint χρησιμοποιώντας Java
linktitle: Διαίρεση κελιών σε πίνακα PowerPoint χρησιμοποιώντας Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Μάθετε πώς να χωρίζετε, να συγχωνεύετε και να μορφοποιείτε κελιά πίνακα PowerPoint μέσω προγραμματισμού χρησιμοποιώντας το Aspose.Slides για Java. Κύριος σχεδιασμός παρουσίασης.
type: docs
weight: 11
url: /el/java/java-powerpoint-table-manipulation/split-cells-powerpoint-table-java/
---
## Εισαγωγή
Σε αυτό το σεμινάριο, θα μάθετε πώς να χειρίζεστε πίνακες PowerPoint σε Java χρησιμοποιώντας το Aspose.Slides. Οι πίνακες είναι ένα θεμελιώδες στοιχείο στις παρουσιάσεις, που χρησιμοποιούνται συχνά για την αποτελεσματική οργάνωση και παρουσίαση δεδομένων. Το Aspose.Slides παρέχει ισχυρές δυνατότητες δημιουργίας, τροποποίησης και βελτίωσης πινάκων μέσω προγραμματισμού, προσφέροντας ευελιξία στο σχεδιασμό και τη διάταξη.
## Προαπαιτούμενα
Πριν ξεκινήσετε αυτό το σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
- Βασικές γνώσεις προγραμματισμού Java.
- Το JDK (Java Development Kit) είναι εγκατεστημένο στο μηχάνημά σας.
-  Aspose.Slides για βιβλιοθήκη Java. Μπορείτε να το κατεβάσετε από[εδώ](https://releases.aspose.com/slides/java/).
- Ολοκληρωμένο περιβάλλον ανάπτυξης (IDE) όπως το Eclipse, το IntelliJ IDEA ή οποιοδήποτε άλλο της επιλογής σας.

## Εισαγωγή πακέτων
Για να ξεκινήσετε να εργάζεστε με το Aspose.Slides για Java, πρέπει να εισαγάγετε τα απαραίτητα πακέτα στο έργο σας Java:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## Βήμα 1: Ρύθμιση της παρουσίασης
 Πρώτα, δημιουργήστε το`Presentation` τάξη για να δημιουργήσετε μια νέα παρουσίαση PowerPoint.
```java
// Η διαδρομή προς τον κατάλογο όπου θέλετε να αποθηκεύσετε την παρουσίαση εξόδου
String dataDir = "Your_Document_Directory/";
// Κλάση Instantiation Presentation που αντιπροσωπεύει το αρχείο PPTX
Presentation presentation = new Presentation();
```
## Βήμα 2: Πρόσβαση στη διαφάνεια και προσθήκη πίνακα
Αποκτήστε πρόσβαση στην πρώτη διαφάνεια και προσθέστε ένα σχήμα πίνακα σε αυτήν. Ορίστε στήλες με πλάτη και σειρές με ύψη.
```java
try {
    // Πρόσβαση στην πρώτη διαφάνεια
    ISlide slide = presentation.getSlides().get_Item(0);
    // Ορίστε στήλες με πλάτη και σειρές με ύψη
    double[] dblCols = {70, 70, 70, 70};
    double[] dblRows = {70, 70, 70, 70};
    // Προσθέστε σχήμα πίνακα στη διαφάνεια
    ITable table = slide.getShapes().addTable(100, 50, dblCols, dblRows);
```
## Βήμα 3: Ορισμός μορφής περιγράμματος για κάθε κελί
Επαναλάβετε σε κάθε κελί του πίνακα και ορίστε τη μορφοποίηση περιγράμματος (χρώμα, πλάτος, κ.λπ.).
```java
    // Ορίστε τη μορφή περιγράμματος για κάθε κελί
    for (IRow row : table.getRows()) {
        for (ICell cell : (Iterable<ICell>) row) {
            cell.getCellFormat().getBorderTop().getFillFormat().setFillType(FillType.Solid);
            cell.getCellFormat().getBorderTop().getFillFormat().getSolidFillColor().setColor(Color.RED);
            cell.getCellFormat().getBorderTop().setWidth(5);
            // Ορίστε παρόμοια μορφοποίηση για άλλα περιγράμματα (κάτω, αριστερά, δεξιά)
            // ...
        }
    }
```
## Βήμα 4: Συγχώνευση κελιών
Συγχώνευση κελιών στον πίνακα όπως απαιτείται. Για παράδειγμα, συγχώνευση κελιών (1,1) έως (2,1) και (1,2) έως (2,2).
```java
    // Συγχώνευση κελιών (1, 1) x (2, 1)
    table.mergeCells(table.get_Item(1, 1), table.get_Item(2, 1), false);
    // Συγχώνευση κελιών (1, 2) x (2, 2)
    table.mergeCells(table.get_Item(1, 2), table.get_Item(2, 2), false);
```
## Βήμα 5: Διαίρεση κυττάρων
Διαχωρίστε ένα συγκεκριμένο κελί σε πολλά κελιά με βάση το πλάτος.
```java
    // Διαίρεση κελιού (1, 1)
    table.get_Item(1, 1).splitByWidth(table.get_Item(2, 1).getWidth() / 2);
```
## Βήμα 6: Αποθήκευση της παρουσίασης
Αποθηκεύστε την τροποποιημένη παρουσίαση στο δίσκο.
```java
    // Γράψτε το PPTX στο δίσκο
    presentation.save(dataDir + "CellSplit_out.pptx", SaveFormat.Pptx);
} finally {
    // Απόρριψη αντικειμένου παρουσίασης
    if (presentation != null) presentation.dispose();
}
```

## συμπέρασμα
Ο χειρισμός πινάκων PowerPoint μέσω προγραμματισμού χρησιμοποιώντας το Aspose.Slides για Java παρέχει έναν ισχυρό τρόπο για την αποτελεσματική προσαρμογή των παρουσιάσεων. Ακολουθώντας αυτό το σεμινάριο, έχετε μάθει πώς να χωρίζετε κελιά, να συγχωνεύετε κελιά και να ορίζετε δυναμικά περιθώρια κελιών, βελτιώνοντας την ικανότητά σας να δημιουργείτε οπτικά ελκυστικές παρουσιάσεις μέσω προγραμματισμού.

## Συχνές ερωτήσεις
### Πού μπορώ να βρω την τεκμηρίωση για το Aspose.Slides για Java;
 Μπορείτε να βρείτε την τεκμηρίωση[εδώ](https://reference.aspose.com/slides/java/).
### Πώς μπορώ να κατεβάσω το Aspose.Slides για Java;
 Μπορείτε να το κατεβάσετε από[αυτός ο σύνδεσμος](https://releases.aspose.com/slides/java/).
### Υπάρχει διαθέσιμη δωρεάν δοκιμή για το Aspose.Slides για Java;
 Ναι, μπορείτε να λάβετε δωρεάν δοκιμή από[εδώ](https://releases.aspose.com/).
### Πού μπορώ να λάβω υποστήριξη για το Aspose.Slides για Java;
 Μπορείτε να λάβετε υποστήριξη από το φόρουμ Aspose.Slides[εδώ](https://forum.aspose.com/c/slides/11).
### Μπορώ να αποκτήσω μια προσωρινή άδεια χρήσης για το Aspose.Slides για Java;
 Ναι, μπορείτε να λάβετε προσωρινή άδεια από[εδώ](https://purchase.aspose.com/temporary-license/).