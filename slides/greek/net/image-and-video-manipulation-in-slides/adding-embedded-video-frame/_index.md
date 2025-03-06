---
title: Aspose.Slides - Προσθήκη ενσωματωμένων βίντεο σε παρουσιάσεις .NET
linktitle: Aspose.Slides - Προσθήκη ενσωματωμένων βίντεο σε παρουσιάσεις .NET
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Βελτιώστε τις παρουσιάσεις σας με ενσωματωμένα βίντεο χρησιμοποιώντας το Aspose.Slides για .NET. Ακολουθήστε τον βήμα προς βήμα οδηγό μας για απρόσκοπτη ενσωμάτωση.
weight: 19
url: /el/net/image-and-video-manipulation-in-slides/adding-embedded-video-frame/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Εισαγωγή
Στον δυναμικό κόσμο των παρουσιάσεων, η ενσωμάτωση στοιχείων πολυμέσων μπορεί να βελτιώσει σημαντικά την αφοσίωση. Το Aspose.Slides for .NET παρέχει μια ισχυρή λύση για την ενσωμάτωση ενσωματωμένων πλαισίων βίντεο στις διαφάνειες της παρουσίασής σας. Αυτό το σεμινάριο θα σας καθοδηγήσει στη διαδικασία, αναλύοντας κάθε βήμα για να εξασφαλίσετε μια απρόσκοπτη εμπειρία.
## Προαπαιτούμενα
Πριν βουτήξουμε στο σεμινάριο, βεβαιωθείτε ότι έχετε τα εξής:
-  Aspose.Slides for .NET Library: Κάντε λήψη και εγκατάσταση της βιβλιοθήκης από το[σελίδα έκδοσης](https://releases.aspose.com/slides/net/).
- Περιεχόμενο πολυμέσων: Έχετε ένα αρχείο βίντεο (π.χ. "Wildlife.mp4") που θέλετε να ενσωματώσετε στην παρουσίασή σας.
## Εισαγωγή χώρων ονομάτων
Ξεκινήστε εισάγοντας τους απαραίτητους χώρους ονομάτων στο έργο σας .NET:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Βήμα 1: Ρύθμιση καταλόγων
Βεβαιωθείτε ότι το έργο σας διαθέτει τους απαιτούμενους καταλόγους για αρχεία εγγράφων και πολυμέσων:
```csharp
string dataDir = "Your Document Directory";
string videoDir = "Your Media Directory";
string resultPath = Path.Combine(dataDir, "VideoFrame_out.pptx");
// Δημιουργήστε κατάλογο εάν δεν υπάρχει ήδη.
bool IsExists = Directory.Exists(dataDir);
if (!IsExists)
    Directory.CreateDirectory(dataDir);
```
## Βήμα 2: Τάξη άμεσης παρουσίασης
Δημιουργήστε ένα στιγμιότυπο της κλάσης Presentation για την αναπαράσταση του αρχείου PPTX:
```csharp
using (Presentation pres = new Presentation())
{
    // Αποκτήστε την πρώτη διαφάνεια
    ISlide sld = pres.Slides[0];
```
## Βήμα 3: Ενσωματώστε το βίντεο μέσα στην παρουσίαση
Χρησιμοποιήστε τον ακόλουθο κώδικα για να ενσωματώσετε ένα βίντεο μέσα στην παρουσίαση:
```csharp
IVideo vid = pres.Videos.AddVideo(new FileStream(videoDir + "Wildlife.mp4", FileMode.Open), LoadingStreamBehavior.ReadStreamAndRelease);
```
## Βήμα 4: Προσθήκη καρέ βίντεο
Τώρα, προσθέστε ένα πλαίσιο βίντεο στη διαφάνεια:
```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 350, vid);
```
## Βήμα 5: Ορίστε τις ιδιότητες βίντεο
Ρυθμίστε το βίντεο στο πλαίσιο βίντεο και διαμορφώστε τη λειτουργία αναπαραγωγής και την ένταση:
```csharp
vf.EmbeddedVideo = vid;
vf.PlayMode = VideoPlayModePreset.Auto;
vf.Volume = AudioVolumeMode.Loud;
```
## Βήμα 6: Αποθηκεύστε την παρουσίαση
Τέλος, αποθηκεύστε το αρχείο PPTX στο δίσκο:
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
Επαναλάβετε αυτά τα βήματα για κάθε βίντεο που θέλετε να ενσωματώσετε στην παρουσίασή σας.
## συμπέρασμα
Συγχαρητήρια! Προσθέσατε με επιτυχία ένα ενσωματωμένο πλαίσιο βίντεο στην παρουσίασή σας χρησιμοποιώντας το Aspose.Slides για .NET. Αυτή η δυναμική λειτουργία μπορεί να ανυψώσει τις παρουσιάσεις σας σε νέα ύψη, μαγεύοντας το κοινό σας με στοιχεία πολυμέσων που ενσωματώνονται απρόσκοπτα στις διαφάνειές σας.
## Συχνές ερωτήσεις
### Μπορώ να ενσωματώσω βίντεο σε οποιαδήποτε διαφάνεια της παρουσίασης;
 Ναι, μπορείτε να επιλέξετε οποιαδήποτε διαφάνεια τροποποιώντας το ευρετήριο`pres.Slides[index]`.
### Ποιες μορφές βίντεο υποστηρίζονται;
Το Aspose.Slides υποστηρίζει μια ποικιλία μορφών βίντεο, συμπεριλαμβανομένων των MP4, AVI και WMV.
### Μπορώ να προσαρμόσω το μέγεθος και τη θέση του καρέ βίντεο;
 Απολύτως! Προσαρμόστε τις παραμέτρους στο`AddVideoFrame(x, y, width, height, video)` όπως απαιτείται.
### Υπάρχει όριο στον αριθμό των βίντεο που μπορώ να ενσωματώσω;
Ο αριθμός των ενσωματωμένων βίντεο περιορίζεται συνήθως από τη χωρητικότητα του λογισμικού παρουσίασής σας.
### Πώς μπορώ να αναζητήσω περαιτέρω βοήθεια ή να μοιραστώ την εμπειρία μου;
 Επισκέψου το[Φόρουμ Aspose.Slides](https://forum.aspose.com/c/slides/11) για κοινοτική υποστήριξη και συζητήσεις.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
