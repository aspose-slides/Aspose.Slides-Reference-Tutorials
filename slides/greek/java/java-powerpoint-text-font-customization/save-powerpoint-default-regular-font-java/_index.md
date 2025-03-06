---
title: Αποθηκεύστε το PowerPoint με την προεπιλεγμένη κανονική γραμματοσειρά χρησιμοποιώντας Java
linktitle: Αποθηκεύστε το PowerPoint με την προεπιλεγμένη κανονική γραμματοσειρά χρησιμοποιώντας Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Μάθετε πώς να χειρίζεστε τις παρουσιάσεις του PowerPoint μέσω προγραμματισμού χρησιμοποιώντας το Aspose.Slides για Java. Κύριος χειρισμός Java PowerPoint με οδηγίες βήμα προς βήμα.
weight: 12
url: /el/java/java-powerpoint-text-font-customization/save-powerpoint-default-regular-font-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Εισαγωγή
Στον τομέα της ανάπτυξης Java, η δημιουργία και ο χειρισμός παρουσιάσεων του PowerPoint μέσω προγραμματισμού μπορεί να βελτιώσει σημαντικά την παραγωγικότητα και τις επιλογές προσαρμογής. Το Aspose.Slides για Java είναι μια ισχυρή βιβλιοθήκη που δίνει τη δυνατότητα στους προγραμματιστές να χειρίζονται αποτελεσματικά αρχεία PowerPoint, προσφέροντας ένα ολοκληρωμένο σύνολο λειτουργιών από απλές τροποποιήσεις έως σύνθετες παρουσιάσεις.
## Προαπαιτούμενα
Πριν ξεκινήσετε τη χρήση του Aspose.Slides για Java, βεβαιωθείτε ότι έχετε ρυθμίσει τις ακόλουθες προϋποθέσεις:
1. Java Development Kit (JDK): Το Aspose.Slides for Java απαιτεί JDK 1.8 ή νεότερη έκδοση για να λειτουργήσει σωστά.
2. Aspose.Slides για Java JAR: Κατεβάστε την πιο πρόσφατη έκδοση του Aspose.Slides για Java από[εδώ](https://releases.aspose.com/slides/java/).
3. Ενσωματωμένο περιβάλλον ανάπτυξης (IDE): Χρησιμοποιήστε το IntelliJ IDEA, το Eclipse ή άλλο Java IDE της επιλογής σας.
4. Βασική κατανόηση της Java: Η εξοικείωση με τις βασικές αρχές της γλώσσας προγραμματισμού Java είναι απαραίτητη.

## Εισαγωγή πακέτων
Για να ξεκινήσετε να χρησιμοποιείτε το Aspose.Slides για Java, εισαγάγετε τα απαραίτητα πακέτα:
```java
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.PdfOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```
Αυτό διασφαλίζει ότι έχετε πρόσβαση σε όλες τις κλάσεις και τις μεθόδους που παρέχονται από το Aspose.Slides για Java.
## Βήμα 1: Ρύθμιση του έργου σας
Αρχικά, δημιουργήστε ένα νέο έργο Java στο IDE σας και συμπεριλάβετε το αρχείο Aspose.Slides for Java JAR στη διαδρομή κατασκευής του έργου σας.
## Βήμα 2: Αρχικοποίηση αντικειμένου παρουσίασης
 Στιγμιότυπο α`Presentation` αντικείμενο φορτώνοντας ένα υπάρχον αρχείο PowerPoint (.pptx) από τον τοπικό σας κατάλογο.
```java
String dataDir = "Your Document Directory";
String outPath = "Your Output Directory";
// Φόρτωση παρουσίασης
Presentation pres = new Presentation(dataDir + "DefaultFonts.pptx");
```
 Αντικαθιστώ`"Your Document Directory"` και`"Your Output Directory"` με τις πραγματικές διαδρομές αρχείων σας.
## Βήμα 3: Αποθηκεύστε την παρουσίαση με τις προεπιλεγμένες κανονικές γραμματοσειρές
 Καθορίστε την προεπιλεγμένη κανονική γραμματοσειρά για τις μορφές εξόδου (HTML και PDF) χρησιμοποιώντας`HtmlOptions` και`PdfOptions` αντίστοιχα.
```java
try {
    // Επιλογές αποθήκευσης HTML
    HtmlOptions htmlOpts = new HtmlOptions();
    htmlOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.html", SaveFormat.Html, htmlOpts);
    htmlOpts.setDefaultRegularFont("Lucida Console");
    pres.save(outPath + "Presentation-out-LucidaConsole.html", SaveFormat.Html, htmlOpts);
    // Επιλογές αποθήκευσης PDF
    PdfOptions pdfOpts = new PdfOptions();
    pdfOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.pdf", SaveFormat.Pdf, pdfOpts);
} finally {
    if (pres != null) pres.dispose();
}
```
 Φροντίστε να αντικαταστήσετε`"Arial Black"` και`"Lucida Console"` με τις επιθυμητές προεπιλεγμένες κανονικές γραμματοσειρές.

## συμπέρασμα
Ακολουθώντας αυτά τα βήματα, έχετε μάθει πώς να χειρίζεστε αποτελεσματικά τις παρουσιάσεις του PowerPoint χρησιμοποιώντας το Aspose.Slides για Java. Αυτή η δυνατότητα σάς επιτρέπει να αυτοματοποιείτε εργασίες, να προσαρμόζετε παρουσιάσεις και να βελτιώνετε τις εφαρμογές σας Java με προηγμένες λειτουργίες χειρισμού PowerPoint.
## Συχνές ερωτήσεις
### Μπορεί το Aspose.Slides για Java να λειτουργήσει με παλαιότερες εκδόσεις του JDK;
Το Aspose.Slides για Java απαιτεί JDK 1.8 ή νεότερη έκδοση για συμβατότητα.
### Πώς μπορώ να λάβω προσωρινή άδεια χρήσης για το Aspose.Slides για Java;
 Μπορείτε να αποκτήσετε προσωρινή άδεια από[εδώ](https://purchase.aspose.com/temporary-license/).
### Πού μπορώ να βρω πιο λεπτομερή τεκμηρίωση για το Aspose.Slides για Java;
 Εξερευνήστε την πλήρη τεκμηρίωση[εδώ](https://reference.aspose.com/slides/java/).
### Υπάρχει διαθέσιμη υποστήριξη κοινότητας για το Aspose.Slides για Java;
 Ναι, μπορείτε να λάβετε υποστήριξη από την κοινότητα[εδώ](https://forum.aspose.com/c/slides/11).
### Μπορώ να δοκιμάσω το Aspose.Slides για Java δωρεάν;
 Ναι, κατεβάστε μια δωρεάν δοκιμαστική έκδοση[εδώ](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
