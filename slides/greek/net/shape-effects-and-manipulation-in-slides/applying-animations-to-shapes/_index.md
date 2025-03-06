---
title: Τα κινούμενα σχέδια σχήματος γίνονται εύκολα με το Aspose.Slides
linktitle: Εφαρμογή κινούμενων εικόνων σε σχήματα σε διαφάνειες παρουσίασης με το Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Δημιουργήστε εκπληκτικές παρουσιάσεις με το Aspose.Slides για .NET. Μάθετε πώς να εφαρμόζετε κινούμενα σχέδια σε σχήματα σε αυτόν τον οδηγό βήμα προς βήμα. Ανυψώστε τις διαφάνειές σας τώρα!
type: docs
weight: 21
url: /el/net/shape-effects-and-manipulation-in-slides/applying-animations-to-shapes/
---
## Εισαγωγή
Στον κόσμο των δυναμικών παρουσιάσεων, η προσθήκη κινούμενων εικόνων σε σχήματα μπορεί να βελτιώσει σημαντικά την οπτική ελκυστικότητα και την αφοσίωση των διαφανειών σας. Το Aspose.Slides for .NET παρέχει μια ισχυρή εργαλειοθήκη για να το πετύχετε αυτό απρόσκοπτα. Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία εφαρμογής κινούμενων εικόνων σε σχήματα χρησιμοποιώντας το Aspose.Slides, επιτρέποντάς σας να δημιουργήσετε συναρπαστικές παρουσιάσεις που αφήνουν μια μόνιμη εντύπωση.
## Προαπαιτούμενα
Πριν ξεκινήσουμε τον οδηγό, βεβαιωθείτε ότι έχετε τα εξής:
1.  Aspose.Slides για .NET: Βεβαιωθείτε ότι έχετε εγκαταστήσει τη βιβλιοθήκη και είναι έτοιμη για χρήση. Μπορείτε να το κατεβάσετε[εδώ](https://releases.aspose.com/slides/net/).
2. Περιβάλλον ανάπτυξης: Ρυθμίστε το περιβάλλον ανάπτυξης που προτιμάτε με τις απαραίτητες διαμορφώσεις.
3. Κατάλογος εγγράφων: Δημιουργήστε έναν κατάλογο για να αποθηκεύσετε τα αρχεία παρουσίασής σας.
## Εισαγωγή χώρων ονομάτων
Στην εφαρμογή σας .NET, ξεκινήστε εισάγοντας τους απαιτούμενους χώρους ονομάτων:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
using Aspose.Slides.Animation;
using System.Drawing;
```
## Βήμα 1: Δημιουργήστε μια παρουσίαση
 Ξεκινήστε δημιουργώντας μια νέα παρουσίαση χρησιμοποιώντας το`Presentation` τάξη:
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // Ο κωδικός σας για τη δημιουργία μιας παρουσίασης βρίσκεται εδώ.
}
```
## Βήμα 2: Προσθέστε κινούμενο σχήμα
Τώρα, ας προσθέσουμε ένα κινούμενο σχήμα στην πρώτη διαφάνεια της παρουσίασής σας:
```csharp
ISlide sld = pres.Slides[0];
IAutoShape ashp = sld.Shapes.AddAutoShape(ShapeType.Rectangle, 150, 150, 250, 25);
ashp.AddTextFrame("Animated TextBox");
```
## Βήμα 3: Εφαρμογή εφέ κινούμενης εικόνας
Προσθέστε το εφέ κινούμενης εικόνας «PathFootball» στο δημιουργημένο σχήμα:
```csharp
pres.Slides[0].Timeline.MainSequence.AddEffect(ashp, EffectType.PathFootball, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```
## Βήμα 4: Δημιουργία κουμπιού ενεργοποίησης
Δημιουργήστε ένα κουμπί που θα ενεργοποιήσει την κινούμενη εικόνα:
```csharp
IShape shapeTrigger = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Bevel, 10, 10, 20, 20);
```
## Βήμα 5: Ορισμός προσαρμοσμένης διαδρομής χρήστη
Καθορίστε μια προσαρμοσμένη διαδρομή χρήστη για την κινούμενη εικόνα:
```csharp
ISequence seqInter = pres.Slides[0].Timeline.InteractiveSequences.Add(shapeTrigger);
IEffect fxUserPath = seqInter.AddEffect(ashp, EffectType.PathUser, EffectSubtype.None, EffectTriggerType.OnClick);
IMotionEffect motionBhv = ((IMotionEffect)fxUserPath.Behaviors[0]);
PointF[] pts = new PointF[1];
pts[0] = new PointF(0.076f, 0.59f);
motionBhv.Path.Add(MotionCommandPathType.LineTo, pts, MotionPathPointsType.Auto, true);
pts[0] = new PointF(-0.076f, -0.59f);
motionBhv.Path.Add(MotionCommandPathType.LineTo, pts, MotionPathPointsType.Auto, false);
motionBhv.Path.Add(MotionCommandPathType.End, null, MotionPathPointsType.Auto, false);
// Αποθηκεύστε την παρουσίαση ως PPTX στο δίσκο
pres.Save(dataDir + "AnimExample_out.pptx", SaveFormat.Pptx);
```
Αυτό ολοκληρώνει τον οδηγό βήμα προς βήμα για την εφαρμογή κινούμενων εικόνων σε σχήματα χρησιμοποιώντας το Aspose.Slides για .NET.
## συμπέρασμα
Η ενσωμάτωση κινούμενων εικόνων στις παρουσιάσεις σας προσθέτει ένα δυναμικό στοιχείο που προσελκύει την προσοχή του κοινού σας. Με το Aspose.Slides, έχετε ένα ισχυρό εργαλείο για να ενσωματώνετε απρόσκοπτα αυτά τα εφέ και να ανεβάζετε τις παρουσιάσεις σας στο επόμενο επίπεδο.
## Συχνές Ερωτήσεις
### Μπορώ να εφαρμόσω πολλαπλές κινούμενες εικόνες σε ένα μόνο σχήμα;
Ναι, το Aspose.Slides σάς επιτρέπει να προσθέτετε πολλαπλά εφέ κίνησης σε ένα μόνο σχήμα, παρέχοντας ευελιξία στη δημιουργία πολύπλοκων κινούμενων εικόνων.
### Είναι το Aspose.Slides συμβατό με διαφορετικές εκδόσεις του PowerPoint;
Το Aspose.Slides εξασφαλίζει συμβατότητα με διάφορες εκδόσεις του PowerPoint, διασφαλίζοντας ότι οι παρουσιάσεις σας λειτουργούν απρόσκοπτα σε διαφορετικές πλατφόρμες.
### Πού μπορώ να βρω πρόσθετους πόρους και υποστήριξη για το Aspose.Slides;
 Εξερευνήστε το[τεκμηρίωση](https://reference.aspose.com/slides/net/) και ζητήστε βοήθεια στο[Φόρουμ Aspose.Slides](https://forum.aspose.com/c/slides/11).
### Χρειάζομαι άδεια χρήσης για το Aspose.Slides για να χρησιμοποιήσω τη βιβλιοθήκη;
 Ναι, μπορείτε να αποκτήσετε άδεια[εδώ](https://purchase.aspose.com/buy) για να ξεκλειδώσετε πλήρως τις δυνατότητες του Aspose.Slides.
### Μπορώ να δοκιμάσω το Aspose.Slides πριν από την αγορά;
 Σίγουρα! Χρησιμοποιήστε το[δωρεάν δοκιμή](https://releases.aspose.com/) για να γνωρίσετε τις δυνατότητες του Aspose.Slides πριν αναλάβετε δέσμευση.