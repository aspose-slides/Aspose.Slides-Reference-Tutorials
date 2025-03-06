---
title: Aspose.Slides - Δημιουργία σχημάτων ομάδας στο .NET
linktitle: Δημιουργία σχημάτων ομάδας σε διαφάνειες παρουσίασης με το Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Μάθετε πώς να δημιουργείτε σχήματα ομάδων στο PowerPoint με το Aspose.Slides για .NET. Ακολουθήστε τον βήμα προς βήμα οδηγό μας για οπτικά ελκυστικές παρουσιάσεις.
weight: 11
url: /el/net/image-and-video-manipulation-in-slides/creating-group-shapes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides - Δημιουργία σχημάτων ομάδας στο .NET

## Εισαγωγή
Εάν θέλετε να βελτιώσετε την οπτική ελκυστικότητα των διαφανειών της παρουσίασής σας και να οργανώσετε το περιεχόμενο πιο αποτελεσματικά, η ενσωμάτωση σχημάτων ομάδων είναι μια ισχυρή λύση. Το Aspose.Slides for .NET παρέχει έναν απρόσκοπτο τρόπο δημιουργίας και χειρισμού σχημάτων ομάδων στις παρουσιάσεις σας στο PowerPoint. Σε αυτό το σεμινάριο, θα ακολουθήσουμε τη διαδικασία δημιουργίας σχημάτων ομάδας χρησιμοποιώντας το Aspose.Slides, αναλύοντάς το σε βήματα που μπορείτε να ακολουθήσετε εύκολα.
## Προαπαιτούμενα
Πριν βουτήξουμε στο σεμινάριο, βεβαιωθείτε ότι έχετε τα εξής:
-  Aspose.Slides για .NET: Βεβαιωθείτε ότι έχετε εγκαταστήσει τη βιβλιοθήκη Aspose.Slides. Μπορείτε να το κατεβάσετε από το[δικτυακός τόπος](https://releases.aspose.com/slides/net/).
- Περιβάλλον ανάπτυξης: Ρυθμίστε ένα περιβάλλον εργασίας με ένα IDE συμβατό με .NET, όπως το Visual Studio.
- Βασικές γνώσεις C#: Εξοικειωθείτε με τα βασικά της γλώσσας προγραμματισμού C#.
## Εισαγωγή χώρων ονομάτων
Στο έργο σας C#, ξεκινήστε εισάγοντας τους απαραίτητους χώρους ονομάτων:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Βήμα 1: Τάξη Instantiate Presentation

 Δημιουργήστε ένα παράδειγμα του`Presentation` τάξη και καθορίστε τον κατάλογο όπου αποθηκεύονται τα έγγραφά σας:

```csharp
string dataDir = "Your Documents Directory";
using (Presentation pres = new Presentation())
{
    // Συνεχίστε με τα ακόλουθα βήματα σε αυτό χρησιμοποιώντας το μπλοκ
}
```

## Βήμα 2: Πρόσβαση στην Πρώτη Διαφάνεια

Ανακτήστε την πρώτη διαφάνεια από την παρουσίαση:

```csharp
ISlide sld = pres.Slides[0];
```

## Βήμα 3: Πρόσβαση στη Συλλογή Σχημάτων

Πρόσβαση στη συλλογή σχημάτων στη διαφάνεια:

```csharp
IShapeCollection slideShapes = sld.Shapes;
```

## Βήμα 4: Προσθήκη σχήματος ομάδας

Προσθέστε ένα σχήμα ομάδας στη διαφάνεια:

```csharp
IGroupShape groupShape = slideShapes.AddGroupShape();
```

## Βήμα 5: Προσθήκη σχημάτων μέσα στο σχήμα ομάδας

Συμπληρώστε το σχήμα της ομάδας με μεμονωμένα σχήματα:

```csharp
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 300, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 300, 100, 100);
```

## Βήμα 6: Προσθήκη πλαισίου σχήματος ομάδας

Ορίστε το πλαίσιο για ολόκληρο το σχήμα της ομάδας:

```csharp
groupShape.Frame = new ShapeFrame(100, 300, 500, 40, NullableBool.False, NullableBool.False, 0);
```

## Βήμα 7: Αποθηκεύστε την Παρουσίαση

Αποθηκεύστε την τροποποιημένη παρουσίαση στον καθορισμένο κατάλογο:

```csharp
pres.Save(dataDir + "GroupShape_out.pptx", SaveFormat.Pptx);
```

Επαναλάβετε αυτά τα βήματα στην εφαρμογή C# για να δημιουργήσετε με επιτυχία σχήματα ομάδων στις διαφάνειες παρουσίασής σας χρησιμοποιώντας το Aspose.Slides.

## συμπέρασμα
Σε αυτό το σεμινάριο, εξερευνήσαμε τη διαδικασία δημιουργίας σχημάτων ομάδας με το Aspose.Slides για .NET. Ακολουθώντας αυτά τα βήματα, μπορείτε να βελτιώσετε την οπτική ελκυστικότητα και την οργάνωση των παρουσιάσεών σας στο PowerPoint.
## Συχνές Ερωτήσεις
### Είναι το Aspose.Slides συμβατό με την πιο πρόσφατη έκδοση του .NET;
 Ναι, το Aspose.Slides ενημερώνεται τακτικά για να υποστηρίζει τις πιο πρόσφατες εκδόσεις .NET. Ελεγξε το[τεκμηρίωση](https://reference.aspose.com/slides/net/) για λεπτομέρειες συμβατότητας.
### Μπορώ να δοκιμάσω το Aspose.Slides πριν από την αγορά;
 Απολύτως! Μπορείτε να κατεβάσετε μια δωρεάν δοκιμαστική έκδοση[εδώ](https://releases.aspose.com/).
### Πού μπορώ να βρω υποστήριξη για ερωτήματα που σχετίζονται με το Aspose.Slides;
Επισκεφτείτε το Aspose.Slides[δικαστήριο](https://forum.aspose.com/c/slides/11) για κοινοτική υποστήριξη και συζητήσεις.
### Πώς μπορώ να αποκτήσω μια προσωρινή άδεια για το Aspose.Slides;
 Μπορείτε να πάρετε μια προσωρινή άδεια[εδώ](https://purchase.aspose.com/temporary-license/).
### Πού μπορώ να αγοράσω μια πλήρη άδεια χρήσης για το Aspose.Slides;
 Μπορείτε να αγοράσετε άδεια από το[σελίδα αγοράς](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
