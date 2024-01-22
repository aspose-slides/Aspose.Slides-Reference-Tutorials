---
title: Προσθήκη Stretch Offset για Παρουσιάσεις PowerPoint Συμπλήρωσης εικόνας
linktitle: Προσθήκη Stretch Offset για Πλήρωση εικόνας σε διαφάνειες
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Μάθετε πώς να βελτιώνετε τις παρουσιάσεις του PowerPoint με το Aspose.Slides για .NET. Ακολουθήστε έναν οδηγό βήμα προς βήμα για να προσθέσετε μια μετατόπιση τεντώματος για γέμισμα εικόνας.
type: docs
weight: 18
url: /el/net/shape-effects-and-manipulation-in-slides/adding-stretch-offset-image-fill/
---
## Εισαγωγή
Στον δυναμικό κόσμο των παρουσιάσεων, τα γραφικά παίζουν καθοριστικό ρόλο στην αιχμαλωσία της προσοχής του κοινού. Το Aspose.Slides for .NET δίνει τη δυνατότητα στους προγραμματιστές να βελτιώσουν τις παρουσιάσεις τους στο PowerPoint παρέχοντας ένα ισχυρό σύνολο λειτουργιών. Ένα τέτοιο χαρακτηριστικό είναι η δυνατότητα προσθήκης μετατόπισης τεντώματος για γέμισμα εικόνας, επιτρέποντας δημιουργικές και οπτικά ελκυστικές διαφάνειες.
## Προαπαιτούμενα
Πριν ξεκινήσετε το σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
1.  Aspose.Slides for .NET Library: Κάντε λήψη και εγκατάσταση της βιβλιοθήκης από το[Aspose.Slides για τεκμηρίωση .NET](https://reference.aspose.com/slides/net/).
2. Περιβάλλον ανάπτυξης: Βεβαιωθείτε ότι έχετε ρυθμίσει ένα λειτουργικό περιβάλλον ανάπτυξης .NET.
Τώρα, ας ξεκινήσουμε με τον οδηγό βήμα προς βήμα.
## Εισαγωγή χώρων ονομάτων
Αρχικά, εισαγάγετε τους απαραίτητους χώρους ονομάτων για να αξιοποιήσετε τη λειτουργικότητα Aspose.Slides στην εφαρμογή σας .NET.
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
```
## Βήμα 1: Ρύθμιση του έργου σας
Δημιουργήστε ένα νέο έργο .NET στο περιβάλλον ανάπτυξης που προτιμάτε. Βεβαιωθείτε ότι το Aspose.Slides για .NET αναφέρεται σωστά.
## Βήμα 2: Εκκίνηση της τάξης παρουσίασης
 Στιγμιότυπο το`Presentation` κλάση για την αναπαράσταση του αρχείου PowerPoint.
```csharp
string dataDir = "Your Document Directory";
bool isExists = System.IO.Directory.Exists(dataDir);
if (!isExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // Ο κωδικός σας πηγαίνει εδώ
}
```
## Βήμα 3: Λάβετε την πρώτη διαφάνεια
Ανακτήστε την πρώτη διαφάνεια από την παρουσίαση για εργασία.
```csharp
ISlide sld = pres.Slides[0];
```
## Βήμα 4: Δημιουργήστε Instant ImageEx Class
 Δημιουργήστε ένα παράδειγμα του`ImageEx` class για να χειριστείτε την εικόνα που θέλετε να προσθέσετε στη διαφάνεια.
```csharp
System.Drawing.Image img = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx = pres.Images.AddImage(img);
```
## Βήμα 5: Προσθήκη πλαισίου εικόνας
 Χρησιμοποιήστε το`AddPictureFrame` μέθοδος προσθήκης κορνίζας στη διαφάνεια. Καθορίστε τις διαστάσεις και τη θέση του πλαισίου.
```csharp
sld.Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 150, imgx.Width, imgx.Height, imgx);
```
## Βήμα 6: Αποθηκεύστε την Παρουσίαση
Αποθηκεύστε την τροποποιημένη παρουσίαση στο δίσκο.
```csharp
pres.Save(dataDir + "AddStretchOffsetForImageFill_out.pptx", SaveFormat.Pptx);
```
Αυτό είναι! Προσθέσατε με επιτυχία μια μετατόπιση τεντώματος για διαφάνειες συμπλήρωσης εικόνων χρησιμοποιώντας το Aspose.Slides για .NET.
## συμπέρασμα
Η βελτίωση των παρουσιάσεων του PowerPoint είναι πλέον ευκολότερη από ποτέ με το Aspose.Slides για .NET. Ακολουθώντας αυτό το σεμινάριο, μάθατε πώς να ενσωματώνετε το stretch offset για γέμισμα εικόνας, φέρνοντας ένα νέο επίπεδο δημιουργικότητας στις διαφάνειές σας.
## Συχνές ερωτήσεις
### Μπορώ να χρησιμοποιήσω το Aspose.Slides για .NET στις web εφαρμογές μου;
Ναι, το Aspose.Slides για .NET είναι κατάλληλο τόσο για επιτραπέζιους υπολογιστές όσο και για εφαρμογές web.
### Υπάρχει διαθέσιμη δωρεάν δοκιμή για το Aspose.Slides για .NET;
 Ναι, μπορείτε να κάνετε λήψη μιας δωρεάν δοκιμής από[εδώ](https://releases.aspose.com/).
### Πώς μπορώ να λάβω υποστήριξη για το Aspose.Slides για .NET;
 Επισκέψου το[Φόρουμ Aspose.Slides](https://forum.aspose.com/c/slides/11) για κοινοτική υποστήριξη.
### Πού μπορώ να βρω την πλήρη τεκμηρίωση για το Aspose.Slides για .NET;
 Αναφέρομαι στο[τεκμηρίωση](https://reference.aspose.com/slides/net/) για αναλυτικές πληροφορίες.
### Μπορώ να αγοράσω Aspose.Slides για .NET;
 Ναι, μπορείτε να αγοράσετε το προϊόν[εδώ](https://purchase.aspose.com/buy).