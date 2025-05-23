---
"description": "Μετατρέψτε παρουσιάσεις PowerPoint σε HTML διατηρώντας παράλληλα τις αρχικές γραμματοσειρές χρησιμοποιώντας το Aspose.Slides για Java."
"linktitle": "Μετατροπή παρουσίασης σε HTML με διατήρηση των αρχικών γραμματοσειρών σε διαφάνειες Java"
"second_title": "Aspose.Slides API επεξεργασίας Java PowerPoint"
"title": "Μετατροπή παρουσίασης σε HTML με διατήρηση των αρχικών γραμματοσειρών σε διαφάνειες Java"
"url": "/el/java/presentation-conversion/convert-presentation-html-preserve-fonts-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Μετατροπή παρουσίασης σε HTML με διατήρηση των αρχικών γραμματοσειρών σε διαφάνειες Java


## Εισαγωγή στη μετατροπή παρουσίασης σε HTML με διατήρηση των αρχικών γραμματοσειρών σε διαφάνειες Java

Σε αυτό το σεμινάριο, θα εξερευνήσουμε πώς να μετατρέψετε μια παρουσίαση PowerPoint (PPTX) σε HTML διατηρώντας παράλληλα τις αρχικές γραμματοσειρές χρησιμοποιώντας το Aspose.Slides για Java. Αυτό θα διασφαλίσει ότι το HTML που προκύπτει μοιάζει πολύ με την εμφάνιση της αρχικής παρουσίασης.

## Βήμα 1: Ρύθμιση του Έργου
Πριν εμβαθύνουμε στον κώδικα, ας βεβαιωθούμε ότι έχετε κάνει τις απαραίτητες ρυθμίσεις:

1. Λήψη Aspose.Slides για Java: Εάν δεν το έχετε κάνει ήδη, κατεβάστε και συμπεριλάβετε τη βιβλιοθήκη Aspose.Slides για Java στο έργο σας.

2. Δημιουργία έργου Java: Ρυθμίστε ένα έργο Java στο αγαπημένο σας IDE και βεβαιωθείτε ότι έχετε έναν φάκελο "lib" όπου μπορείτε να τοποθετήσετε το αρχείο JAR Aspose.Slides.

3. Εισαγωγή απαιτούμενων κλάσεων: Εισαγάγετε τις απαραίτητες κλάσεις στην αρχή του αρχείου Java:

```java
import com.aspose.slides.EmbedAllFontsHtmlController;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Βήμα 2: Μετατροπή παρουσίασης σε HTML με πρωτότυπες γραμματοσειρές

Τώρα, ας μετατρέψουμε μια παρουσίαση PowerPoint σε HTML διατηρώντας παράλληλα τις αρχικές γραμματοσειρές:

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";

// Φόρτωση της παρουσίασης
Presentation pres = new Presentation("input.pptx");

try {
    // Εξαιρούνται οι προεπιλεγμένες γραμματοσειρές παρουσίασης όπως οι Calibri και Arial
    String[] fontNameExcludeList = {"Calibri", "Arial"};
    EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
    
    // Δημιουργήστε επιλογές HTML και ορίστε τον προσαρμοσμένο μορφοποιητή HTML
    HtmlOptions htmlOptionsEmbed = new HtmlOptions();
    htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
    
    // Αποθήκευση της παρουσίασης ως HTML
    pres.save("output.html", SaveFormat.Html, htmlOptionsEmbed);
} finally {
    // Απόρριψη του αντικειμένου παρουσίασης
    if (pres != null) pres.dispose();
}
```

Σε αυτό το απόσπασμα κώδικα:

- Φορτώνουμε την παρουσίαση PowerPoint εισόδου χρησιμοποιώντας `Presentation`.

- Ορίζουμε μια λίστα γραμματοσειρών (`fontNameExcludeList`) που θέλουμε να εξαιρέσουμε από την ενσωμάτωση στην HTML. Αυτό είναι χρήσιμο για την εξαίρεση κοινών γραμματοσειρών όπως Calibri και Arial, με σκοπό τη μείωση του μεγέθους του αρχείου.

- Δημιουργούμε μια παρουσία του `EmbedAllFontsHtmlController` και να του μεταβιβάσετε τη λίστα εξαιρούμενων γραμματοσειρών.

- Δημιουργούμε `HtmlOptions` και ορίστε έναν προσαρμοσμένο μορφοποιητή HTML χρησιμοποιώντας `HtmlFormatter.createCustomFormatter(embedFontsController)`.

- Τέλος, αποθηκεύουμε την παρουσίαση ως HTML με τις καθορισμένες επιλογές.

## Πλήρης πηγαίος κώδικας για τη μετατροπή παρουσίασης σε HTML με διατήρηση των αρχικών γραμματοσειρών σε διαφάνειες Java

```java
// Η διαδρομή προς τον κατάλογο εγγράφων.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation("input.pptx");
try
{
	// εξαίρεση προεπιλεγμένων γραμματοσειρών παρουσίασης
	String[] fontNameExcludeList = {"Calibri", "Arial"};
	EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
	HtmlOptions htmlOptionsEmbed = new HtmlOptions();
	htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
	pres.save("input-PFDinDisplayPro-Regular-installed.html", SaveFormat.Html, htmlOptionsEmbed);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Σύναψη

Σε αυτό το σεμινάριο, μάθατε πώς να μετατρέψετε μια παρουσίαση PowerPoint σε HTML διατηρώντας παράλληλα τις αρχικές γραμματοσειρές χρησιμοποιώντας το Aspose.Slides για Java. Αυτό είναι χρήσιμο όταν θέλετε να διατηρήσετε την οπτική πιστότητα των παρουσιάσεών σας κατά την κοινή χρήση τους στο διαδίκτυο.

## Συχνές ερωτήσεις

### Πώς μπορώ να κατεβάσω το Aspose.Slides για Java;

Μπορείτε να κατεβάσετε το Aspose.Slides για Java από τον ιστότοπο της Aspose. Επισκεφθείτε το [εδώ](https://downloads.aspose.com/slides/java/) για να λάβετε την πιο πρόσφατη έκδοση.

### Μπορώ να προσαρμόσω τη λίστα των εξαιρούμενων γραμματοσειρών;

Ναι, μπορείτε να προσαρμόσετε το `fontNameExcludeList` πίνακα για να συμπεριλάβετε ή να εξαιρέσετε συγκεκριμένες γραμματοσειρές σύμφωνα με τις απαιτήσεις σας.

### Λειτουργεί αυτή η μέθοδος για παλαιότερες μορφές PowerPoint όπως το PPT;

Αυτό το παράδειγμα κώδικα έχει σχεδιαστεί για αρχεία PPTX. Εάν χρειάζεται να μετατρέψετε παλαιότερα αρχεία PPT, ίσως χρειαστεί να κάνετε προσαρμογές στον κώδικα.

### Πώς μπορώ να προσαρμόσω περαιτέρω την έξοδο HTML;

Μπορείτε να εξερευνήσετε το `HtmlOptions` κλάση για να προσαρμόσετε διάφορες πτυχές της εξόδου HTML, όπως το μέγεθος της διαφάνειας, την ποιότητα της εικόνας και άλλα.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}