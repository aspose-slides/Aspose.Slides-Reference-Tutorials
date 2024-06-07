---
title: Αλλαγή δεδομένων αντικειμένου OLE στην παρουσίαση με το Aspose.Slides
linktitle: Αλλαγή δεδομένων αντικειμένου OLE στην παρουσίαση με το Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Εξερευνήστε τη δύναμη του Aspose.Slides για .NET στην αλλαγή των δεδομένων αντικειμένων OLE χωρίς κόπο. Βελτιώστε τις παρουσιάσεις σας με δυναμικό περιεχόμενο.
type: docs
weight: 25
url: /el/net/shape-effects-and-manipulation-in-slides/changing-ole-object-data/
---
## Εισαγωγή
Η δημιουργία δυναμικών και διαδραστικών παρουσιάσεων PowerPoint είναι μια κοινή απαίτηση στον σημερινό ψηφιακό κόσμο. Ένα ισχυρό εργαλείο για να το πετύχετε αυτό είναι το Aspose.Slides for .NET, μια ισχυρή βιβλιοθήκη που επιτρέπει στους προγραμματιστές να χειρίζονται και να βελτιώνουν τις παρουσιάσεις του PowerPoint μέσω προγραμματισμού. Σε αυτό το σεμινάριο, θα εμβαθύνουμε στη διαδικασία αλλαγής των δεδομένων αντικειμένων OLE (Σύνδεση και ενσωμάτωση αντικειμένων) σε διαφάνειες παρουσίασης χρησιμοποιώντας το Aspose.Slides.
## Προαπαιτούμενα
Πριν ξεκινήσετε να εργάζεστε με το Aspose.Slides για .NET, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
1. Περιβάλλον ανάπτυξης: Ρυθμίστε ένα περιβάλλον ανάπτυξης με εγκατεστημένο το .NET.
2.  Aspose.Slides Library: Κάντε λήψη και εγκατάσταση της βιβλιοθήκης Aspose.Slides για .NET. Μπορείτε να βρείτε τη βιβλιοθήκη[εδώ](https://releases.aspose.com/slides/net/).
3. Βασική Κατανόηση: Εξοικειωθείτε με τις βασικές έννοιες του προγραμματισμού C# και των παρουσιάσεων PowerPoint.
## Εισαγωγή χώρων ονομάτων
Στο έργο σας C#, εισαγάγετε τους απαραίτητους χώρους ονομάτων για να χρησιμοποιήσετε τις λειτουργίες Aspose.Slides:
```csharp
using System.IO;
using Aspose.Cells;
using Aspose.Slides;
using Aspose.Slides.DOM.Ole;
using SaveFormat = Aspose.Slides.Export.SaveFormat;
```
## Βήμα 1: Ρύθμιση του έργου σας
Ξεκινήστε δημιουργώντας ένα νέο έργο C# και εισάγοντας τη βιβλιοθήκη Aspose.Slides. Βεβαιωθείτε ότι το έργο σας έχει ρυθμιστεί σωστά και ότι έχετε τις απαιτούμενες εξαρτήσεις.
## Βήμα 2: Πρόσβαση στην παρουσίαση και τη διαφάνεια
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx"))
{
    ISlide slide = pres.Slides[0];
```
## Βήμα 3: Εντοπίστε το αντικείμενο OLE
Διασχίστε όλα τα σχήματα στη διαφάνεια για να βρείτε το πλαίσιο αντικειμένου OLE:
```csharp
OleObjectFrame ole = null;
foreach (IShape shape in slide.Shapes)
{
    if (shape is OleObjectFrame)
    {
        ole = (OleObjectFrame)shape;
    }
}
```
## Βήμα 4: Διαβάστε και τροποποιήστε τα δεδομένα του βιβλίου εργασίας
```csharp
if (ole != null)
{
    using (MemoryStream msln = new MemoryStream(ole.EmbeddedData.EmbeddedFileData))
    {
        // Ανάγνωση δεδομένων αντικειμένου στο βιβλίο εργασίας
        Workbook Wb = new Workbook(msln);
        using (MemoryStream msout = new MemoryStream())
        {
            // Τροποποίηση των δεδομένων του βιβλίου εργασίας
            Wb.Worksheets[0].Cells[0, 4].PutValue("E");
            Wb.Worksheets[0].Cells[1, 4].PutValue(12);
            Wb.Worksheets[0].Cells[2, 4].PutValue(14);
            Wb.Worksheets[0].Cells[3, 4].PutValue(15);
            OoxmlSaveOptions so1 = new OoxmlSaveOptions(Aspose.Cells.SaveFormat.Xlsx);
            Wb.Save(msout, so1);
            // Αλλαγή δεδομένων αντικειμένου πλαισίου Ole
            IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.ToArray(), ole.EmbeddedData.EmbeddedFileExtension);
            ole.SetEmbeddedData(newData);
        }
    }
}
```
## Βήμα 5: Αποθηκεύστε την παρουσίαση
```csharp
pres.Save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
```
## συμπέρασμα
Ακολουθώντας αυτά τα βήματα, μπορείτε να αλλάξετε απρόσκοπτα τα δεδομένα αντικειμένων OLE μέσα στις διαφάνειες παρουσίασης χρησιμοποιώντας το Aspose.Slides για .NET. Αυτό ανοίγει έναν κόσμο δυνατοτήτων για τη δημιουργία δυναμικών και προσαρμοσμένων παρουσιάσεων προσαρμοσμένων στις συγκεκριμένες ανάγκες σας.
## Συχνές Ερωτήσεις
### Τι είναι το Aspose.Slides για .NET;
Το Aspose.Slides for .NET είναι μια ισχυρή βιβλιοθήκη που επιτρέπει στους προγραμματιστές να εργάζονται με παρουσιάσεις PowerPoint μέσω προγραμματισμού, επιτρέποντας εύκολο χειρισμό και βελτίωση.
### Πού μπορώ να βρω την τεκμηρίωση του Aspose.Slides;
 Μπορείτε να βρείτε την τεκμηρίωση για το Aspose.Slides για .NET[εδώ](https://reference.aspose.com/slides/net/).
### Πώς μπορώ να κατεβάσω το Aspose.Slides για .NET;
 Μπορείτε να κατεβάσετε τη βιβλιοθήκη από τη σελίδα έκδοσης[εδώ](https://releases.aspose.com/slides/net/).
### Υπάρχει διαθέσιμη δωρεάν δοκιμή για το Aspose.Slides;
 Ναι, μπορείτε να έχετε πρόσβαση στη δωρεάν δοκιμή[εδώ](https://releases.aspose.com/).
### Πού μπορώ να λάβω υποστήριξη για το Aspose.Slides για .NET;
 Για υποστήριξη και συζητήσεις, επισκεφτείτε το[Φόρουμ Aspose.Slides](https://forum.aspose.com/c/slides/11).