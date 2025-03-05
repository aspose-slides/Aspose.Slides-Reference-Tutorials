---
title: Aspose.Slides - Συνδέστε τα σχήματα απρόσκοπτα στο .NET
linktitle: Σύνδεση σχημάτων με χρήση συνδέσμων στην παρουσίαση
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Εξερευνήστε τη δύναμη του Aspose.Slides για .NET, συνδέοντας σχήματα χωρίς κόπο στις παρουσιάσεις σας. Ανυψώστε τις διαφάνειές σας με δυναμικές υποδοχές.
type: docs
weight: 29
url: /el/net/shape-effects-and-manipulation-in-slides/connecting-shapes-using-connectors/
---
## Εισαγωγή
Στον δυναμικό κόσμο των παρουσιάσεων, η δυνατότητα σύνδεσης σχημάτων χρησιμοποιώντας συνδέσμους προσθέτει ένα επίπεδο πολυπλοκότητας στις διαφάνειές σας. Το Aspose.Slides for .NET δίνει τη δυνατότητα στους προγραμματιστές να το επιτύχουν απρόσκοπτα. Αυτό το σεμινάριο θα σας καθοδηγήσει στη διαδικασία, αναλύοντας κάθε βήμα για να εξασφαλίσετε μια σαφή κατανόηση.
## Προαπαιτούμενα
Πριν βουτήξουμε στο σεμινάριο, βεβαιωθείτε ότι έχετε τα εξής:
- Βασικές γνώσεις C# και .NET Framework.
-  Εγκαταστάθηκαν Aspose.Slides για .NET. Αν όχι, κατεβάστε το[εδώ](https://releases.aspose.com/slides/net/).
- Δημιουργήθηκε ένα αναπτυξιακό περιβάλλον.
## Εισαγωγή χώρων ονομάτων
Στον κώδικα C#, ξεκινήστε εισάγοντας τους απαραίτητους χώρους ονομάτων:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
                input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## 1. Ρυθμίστε τον Κατάλογο εγγράφων
Ξεκινήστε ορίζοντας τον κατάλογο για το έγγραφό σας:
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## 2. Τάξη Instantiate Presentation
Δημιουργήστε μια παρουσία της κλάσης Presentation για να αντιπροσωπεύει το αρχείο PPTX:
```csharp
using (Presentation input = new Presentation())
{
    // Πρόσβαση στη συλλογή σχημάτων για την επιλεγμένη διαφάνεια
    IShapeCollection shapes = input.Slides[0].Shapes;
```
## 3. Προσθέστε σχήματα στη Διαφάνεια
Προσθέστε τα απαραίτητα σχήματα στη διαφάνεια σας, όπως Ellipse και Rectangle:
```csharp
IAutoShape ellipse = shapes.AddAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.AddAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## 4. Προσθέστε σχήμα σύνδεσης
Συμπεριλάβετε ένα σχήμα σύνδεσης στη συλλογή σχημάτων της διαφάνειας:
```csharp
IConnector connector = shapes.AddConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## 5. Συνδέστε τα σχήματα με σύνδεσμο
Καθορίστε τα σχήματα που θα συνδεθούν από τον σύνδεσμο:
```csharp
connector.StartShapeConnectedTo = ellipse;
connector.EndShapeConnectedTo = rectangle;
```
## 6. Επαναδρομολόγηση σύνδεσης
Καλέστε τη μέθοδο αναδρομολόγησης για να ορίσετε την αυτόματη συντομότερη διαδρομή μεταξύ των σχημάτων:
```csharp
connector.Reroute();
```
## 7. Αποθήκευση παρουσίασης
Αποθηκεύστε την παρουσίασή σας για να δείτε τα συνδεδεμένα σχήματα:
```csharp
input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## συμπέρασμα
Συγχαρητήρια! Έχετε συνδέσει με επιτυχία σχήματα χρησιμοποιώντας συνδέσμους σε διαφάνειες παρουσίασης χρησιμοποιώντας το Aspose.Slides για .NET. Βελτιώστε τις παρουσιάσεις σας με αυτήν την προηγμένη λειτουργία και μαγέψτε το κοινό σας.
## Συχνές ερωτήσεις
### Είναι το Aspose.Slides για .NET συμβατό με το πιο πρόσφατο πλαίσιο .NET;
Ναι, το Aspose.Slides για .NET ενημερώνεται τακτικά για να διασφαλίζεται η συμβατότητα με τις πιο πρόσφατες εκδόσεις πλαισίου .NET.
### Μπορώ να συνδέσω περισσότερα από δύο σχήματα χρησιμοποιώντας έναν μόνο σύνδεσμο;
Οπωσδήποτε, μπορείτε να συνδέσετε πολλά σχήματα επεκτείνοντας τη λογική σύνδεσης στον κώδικά σας.
### Υπάρχουν περιορισμοί στα σχήματα που μπορώ να συνδέσω;
Το Aspose.Slides for .NET υποστηρίζει τη σύνδεση διαφόρων σχημάτων, συμπεριλαμβανομένων των βασικών σχημάτων, της έξυπνης τέχνης και των προσαρμοσμένων σχημάτων.
### Πώς μπορώ να προσαρμόσω την εμφάνιση του βύσματος;
Εξερευνήστε την τεκμηρίωση Aspose.Slides για μεθόδους προσαρμογής της εμφάνισης της εφαρμογής σύνδεσης, όπως το στυλ γραμμής και το χρώμα.
### Υπάρχει κάποιο φόρουμ κοινότητας για υποστήριξη Aspose.Slides;
 Ναι, μπορείτε να βρείτε βοήθεια και να μοιραστείτε τις εμπειρίες σας στο[Φόρουμ Aspose.Slides](https://forum.aspose.com/c/slides/11).