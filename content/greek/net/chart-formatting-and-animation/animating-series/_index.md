---
title: Κινούμενη σειρά γραφημάτων με Aspose.Slides για .NET
linktitle: Σειρά κινουμένων σχεδίων στο γράφημα
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Μάθετε πώς να δημιουργείτε κινούμενες σειρές γραφημάτων με το Aspose.Slides για .NET. Προσελκύστε το κοινό σας με δυναμικές παρουσιάσεις. Ξεκινήστε τώρα!
type: docs
weight: 12
url: /el/net/chart-formatting-and-animation/animating-series/
---

Ψάχνετε να προσθέσετε λίγο pizzazz στις παρουσιάσεις σας με κινούμενα charts; Το Aspose.Slides για .NET είναι εδώ για να ζωντανέψει τα γραφήματα σας. Σε αυτόν τον οδηγό βήμα προς βήμα, θα σας δείξουμε πώς να κάνετε κινούμενες σειρές σε ένα γράφημα χρησιμοποιώντας το Aspose.Slides για .NET. Πριν όμως βουτήξουμε στη δράση, ας καλύψουμε τα προαπαιτούμενα.

## Προαπαιτούμενα

Για να δημιουργήσετε με επιτυχία σειρές σε ένα γράφημα χρησιμοποιώντας το Aspose.Slides για .NET, θα χρειαστείτε τα εξής:

### 1. Aspose.Slides για .NET Library

 Βεβαιωθείτε ότι έχετε εγκαταστήσει τη βιβλιοθήκη Aspose.Slides for .NET. Εάν δεν το έχετε κάνει ήδη, μπορείτε να το κατεβάσετε από το[Aspose.Slides για τον ιστότοπο .NET](https://releases.aspose.com/slides/net/).

### 2. Υπάρχουσα Παρουσίαση με Διάγραμμα

Προετοιμάστε μια παρουσίαση PowerPoint (PPTX) με ένα υπάρχον γράφημα που θέλετε να κάνετε κίνηση.

Τώρα που έχουμε καλύψει τις προϋποθέσεις, ας αναλύσουμε τη διαδικασία σε μια σειρά βημάτων για να δημιουργήσουμε κινούμενα σχέδια στη σειρά τσαρτ.


## Βήμα 1: Εισαγάγετε τους απαραίτητους χώρους ονομάτων

Θα χρειαστεί να εισαγάγετε τους απαιτούμενους χώρους ονομάτων στον κώδικα C# για να εργαστείτε με το Aspose.Slides για .NET:

```csharp
﻿using Aspose.Slides.Charts;
using Aspose.Slides.Export;
using Aspose.Slides.Animation;
using Aspose.Slides;
```

## Βήμα 2: Φορτώστε την υπάρχουσα παρουσίαση

Σε αυτό το βήμα, φορτώστε την υπάρχουσα παρουσίαση του PowerPoint (PPTX) που περιέχει το γράφημα που θέλετε να κάνετε κίνηση.

```csharp
// Διαδρομή στον κατάλογο εγγράφων
string dataDir = "Your Document Directory";

// Κλάση Instantiate Presentation που αντιπροσωπεύει ένα αρχείο παρουσίασης
using (Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx"))
{
    // Ο κωδικός σας πηγαίνει εδώ
}
```

## Βήμα 3: Λήψη αναφοράς για το αντικείμενο του γραφήματος

Για να εργαστείτε με το γράφημα στην παρουσίασή σας, θα χρειαστεί να λάβετε μια αναφορά στο αντικείμενο του γραφήματος:

```csharp
var slide = presentation.Slides[0] as Slide;
var shapes = slide.Shapes as ShapeCollection;
var chart = shapes[0] as IChart;
```

## Βήμα 4: Κινούμενη κίνηση της σειράς

Τώρα, ήρθε η ώρα να προσθέσετε εφέ κινουμένων σχεδίων στη σειρά γραφημάτων σας. Θα προσθέσουμε ένα εφέ fade-in σε ολόκληρο το γράφημα και θα κάνουμε κάθε σειρά να εμφανίζεται μία προς μία.

```csharp
// Ζωντανέψτε το γράφημα
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

// Προσθέστε κινούμενα σχέδια σε κάθε σειρά
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

## Βήμα 5: Αποθηκεύστε την Τροποποιημένη Παρουσίαση

Αφού προσθέσετε τα εφέ κίνησης στο γράφημά σας, αποθηκεύστε την τροποποιημένη παρουσίαση στο δίσκο.

```csharp
//Αποθηκεύστε την τροποποιημένη παρουσίαση
presentation.Save(dataDir + "AnimatingSeries_out.pptx", SaveFormat.Pptx);
```

Αυτό είναι! Έχετε δημιουργήσει με επιτυχία σειρές κινουμένων σχεδίων σε ένα γράφημα χρησιμοποιώντας το Aspose.Slides για .NET.

## συμπέρασμα

Σε αυτό το σεμινάριο, σας καθοδηγήσαμε στη διαδικασία δημιουργίας κινούμενων σχεδίων σε ένα γράφημα χρησιμοποιώντας Aspose.Slides για .NET. Με αυτήν την ισχυρή βιβλιοθήκη, μπορείτε να δημιουργήσετε ελκυστικές και δυναμικές παρουσιάσεις που αιχμαλωτίζουν το κοινό σας.

 Εάν έχετε οποιεσδήποτε ερωτήσεις ή χρειάζεστε περαιτέρω βοήθεια, μη διστάσετε να απευθυνθείτε στην κοινότητα Aspose.Slides στο[φόρουμ υποστήριξης](https://forum.aspose.com/).

## Συχνές ερωτήσεις

### Μπορώ να κάνω κίνηση και άλλα στοιχεία γραφήματος εκτός από σειρές χρησιμοποιώντας το Aspose.Slides για .NET;
Ναι, μπορείτε να κάνετε κίνηση διαφόρων στοιχείων γραφήματος, συμπεριλαμβανομένων σημείων δεδομένων, αξόνων και υπομνημάτων, χρησιμοποιώντας το Aspose.Slides για .NET.

### Είναι το Aspose.Slides για .NET συμβατό με τις πιο πρόσφατες εκδόσεις του PowerPoint;
Το Aspose.Slides για .NET υποστηρίζει διάφορες εκδόσεις PowerPoint, συμπεριλαμβανομένου του PowerPoint 2007 και νεότερων, διασφαλίζοντας τη συμβατότητα με τις πιο πρόσφατες εκδόσεις.

### Μπορώ να προσαρμόσω τα εφέ κίνησης για κάθε σειρά γραφημάτων ξεχωριστά;
Ναι, μπορείτε να προσαρμόσετε τα εφέ κίνησης για κάθε σειρά γραφημάτων για να δημιουργήσετε μοναδικές και ελκυστικές παρουσιάσεις.

### Υπάρχει διαθέσιμη δοκιμαστική έκδοση για το Aspose.Slides για .NET;
 Ναι, μπορείτε να δοκιμάσετε τη βιβλιοθήκη με μια δωρεάν δοκιμή από το[Aspose.Slides για τον ιστότοπο .NET](https://releases.aspose.com/).

### Πού μπορώ να αγοράσω άδεια χρήσης για το Aspose.Slides για .NET;
 Μπορείτε να αποκτήσετε άδεια χρήσης για το Aspose.Slides για .NET από τη σελίδα αγοράς[εδώ](https://purchase.aspose.com/buy).