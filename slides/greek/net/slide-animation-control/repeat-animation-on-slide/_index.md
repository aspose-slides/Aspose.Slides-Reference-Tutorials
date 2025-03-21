---
title: Κατακτήστε τα κινούμενα σχέδια του PowerPoint με το Aspose.Slides .NET
linktitle: Επαναλάβετε την κινούμενη εικόνα στη διαφάνεια
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Βελτιώστε τις παρουσιάσεις PowerPoint χρησιμοποιώντας το Aspose.Slides για .NET. Ελέγξτε τα κινούμενα σχέδια χωρίς κόπο, μαγέψτε το κοινό σας και αφήστε μια μόνιμη εντύπωση.
weight: 12
url: /el/net/slide-animation-control/repeat-animation-on-slide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Κατακτήστε τα κινούμενα σχέδια του PowerPoint με το Aspose.Slides .NET

## Εισαγωγή
Στον δυναμικό κόσμο των παρουσιάσεων, η ικανότητα ελέγχου των κινούμενων εικόνων παίζει καθοριστικό ρόλο στην προσέλκυση και την αιχμαλωσία της προσοχής του κοινού. Το Aspose.Slides for .NET δίνει τη δυνατότητα στους προγραμματιστές να αναλάβουν τους τύπους κινούμενων εικόνων εντός των διαφανειών, επιτρέποντας μια πιο διαδραστική και οπτικά ελκυστική παρουσίαση. Σε αυτό το σεμινάριο, θα εξερευνήσουμε τον τρόπο ελέγχου των τύπων κινούμενων εικόνων σε μια διαφάνεια χρησιμοποιώντας το Aspose.Slides για .NET, βήμα προς βήμα.
## Προαπαιτούμενα
Πριν ξεκινήσουμε το σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
1.  Aspose.Slides for .NET Library: Κάντε λήψη και εγκατάσταση της βιβλιοθήκης από[εδώ](https://releases.aspose.com/slides/net/).
2. .NET Development Environment: Ρυθμίστε ένα περιβάλλον ανάπτυξης .NET στον υπολογιστή σας.
## Εισαγωγή χώρων ονομάτων
Στο έργο σας .NET, ξεκινήστε εισάγοντας τους απαραίτητους χώρους ονομάτων για να αξιοποιήσετε τις λειτουργίες που παρέχονται από το Aspose.Slides:
```csharp
using Aspose.Slides.Animation;
using Aspose.Slides.SlideShow;
using Aspose.Slides.Export;
```
## Βήμα 1: Ρύθμιση του έργου
Δημιουργήστε έναν νέο κατάλογο για το έργο σας και δημιουργήστε την κλάση Presentation για να αντιπροσωπεύσει το αρχείο παρουσίασης.
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation(dataDir + "AnimationOnSlide.pptx"))
{
    // Ο κωδικός σας πηγαίνει εδώ
}
```
## Βήμα 2: Πρόσβαση στην Ακολουθία Εφέ
Ανακτήστε την ακολουθία εφέ για την πρώτη διαφάνεια χρησιμοποιώντας την ιδιότητα MainSequence.
```csharp
ISequence effectsSequence = pres.Slides[0].Timeline.MainSequence;
```
## Βήμα 3: Πρόσβαση στο πρώτο εφέ
Αποκτήστε το πρώτο εφέ της κύριας ακολουθίας για να χειριστείτε τις ιδιότητές της.
```csharp
IEffect effect = effectsSequence[0];
```
## Βήμα 4: Τροποποίηση των ρυθμίσεων επανάληψης
Αλλάξτε την ιδιότητα Χρονισμός/Επανάληψη του εφέ σε "Μέχρι το τέλος της διαφάνειας".
```csharp
effect.Timing.RepeatUntilEndSlide = true;
```
## Βήμα 5: Αποθηκεύστε την Παρουσίαση
Αποθηκεύστε την τροποποιημένη παρουσίαση για να οπτικοποιήσετε τις αλλαγές.
```csharp
pres.Save(RunExamples.OutPath + "AnimationOnSlide-out.pptx", Aspose.Slides.Export.SaveFormat.Pptx);
```
Επαναλάβετε αυτά τα βήματα για πρόσθετα εφέ ή προσαρμόστε τα σύμφωνα με τις απαιτήσεις παρουσίασής σας.
## συμπέρασμα
Η ενσωμάτωση δυναμικών κινούμενων εικόνων στις παρουσιάσεις σας στο PowerPoint δεν ήταν ποτέ ευκολότερη με το Aspose.Slides για .NET. Αυτός ο οδηγός βήμα προς βήμα σάς εξοπλίζει με τη γνώση για τον έλεγχο των τύπων κινούμενων εικόνων, διασφαλίζοντας ότι οι διαφάνειές σας αφήνουν μια μόνιμη εντύπωση στο κοινό σας.
## Συχνές Ερωτήσεις
### Μπορώ να εφαρμόσω αυτά τα κινούμενα σχέδια σε συγκεκριμένα αντικείμενα μέσα σε μια διαφάνεια;
Ναι, μπορείτε να στοχεύσετε συγκεκριμένα αντικείμενα αποκτώντας πρόσβαση στα επιμέρους εφέ τους εντός της ακολουθίας.
### Είναι το Aspose.Slides συμβατό με τις πιο πρόσφατες εκδόσεις του PowerPoint;
Το Aspose.Slides παρέχει υποστήριξη για ένα ευρύ φάσμα εκδόσεων PowerPoint, διασφαλίζοντας συμβατότητα τόσο με τις παλιές όσο και με τις νέες εκδόσεις.
### Πού μπορώ να βρω επιπλέον παραδείγματα και πόρους;
 Εξερευνήστε το[τεκμηρίωση](https://reference.aspose.com/slides/net/) για ολοκληρωμένα παραδείγματα και λεπτομερείς εξηγήσεις.
### Πώς μπορώ να αποκτήσω μια προσωρινή άδεια για το Aspose.Slides;
 Επίσκεψη[εδώ](https://purchase.aspose.com/temporary-license/) για πληροφορίες σχετικά με την απόκτηση προσωρινής άδειας.
### Χρειάζεστε βοήθεια ή έχετε περισσότερες ερωτήσεις;
 Αλληλεπιδράστε με την κοινότητα Aspose.Slides στο[φόρουμ υποστήριξης](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
