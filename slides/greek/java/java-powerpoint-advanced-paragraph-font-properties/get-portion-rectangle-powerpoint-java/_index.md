---
title: Αποκτήστε το Ortion Rectangle στο PowerPoint με Java
linktitle: Αποκτήστε το Ortion Rectangle στο PowerPoint με Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Μάθετε πώς μπορείτε να αποκτήσετε το ορθογώνιο τμήματος στο PowerPoint χρησιμοποιώντας το Aspose.Slides για Java με αυτόν τον λεπτομερή, βήμα προς βήμα εκμάθηση. Ιδανικό για προγραμματιστές Java.
weight: 12
url: /el/java/java-powerpoint-advanced-paragraph-font-properties/get-portion-rectangle-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Αποκτήστε το Ortion Rectangle στο PowerPoint με Java

## Εισαγωγή
Η δημιουργία δυναμικών παρουσιάσεων σε Java είναι παιχνιδάκι με το Aspose.Slides for Java. Σε αυτό το σεμινάριο, θα ρίξουμε μια ματιά στη λεπτομέρεια της λήψης του ορθογωνίου τμήματος στο PowerPoint χρησιμοποιώντας το Aspose.Slides. Θα καλύψουμε τα πάντα, από τη ρύθμιση του περιβάλλοντος σας έως την ανάλυση του κώδικα βήμα προς βήμα. Λοιπόν, ας ξεκινήσουμε!
## Προαπαιτούμενα
Προτού μεταβούμε στον κώδικα, ας βεβαιωθούμε ότι έχετε όλα όσα χρειάζεστε για να ακολουθήσετε ομαλά:
1. Java Development Kit (JDK): Βεβαιωθείτε ότι έχετε εγκαταστήσει το JDK 8 ή νεότερο στον υπολογιστή σας.
2.  Aspose.Slides για Java: Κάντε λήψη της πιο πρόσφατης έκδοσης από[εδώ](https://releases.aspose.com/slides/java/).
3. Ενσωματωμένο περιβάλλον ανάπτυξης (IDE): Eclipse, IntelliJ IDEA ή οποιοδήποτε άλλο Java IDE της επιλογής σας.
4. Βασική γνώση Java: Η κατανόηση του προγραμματισμού Java είναι απαραίτητη.
## Εισαγωγή πακέτων
Πρώτα πρώτα, ας εισάγουμε τα απαραίτητα πακέτα. Αυτό θα περιλαμβάνει Aspose.Slides και μερικά άλλα για τον αποτελεσματικό χειρισμό της εργασίας μας.
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.awt.*;
import java.awt.geom.Rectangle2D;
```
## Βήμα 1: Ρύθμιση της παρουσίασης
Το πρώτο βήμα είναι να δημιουργήσετε μια νέα παρουσίαση. Αυτός θα είναι ο καμβάς μας για να δουλέψουμε.
```java
Presentation pres = new Presentation();
```
## Βήμα 2: Δημιουργία πίνακα
Τώρα, ας προσθέσουμε έναν πίνακα στην πρώτη διαφάνεια της παρουσίασής μας. Αυτός ο πίνακας θα περιέχει τα κελιά όπου θα προσθέσουμε το κείμενό μας.
```java
ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```
## Βήμα 3: Προσθήκη παραγράφων σε κελιά
Στη συνέχεια, θα δημιουργήσουμε παραγράφους και θα τις προσθέσουμε σε ένα συγκεκριμένο κελί του πίνακα. Αυτό περιλαμβάνει την εκκαθάριση οποιουδήποτε υπάρχοντος κειμένου και στη συνέχεια την προσθήκη νέων παραγράφων.
```java
// Δημιουργήστε παραγράφους
IParagraph paragraph0 = new Paragraph();
paragraph0.getPortions().add(new Portion("Text "));
paragraph0.getPortions().add(new Portion("in0"));
paragraph0.getPortions().add(new Portion(" Cell"));
IParagraph paragraph1 = new Paragraph();
paragraph1.setText("On0");
IParagraph paragraph2 = new Paragraph();
paragraph2.getPortions().add(new Portion("Hi there "));
paragraph2.getPortions().add(new Portion("col0"));
// Προσθέστε κείμενο στο κελί του πίνακα
ICell cell = tbl.get_Item(1, 1);
cell.getTextFrame().getParagraphs().clear();
cell.getTextFrame().getParagraphs().add(paragraph0);
cell.getTextFrame().getParagraphs().add(paragraph1);
cell.getTextFrame().getParagraphs().add(paragraph2);
```
## Βήμα 4: Προσθήκη πλαισίου κειμένου σε αυτόματο σχήμα
Για να κάνουμε την παρουσίασή μας πιο δυναμική, θα προσθέσουμε ένα πλαίσιο κειμένου σε ένα AutoShape και θα ορίσουμε την ευθυγράμμισή του.
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
 Χρησιμοποιώντας την`IParagraph.getRect()` και`IPortion.getRect()`μεθόδους, μπορούμε να προσθέσουμε πλαίσια στις παραγράφους και τα τμήματα μας. Αυτό περιλαμβάνει την επανάληψη στις παραγράφους και τα τμήματα, τη δημιουργία σχημάτων γύρω τους και την προσαρμογή της εμφάνισής τους.
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
## Βήμα 7: Προσθήκη πλαισίων σε παραγράφους AutoShape
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
Είναι καλή πρακτική να απορρίπτετε το αντικείμενο παρουσίασης για να ελευθερώσετε πόρους.
```java
if (pres != null) pres.dispose();
```
## συμπέρασμα
Συγχαρητήρια! Μάθατε με επιτυχία πώς να λαμβάνετε το ορθογώνιο τμήματος στο PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Αυτή η ισχυρή βιβλιοθήκη ανοίγει έναν κόσμο δυνατοτήτων για τη δημιουργία δυναμικών και οπτικά ελκυστικών παρουσιάσεων μέσω προγραμματισμού. Βουτήξτε βαθύτερα στο Aspose.Slides και εξερευνήστε περισσότερες δυνατότητες για να βελτιώσετε περαιτέρω τις παρουσιάσεις σας.
## Συχνές ερωτήσεις
### Τι είναι το Aspose.Slides για Java;
Το Aspose.Slides για Java είναι μια ισχυρή βιβλιοθήκη που επιτρέπει στους προγραμματιστές να δημιουργούν, να τροποποιούν και να χειρίζονται παρουσιάσεις PowerPoint μέσω προγραμματισμού.
### Μπορώ να χρησιμοποιήσω το Aspose.Slides για Java σε εμπορικά έργα;
 Ναι, το Aspose.Slides για Java μπορεί να χρησιμοποιηθεί σε εμπορικά έργα. Μπορείτε να αγοράσετε άδεια από[εδώ](https://purchase.aspose.com/buy).
### Υπάρχει διαθέσιμη δωρεάν δοκιμή για το Aspose.Slides για Java;
 Ναι, μπορείτε να κάνετε λήψη μιας δωρεάν δοκιμής από[εδώ](https://releases.aspose.com/).
### Πού μπορώ να βρω την τεκμηρίωση για το Aspose.Slides για Java;
 Η τεκμηρίωση είναι διαθέσιμη[εδώ](https://reference.aspose.com/slides/java/).
### Πώς μπορώ να λάβω υποστήριξη για το Aspose.Slides για Java;
 Μπορείτε να λάβετε υποστήριξη από το φόρουμ Aspose[εδώ](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
