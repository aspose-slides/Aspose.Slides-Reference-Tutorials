---
"description": "Μάθετε πώς να δημιουργήσετε το ορθογώνιο τμήματος στο PowerPoint χρησιμοποιώντας το Aspose.Slides για Java με αυτό το λεπτομερές, βήμα προς βήμα σεμινάριο. Ιδανικό για προγραμματιστές Java."
"linktitle": "Λήψη Partition Rectangle στο PowerPoint με Java"
"second_title": "Aspose.Slides API επεξεργασίας Java PowerPoint"
"title": "Λήψη Partition Rectangle στο PowerPoint με Java"
"url": "/el/java/java-powerpoint-advanced-paragraph-font-properties/get-portion-rectangle-powerpoint-java/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Λήψη Partition Rectangle στο PowerPoint με Java

## Εισαγωγή
Η δημιουργία δυναμικών παρουσιάσεων σε Java είναι παιχνιδάκι με το Aspose.Slides για Java. Σε αυτό το σεμινάριο, θα εμβαθύνουμε στις λεπτομέρειες της δημιουργίας του ορθογωνίου τμήματος στο PowerPoint χρησιμοποιώντας το Aspose.Slides. Θα καλύψουμε τα πάντα, από τη ρύθμιση του περιβάλλοντός σας έως την ανάλυση του κώδικα βήμα προς βήμα. Ας ξεκινήσουμε, λοιπόν!
## Προαπαιτούμενα
Πριν προχωρήσουμε στον κώδικα, ας βεβαιωθούμε ότι έχετε όλα όσα χρειάζεστε για να ακολουθήσετε ομαλά:
1. Κιτ Ανάπτυξης Java (JDK): Βεβαιωθείτε ότι έχετε εγκαταστήσει το JDK 8 ή νεότερη έκδοση στον υπολογιστή σας.
2. Aspose.Slides για Java: Κατεβάστε την τελευταία έκδοση από [εδώ](https://releases.aspose.com/slides/java/).
3. Ολοκληρωμένο Περιβάλλον Ανάπτυξης (IDE): Eclipse, IntelliJ IDEA ή οποιοδήποτε άλλο Java IDE της επιλογής σας.
4. Βασικές γνώσεις Java: Η κατανόηση του προγραμματισμού Java είναι απαραίτητη.
## Εισαγωγή πακέτων
Πρώτα απ 'όλα, ας εισαγάγουμε τα απαραίτητα πακέτα. Αυτά θα περιλαμβάνουν το Aspose.Slides και μερικά άλλα για την αποτελεσματική διαχείριση της εργασίας μας.
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.awt.*;
import java.awt.geom.Rectangle2D;
```
## Βήμα 1: Ρύθμιση της παρουσίασης
Το πρώτο βήμα είναι να δημιουργήσετε μια νέα παρουσίαση. Αυτή θα είναι η βάση πάνω στην οποία θα εργαστούμε.
```java
Presentation pres = new Presentation();
```
## Βήμα 2: Δημιουργία πίνακα
Τώρα, ας προσθέσουμε έναν πίνακα στην πρώτη διαφάνεια της παρουσίασής μας. Αυτός ο πίνακας θα περιέχει τα κελιά όπου θα προσθέσουμε το κείμενό μας.
```java
ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```
## Βήμα 3: Προσθήκη παραγράφων σε κελιά
Στη συνέχεια, θα δημιουργήσουμε παραγράφους και θα τις προσθέσουμε σε ένα συγκεκριμένο κελί στον πίνακα. Αυτό περιλαμβάνει την εκκαθάριση οποιουδήποτε υπάρχοντος κειμένου και στη συνέχεια την προσθήκη νέων παραγράφων.
```java
// Δημιουργία παραγράφων
IParagraph paragraph0 = new Paragraph();
paragraph0.getPortions().add(new Portion("Text "));
paragraph0.getPortions().add(new Portion("in0"));
paragraph0.getPortions().add(new Portion(" Cell"));
IParagraph paragraph1 = new Paragraph();
paragraph1.setText("On0");
IParagraph paragraph2 = new Paragraph();
paragraph2.getPortions().add(new Portion("Hi there "));
paragraph2.getPortions().add(new Portion("col0"));
// Προσθήκη κειμένου στο κελί του πίνακα
ICell cell = tbl.get_Item(1, 1);
cell.getTextFrame().getParagraphs().clear();
cell.getTextFrame().getParagraphs().add(paragraph0);
cell.getTextFrame().getParagraphs().add(paragraph1);
cell.getTextFrame().getParagraphs().add(paragraph2);
```
## Βήμα 4: Προσθήκη πλαισίου κειμένου σε αυτόματο σχήμα
Για να κάνουμε την παρουσίασή μας πιο δυναμική, θα προσθέσουμε ένα πλαίσιο κειμένου σε ένα Αυτόματο Σχήμα και θα ορίσουμε την ευθυγράμμισή του.
```java
IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 400, 100, 60, 120);
autoShape.getTextFrame().setText("Text in shape");
autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```
## Βήμα 5: Υπολογισμός συντεταγμένων
Πρέπει να λάβουμε τις συντεταγμένες της επάνω αριστερής γωνίας του κελιού του πίνακα. Αυτό θα μας βοηθήσει να τοποθετήσουμε τα σχήματα με ακρίβεια.
```java
double x = tbl.getX() + cell.getOffsetX();
double y = tbl.getY() + cell.getOffsetY();
```
## Βήμα 6: Προσθήκη πλαισίων σε παραγράφους και τμήματα
Χρησιμοποιώντας το `IParagraph.getRect()` και `IPortion.getRect()` Με τις μεθόδους, μπορούμε να προσθέσουμε πλαίσια στις παραγράφους και τα τμήματά μας. Αυτό περιλαμβάνει την επανάληψη των παραγράφων και των τμημάτων, τη δημιουργία σχημάτων γύρω τους και την προσαρμογή της εμφάνισής τους.
```java
for (IParagraph para : cell.getTextFrame().getParagraphs()) {
    if ("".equals(para.getText())) continue;
    Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
    IAutoShape shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle,
        (float) rect.getX() + (float) x,
        (float) rect.getY() + (float) y,
        (float) rect.getWidth(),
        (float) rect.getHeight()
    );
    shape.getFillFormat().setFillType(FillType.NoFill);
    shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
    shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
    for (IPortion portion : para.getPortions()) {
        if (portion.getText().contains("0")) {
            rect = portion.getRect();
            shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
                ShapeType.Rectangle,
                (float) rect.getX() + (float) x,
                (float) rect.getY() + (float) y,
                (float) rect.getWidth(),
                (float) rect.getHeight()
            );
            shape.getFillFormat().setFillType(FillType.NoFill);
        }
    }
}
```
## Βήμα 7: Προσθήκη πλαισίων σε παραγράφους αυτόματης διαμόρφωσης
Ομοίως, θα προσθέσουμε πλαίσια στις παραγράφους στο AutoShape μας, ενισχύοντας την οπτική ελκυστικότητα της παρουσίασης.
```java
for (IParagraph para : autoShape.getTextFrame().getParagraphs()) {
    Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
    IAutoShape shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle,
        (float) rect.getX() + autoShape.getX(),
        (float) rect.getY() + autoShape.getY(),
        (float) rect.getWidth(),
        (float) rect.getHeight()
    );
    shape.getFillFormat().setFillType(FillType.NoFill);
    shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
    shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
}
```
## Βήμα 8: Αποθήκευση της παρουσίασης
Τέλος, θα αποθηκεύσουμε την παρουσίασή μας σε μια καθορισμένη διαδρομή.
```java
String outPath = "path_to_output_directory";
pres.save(outPath + "GetRect_Out.pptx", SaveFormat.Pptx);
```
## Βήμα 9: Καθαρισμός
Είναι καλή πρακτική να απορρίπτετε το αντικείμενο παρουσίασης για να ελευθερώνετε πόρους.
```java
if (pres != null) pres.dispose();
```
## Σύναψη
Συγχαρητήρια! Μάθατε με επιτυχία πώς να δημιουργήσετε το ορθογώνιο τμήματος στο PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Αυτή η ισχυρή βιβλιοθήκη ανοίγει έναν κόσμο δυνατοτήτων για τη δημιουργία δυναμικών και οπτικά ελκυστικών παρουσιάσεων μέσω προγραμματισμού. Βυθιστείτε βαθύτερα στο Aspose.Slides και εξερευνήστε περισσότερες λειτουργίες για να βελτιώσετε περαιτέρω τις παρουσιάσεις σας.
## Συχνές ερωτήσεις
### Τι είναι το Aspose.Slides για Java;
Το Aspose.Slides για Java είναι μια ισχυρή βιβλιοθήκη που επιτρέπει στους προγραμματιστές να δημιουργούν, να τροποποιούν και να χειρίζονται παρουσιάσεις PowerPoint μέσω προγραμματισμού.
### Μπορώ να χρησιμοποιήσω το Aspose.Slides για Java σε εμπορικά έργα;
Ναι, το Aspose.Slides για Java μπορεί να χρησιμοποιηθεί σε εμπορικά έργα. Μπορείτε να αγοράσετε μια άδεια χρήσης από [εδώ](https://purchase.aspose.com/buy).
### Υπάρχει διαθέσιμη δωρεάν δοκιμαστική έκδοση για το Aspose.Slides για Java;
Ναι, μπορείτε να κατεβάσετε μια δωρεάν δοκιμαστική έκδοση από [εδώ](https://releases.aspose.com/).
### Πού μπορώ να βρω την τεκμηρίωση για το Aspose.Slides για Java;
Η τεκμηρίωση είναι διαθέσιμη [εδώ](https://reference.aspose.com/slides/java/).
### Πώς μπορώ να λάβω υποστήριξη για το Aspose.Slides για Java;
Μπορείτε να λάβετε υποστήριξη από το φόρουμ Aspose [εδώ](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}