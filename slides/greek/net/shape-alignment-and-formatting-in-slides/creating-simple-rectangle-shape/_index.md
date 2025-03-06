---
title: Δημιουργία ορθογώνιων σχημάτων με το Aspose.Slides για .NET
linktitle: Δημιουργία απλού σχήματος ορθογωνίου σε διαφάνειες παρουσίασης χρησιμοποιώντας το Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Εξερευνήστε τον κόσμο των δυναμικών παρουσιάσεων PowerPoint με το Aspose.Slides για .NET. Μάθετε πώς να δημιουργείτε ελκυστικά σχήματα ορθογωνίου σε διαφάνειες με αυτόν τον οδηγό βήμα προς βήμα.
weight: 12
url: /el/net/shape-alignment-and-formatting-in-slides/creating-simple-rectangle-shape/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Εισαγωγή
Αν θέλετε να βελτιώσετε τις εφαρμογές σας .NET με δυναμικές και οπτικά ελκυστικές παρουσιάσεις PowerPoint, το Aspose.Slides για .NET είναι η καλύτερη λύση. Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία δημιουργίας ενός απλού σχήματος ορθογωνίου σε διαφάνειες παρουσίασης χρησιμοποιώντας το Aspose.Slides για .NET.
## Προαπαιτούμενα
Πριν βουτήξετε στο σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
- Visual Studio: Βεβαιωθείτε ότι έχετε εγκαταστήσει το Visual Studio στο μηχάνημα ανάπτυξης.
-  Aspose.Slides για .NET: Λήψη και εγκατάσταση της βιβλιοθήκης Aspose.Slides για .NET από[εδώ](https://releases.aspose.com/slides/net/).
- Βασικές γνώσεις C#: Η εξοικείωση με τη γλώσσα προγραμματισμού C# είναι απαραίτητη.
## Εισαγωγή χώρων ονομάτων
Στο έργο σας C#, ξεκινήστε εισάγοντας τους απαραίτητους χώρους ονομάτων για πρόσβαση στις λειτουργίες Aspose.Slides:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Βήμα 1: Ρύθμιση του έργου
Ξεκινήστε δημιουργώντας ένα νέο έργο C# στο Visual Studio. Βεβαιωθείτε ότι το Aspose.Slides for .NET αναφέρεται σωστά στο έργο σας.
## Βήμα 2: Αρχικοποίηση αντικειμένου παρουσίασης
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // Ο κωδικός σας για τα επόμενα βήματα θα βρίσκεται εδώ.
}
```
## Βήμα 3: Λάβετε την πρώτη διαφάνεια
```csharp
ISlide sld = pres.Slides[0];
```
## Βήμα 4: Προσθέστε αυτόματο σχήμα ορθογωνίου
```csharp
sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 150, 150, 50);
```
Αυτός ο κωδικός προσθέτει ένα ορθογώνιο σχήμα στις συντεταγμένες (50, 150) με πλάτος 150 και ύψος 50.
## Βήμα 5: Αποθηκεύστε την Παρουσίαση
```csharp
pres.Save(dataDir + "RectShp1_out.pptx", SaveFormat.Pptx);
```
Αυτό το βήμα αποθηκεύει την παρουσίαση με το προστιθέμενο σχήμα ορθογωνίου στον καθορισμένο κατάλογο.
## συμπέρασμα
Συγχαρητήρια! Δημιουργήσατε με επιτυχία ένα απλό ορθογώνιο σχήμα σε μια διαφάνεια παρουσίασης χρησιμοποιώντας το Aspose.Slides για .NET. Αυτή είναι μόνο η αρχή – Το Aspose.Slides προσφέρει ένα ευρύ φάσμα δυνατοτήτων για περαιτέρω προσαρμογή και βελτίωση των παρουσιάσεών σας.
## Συχνές Ερωτήσεις
### Μπορώ να χρησιμοποιήσω το Aspose.Slides για .NET σε περιβάλλοντα Windows και Linux;
Ναι, το Aspose.Slides για .NET είναι ανεξάρτητο από πλατφόρμα και μπορεί να χρησιμοποιηθεί τόσο σε περιβάλλοντα Windows όσο και σε περιβάλλον Linux.
### Υπάρχει διαθέσιμη δωρεάν δοκιμή για το Aspose.Slides για .NET;
 Ναι, μπορείτε να αποκτήσετε δωρεάν δοκιμή[εδώ](https://releases.aspose.com/).
### Πώς μπορώ να λάβω υποστήριξη για το Aspose.Slides για .NET;
 Επισκέψου το[Φόρουμ Aspose.Slides](https://forum.aspose.com/c/slides/11) για κοινοτική υποστήριξη.
### Μπορώ να αγοράσω μια προσωρινή άδεια χρήσης για το Aspose.Slides για .NET;
 Ναι, μπορείτε να αγοράσετε μια προσωρινή άδεια[εδώ](https://purchase.aspose.com/temporary-license/).
### Πού μπορώ να βρω την τεκμηρίωση για το Aspose.Slides για .NET;
 Ανατρέξτε στην τεκμηρίωση[εδώ](https://reference.aspose.com/slides/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
