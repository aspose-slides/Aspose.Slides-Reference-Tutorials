---
"description": "Εξερευνήστε τη δύναμη του Aspose.Slides για .NET, συνδέοντας σχήματα εύκολα στις παρουσιάσεις σας. Αναβαθμίστε τις διαφάνειές σας με δυναμικούς συνδέσμους."
"linktitle": "Σύνδεση σχημάτων χρησιμοποιώντας συνδέσμους σε παρουσίαση"
"second_title": "API επεξεργασίας PowerPoint Aspose.Slides .NET"
"title": "Aspose.Slides - Συνδέστε σχήματα απρόσκοπτα στο .NET"
"url": "/el/net/shape-effects-and-manipulation-in-slides/connecting-shapes-using-connectors/"
"weight": 29
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides - Συνδέστε σχήματα απρόσκοπτα στο .NET

## Εισαγωγή
Στον δυναμικό κόσμο των παρουσιάσεων, η δυνατότητα σύνδεσης σχημάτων χρησιμοποιώντας συνδέσμους προσθέτει ένα επίπεδο πολυπλοκότητας στις διαφάνειές σας. Το Aspose.Slides για .NET δίνει τη δυνατότητα στους προγραμματιστές να το επιτύχουν αυτό απρόσκοπτα. Αυτό το σεμινάριο θα σας καθοδηγήσει στη διαδικασία, αναλύοντας κάθε βήμα για να διασφαλίσετε μια σαφή κατανόηση.
## Προαπαιτούμενα
Πριν ξεκινήσουμε το σεμινάριο, βεβαιωθείτε ότι έχετε τα εξής:
- Βασική γνώση C# και .NET framework.
- Το Aspose.Slides για .NET είναι εγκατεστημένο. Εάν όχι, κατεβάστε το. [εδώ](https://releases.aspose.com/slides/net/).
- Ένα περιβάλλον ανάπτυξης έχει δημιουργηθεί.
## Εισαγωγή χώρων ονομάτων
Στον κώδικα C#, ξεκινήστε εισάγοντας τους απαραίτητους χώρους ονομάτων:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
                input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## 1. Ρύθμιση του καταλόγου εγγράφων
Ξεκινήστε ορίζοντας τον κατάλογο για το έγγραφό σας:
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## 2. Δημιουργία αρχικών παρουσιάσεων
Δημιουργήστε μια παρουσία της κλάσης Presentation για να αναπαραστήσετε το αρχείο PPTX σας:
```csharp
using (Presentation input = new Presentation())
{
    // Πρόσβαση στη συλλογή σχημάτων για την επιλεγμένη διαφάνεια
    IShapeCollection shapes = input.Slides[0].Shapes;
```
## 3. Προσθήκη σχημάτων στη διαφάνεια
Προσθέστε τα απαραίτητα σχήματα στη διαφάνειά σας, όπως έλλειψη και ορθογώνιο:
```csharp
IAutoShape ellipse = shapes.AddAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.AddAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## 4. Προσθήκη σχήματος σύνδεσης
Συμπεριλάβετε ένα σχήμα γραμμής σύνδεσης στη συλλογή σχημάτων της διαφάνειας:
```csharp
IConnector connector = shapes.AddConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## 5. Συνδέστε σχήματα με σύνδεσμο
Καθορίστε τα σχήματα που θα συνδεθούν με τη γραμμή σύνδεσης:
```csharp
connector.StartShapeConnectedTo = ellipse;
connector.EndShapeConnectedTo = rectangle;
```
## 6. Αναδρομολόγηση σύνδεσης
Καλέστε τη μέθοδο αναδρομολόγησης για να ορίσετε την αυτόματη συντομότερη διαδρομή μεταξύ σχημάτων:
```csharp
connector.Reroute();
```
## 7. Αποθήκευση παρουσίασης
Αποθηκεύστε την παρουσίασή σας για να δείτε τα συνδεδεμένα σχήματα:
```csharp
input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## Σύναψη
Συγχαρητήρια! Συνδέσατε με επιτυχία σχήματα χρησιμοποιώντας συνδέσμους σε διαφάνειες παρουσίασης χρησιμοποιώντας το Aspose.Slides για .NET. Βελτιώστε τις παρουσιάσεις σας με αυτήν την προηγμένη λειτουργία και αιχμαλωτίστε το κοινό σας.
## Συχνές ερωτήσεις
### Είναι το Aspose.Slides για .NET συμβατό με το πιο πρόσφατο .NET framework;
Ναι, το Aspose.Slides για .NET ενημερώνεται τακτικά για να διασφαλιστεί η συμβατότητα με τις πιο πρόσφατες εκδόσεις του .NET framework.
### Μπορώ να συνδέσω περισσότερα από δύο σχήματα χρησιμοποιώντας μία μόνο σύνδεση;
Απολύτως, μπορείτε να συνδέσετε πολλά σχήματα επεκτείνοντας τη λογική σύνδεσης στον κώδικά σας.
### Υπάρχουν περιορισμοί στα σχήματα που μπορώ να συνδέσω;
Το Aspose.Slides για .NET υποστηρίζει τη σύνδεση διαφόρων σχημάτων, συμπεριλαμβανομένων βασικών σχημάτων, έξυπνων σχεδίων και προσαρμοσμένων σχημάτων.
### Πώς μπορώ να προσαρμόσω την εμφάνιση της εφαρμογής σύνδεσης;
Εξερευνήστε την τεκμηρίωση του Aspose.Slides για μεθόδους προσαρμογής της εμφάνισης της γραμμής σύνδεσης, όπως το στυλ και το χρώμα της γραμμής.
### Υπάρχει κάποιο φόρουμ κοινότητας για την υποστήριξη του Aspose.Slides;
Ναι, μπορείτε να βρείτε βοήθεια και να μοιραστείτε τις εμπειρίες σας στο [Φόρουμ Aspose.Slides](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}