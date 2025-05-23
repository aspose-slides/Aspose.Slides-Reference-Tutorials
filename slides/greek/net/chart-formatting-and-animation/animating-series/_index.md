---
"description": "Μάθετε πώς να δημιουργείτε κίνηση σε σειρές γραφημάτων με το Aspose.Slides για .NET. Προσελκύστε το κοινό σας με δυναμικές παρουσιάσεις. Ξεκινήστε τώρα!"
"linktitle": "Σειρά κινουμένων σχεδίων σε διάγραμμα"
"second_title": "API επεξεργασίας PowerPoint Aspose.Slides .NET"
"title": "Κίνηση σε σειρά γραφημάτων με το Aspose.Slides για .NET"
"url": "/el/net/chart-formatting-and-animation/animating-series/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Κίνηση σε σειρά γραφημάτων με το Aspose.Slides για .NET


Θέλετε να προσθέσετε λίγη πινελιά στις παρουσιάσεις σας με κινούμενα γραφήματα; Το Aspose.Slides για .NET είναι εδώ για να ζωντανέψει τα γραφήματά σας. Σε αυτόν τον οδηγό βήμα προς βήμα, θα σας δείξουμε πώς να δημιουργήσετε κίνηση σε σειρές σε ένα γράφημα χρησιμοποιώντας το Aspose.Slides για .NET. Αλλά πριν βυθιστούμε στη δράση, ας καλύψουμε τις προϋποθέσεις.

## Προαπαιτούμενα

Για να δημιουργήσετε με επιτυχία μια σειρά κινήσεων σε ένα γράφημα χρησιμοποιώντας το Aspose.Slides για .NET, θα χρειαστείτε τα εξής:

### 1. Aspose.Slides για τη βιβλιοθήκη .NET

Βεβαιωθείτε ότι έχετε εγκαταστήσει τη βιβλιοθήκη Aspose.Slides για .NET. Εάν δεν το έχετε κάνει ήδη, μπορείτε να την κατεβάσετε από το [Aspose.Slides για ιστότοπο .NET](https://releases.aspose.com/slides/net/).

### 2. Υπάρχουσα παρουσίαση με διάγραμμα

Προετοιμάστε μια παρουσίαση PowerPoint (PPTX) με ένα υπάρχον γράφημα στο οποίο θέλετε να προσθέσετε κίνηση.

Τώρα που έχουμε καλύψει τις προϋποθέσεις, ας αναλύσουμε τη διαδικασία σε μια σειρά βημάτων για να δώσουμε κίνηση στη σειρά γραφημάτων.


## Βήμα 1: Εισαγωγή απαραίτητων χώρων ονομάτων

Θα χρειαστεί να εισαγάγετε τους απαιτούμενους χώρους ονομάτων στον κώδικα C# σας για να εργαστείτε με το Aspose.Slides για .NET:

```csharp
﻿using Aspose.Slides.Charts;
using Aspose.Slides.Export;
using Aspose.Slides.Animation;
using Aspose.Slides;
```

## Βήμα 2: Φόρτωση της υπάρχουσας παρουσίασης

Σε αυτό το βήμα, φορτώστε την υπάρχουσα παρουσίαση PowerPoint (PPTX) που περιέχει το γράφημα στο οποίο θέλετε να προσθέσετε κίνηση.

```csharp
// Διαδρομή προς τον κατάλογο εγγράφων
string dataDir = "Your Document Directory";

// Δημιουργία κλάσης παρουσίασης που αναπαριστά ένα αρχείο παρουσίασης 
using (Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx"))
{
    // Ο κωδικός σας πηγαίνει εδώ
}
```

## Βήμα 3: Λήψη αναφοράς του αντικειμένου γραφήματος

Για να εργαστείτε με το γράφημα στην παρουσίασή σας, θα χρειαστεί να λάβετε μια αναφορά στο αντικείμενο γραφήματος:

```csharp
var slide = presentation.Slides[0] as Slide;
var shapes = slide.Shapes as ShapeCollection;
var chart = shapes[0] as IChart;
```

## Βήμα 4: Δώστε κίνηση στη σειρά

Τώρα, ήρθε η ώρα να προσθέσετε εφέ κίνησης στη σειρά γραφημάτων σας. Θα προσθέσουμε ένα εφέ fade-in σε ολόκληρο το γράφημα και θα κάνουμε κάθε σειρά να εμφανίζεται μία προς μία.

```csharp
// Κίνηση στο γράφημα
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

// Προσθήκη κινούμενης εικόνας σε κάθε σειρά
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

## Βήμα 5: Αποθήκευση της τροποποιημένης παρουσίασης

Μόλις προσθέσετε τα εφέ κίνησης στο γράφημά σας, αποθηκεύστε την τροποποιημένη παρουσίαση στο δίσκο.

```csharp
// Αποθήκευση της τροποποιημένης παρουσίασης
presentation.Save(dataDir + "AnimatingSeries_out.pptx", SaveFormat.Pptx);
```

Αυτό ήταν! Δημιουργήσατε με επιτυχία μια σειρά κινουμένων σχεδίων σε ένα γράφημα χρησιμοποιώντας το Aspose.Slides για .NET.

## Σύναψη

Σε αυτό το σεμινάριο, σας καθοδηγήσαμε στη διαδικασία δημιουργίας κίνησης σε σειρές σε ένα γράφημα χρησιμοποιώντας το Aspose.Slides για .NET. Με αυτήν την ισχυρή βιβλιοθήκη, μπορείτε να δημιουργήσετε ελκυστικές και δυναμικές παρουσιάσεις που θα αιχμαλωτίσουν το κοινό σας.

Εάν έχετε οποιεσδήποτε ερωτήσεις ή χρειάζεστε περαιτέρω βοήθεια, μη διστάσετε να επικοινωνήσετε με την κοινότητα Aspose.Slides στη διεύθυνση [φόρουμ υποστήριξης](https://forum.aspose.com/).

## Συχνές ερωτήσεις

### Μπορώ να προσθέσω κίνηση σε άλλα στοιχεία γραφήματος εκτός από σειρές χρησιμοποιώντας το Aspose.Slides για .NET;
Ναι, μπορείτε να δημιουργήσετε κίνηση σε διάφορα στοιχεία γραφήματος, συμπεριλαμβανομένων σημείων δεδομένων, αξόνων και υπομνημάτων, χρησιμοποιώντας το Aspose.Slides για .NET.

### Είναι το Aspose.Slides για .NET συμβατό με τις πιο πρόσφατες εκδόσεις του PowerPoint;
Το Aspose.Slides για .NET υποστηρίζει διάφορες εκδόσεις του PowerPoint, συμπεριλαμβανομένου του PowerPoint 2007 και νεότερων, εξασφαλίζοντας συμβατότητα με τις πιο πρόσφατες εκδόσεις.

### Μπορώ να προσαρμόσω τα εφέ κίνησης για κάθε σειρά γραφημάτων ξεχωριστά;
Ναι, μπορείτε να προσαρμόσετε τα εφέ κίνησης για κάθε σειρά γραφημάτων για να δημιουργήσετε μοναδικές και ελκυστικές παρουσιάσεις.

### Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το Aspose.Slides για .NET;
Ναι, μπορείτε να δοκιμάσετε τη βιβλιοθήκη με δωρεάν δοκιμαστική περίοδο από το [Aspose.Slides για ιστότοπο .NET](https://releases.aspose.com/).

### Πού μπορώ να αγοράσω μια άδεια χρήσης για το Aspose.Slides για .NET;
Μπορείτε να αποκτήσετε μια άδεια χρήσης για το Aspose.Slides για .NET από τη σελίδα αγοράς [εδώ](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}