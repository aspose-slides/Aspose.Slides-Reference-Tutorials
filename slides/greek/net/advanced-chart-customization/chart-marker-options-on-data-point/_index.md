---
"description": "Μάθετε πώς να βελτιώσετε τα γραφήματα PowerPoint σας χρησιμοποιώντας το Aspose.Slides για .NET. Προσαρμόστε τους δείκτες σημείων δεδομένων με εικόνες. Δημιουργήστε ελκυστικές παρουσιάσεις."
"linktitle": "Επιλογές δείκτη γραφήματος σε σημείο δεδομένων"
"second_title": "API επεξεργασίας PowerPoint Aspose.Slides .NET"
"title": "Χρήση επιλογών δείκτη γραφήματος σε σημείο δεδομένων στο Aspose.Slides .NET"
"url": "/el/net/advanced-chart-customization/chart-marker-options-on-data-point/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Χρήση επιλογών δείκτη γραφήματος σε σημείο δεδομένων στο Aspose.Slides .NET


Όταν εργάζεστε με παρουσιάσεις και οπτικοποίηση δεδομένων, το Aspose.Slides για .NET προσφέρει ένα ευρύ φάσμα ισχυρών λειτουργιών για τη δημιουργία, την προσαρμογή και τον χειρισμό γραφημάτων. Σε αυτό το σεμινάριο, θα εξερευνήσουμε πώς να χρησιμοποιήσετε τις επιλογές δεικτών γραφήματος σε σημεία δεδομένων για να βελτιώσετε τις παρουσιάσεις γραφημάτων σας. Αυτός ο οδηγός βήμα προς βήμα θα σας καθοδηγήσει στη διαδικασία, ξεκινώντας από τις προϋποθέσεις και την εισαγωγή χώρων ονομάτων, έως την ανάλυση κάθε παραδείγματος σε πολλά βήματα.

## Προαπαιτούμενα

Πριν εμβαθύνουμε στη χρήση επιλογών δείκτη γραφήματος σε σημεία δεδομένων, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

- Aspose.Slides για .NET: Βεβαιωθείτε ότι έχετε εγκαταστήσει το Aspose.Slides για .NET. Μπορείτε να το κατεβάσετε από το [δικτυακός τόπος](https://releases.aspose.com/slides/net/).

- Δείγμα Παρουσίασης: Για αυτό το σεμινάριο, θα χρησιμοποιήσουμε ένα δείγμα παρουσίασης με το όνομα "Test.pptx". Θα πρέπει να έχετε αυτήν την παρουσίαση στον κατάλογο εγγράφων σας.

Τώρα, ας ξεκινήσουμε εισάγοντας τους απαραίτητους χώρους ονομάτων.

## Εισαγωγή χώρων ονομάτων

```csharp
﻿using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

Έχουμε εισαγάγει τους απαιτούμενους χώρους ονομάτων και έχουμε αρχικοποιήσει την παρουσίασή μας. Τώρα, ας προχωρήσουμε στη χρήση επιλογών δείκτη γραφήματος σε σημεία δεδομένων.

## Βήμα 1: Δημιουργία του προεπιλεγμένου γραφήματος

```csharp

// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");

ISlide slide = pres.Slides[0];

// Δημιουργία του προεπιλεγμένου γραφήματος
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

Δημιουργούμε ένα προεπιλεγμένο γράφημα τύπου "LineWithMarkers" στη διαφάνεια σε μια καθορισμένη θέση και μέγεθος.

## Βήμα 2: Λήψη του προεπιλεγμένου ευρετηρίου φύλλου εργασίας δεδομένων γραφήματος

```csharp
// Λήψη του προεπιλεγμένου ευρετηρίου φύλλου εργασίας δεδομένων γραφήματος
int defaultWorksheetIndex = 0;
```

Εδώ, λαμβάνουμε τον δείκτη του προεπιλεγμένου φύλλου εργασίας δεδομένων γραφήματος.

## Βήμα 3: Λήψη του Φύλλου Εργασίας Δεδομένων Γραφήματος

```csharp
// Λήψη του φύλλου εργασίας δεδομένων γραφήματος
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```

Ανακτούμε το βιβλίο εργασίας δεδομένων γραφήματος για να εργαστούμε με δεδομένα γραφήματος.

## Βήμα 4: Τροποποίηση της σειράς γραφημάτων

```csharp
// Διαγραφή σειράς επίδειξης
chart.ChartData.Series.Clear();

// Προσθήκη νέας σειράς
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);
```

Σε αυτό το βήμα, αφαιρούμε οποιαδήποτε υπάρχουσα σειρά επίδειξης και προσθέτουμε μια νέα σειρά με το όνομα "Σειρά 1" στο γράφημα.

## Βήμα 5: Ρύθμιση γεμίσματος εικόνας για σημεία δεδομένων

```csharp
// Ορίστε την εικόνα για τους δείκτες
System.Drawing.Image img1 = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx1 = pres.Images.AddImage(img1);

System.Drawing.Image img2 = (System.Drawing.Image)new Bitmap(dataDir + "Tulips.jpg");
IPPImage imgx2 = pres.Images.AddImage(img2);

// Πάρτε την πρώτη σειρά γραφημάτων
IChartSeries series = chart.ChartData.Series[0];

// Προσθήκη νέων σημείων δεδομένων με γέμισμα εικόνας
IChartDataPoint point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 1, 1, (double)4.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, (double)2.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, (double)3.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 4, 1, (double)4.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;
```

Ορίζουμε δείκτες εικόνας για σημεία δεδομένων, επιτρέποντάς σας να προσαρμόσετε τον τρόπο με τον οποίο εμφανίζεται κάθε σημείο δεδομένων στο γράφημα.

## Βήμα 6: Αλλαγή του μεγέθους του δείκτη σειράς γραφημάτων

```csharp
// Αλλαγή μεγέθους δείκτη σειράς γραφήματος
series.Marker.Size = 15;
```

Εδώ, προσαρμόζουμε το μέγεθος του δείκτη σειράς γραφήματος για να τον κάνουμε οπτικά ελκυστικό.

## Βήμα 7: Αποθήκευση της παρουσίασης

```csharp
pres.Save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

Τέλος, αποθηκεύουμε την παρουσίαση με τις νέες ρυθμίσεις του γραφήματος.

## Σύναψη

Το Aspose.Slides για .NET σάς δίνει τη δυνατότητα να δημιουργείτε εκπληκτικές παρουσιάσεις γραφημάτων με διάφορες επιλογές προσαρμογής. Σε αυτό το σεμινάριο, εστιάσαμε στη χρήση επιλογών δεικτών γραφημάτων σε σημεία δεδομένων για να βελτιώσουμε την οπτική αναπαράσταση των δεδομένων σας. Με το Aspose.Slides για .NET, μπορείτε να αναβαθμίσετε τις παρουσιάσεις σας, κάνοντάς τες πιο ελκυστικές και ενημερωτικές.

Εάν έχετε οποιεσδήποτε ερωτήσεις ή χρειάζεστε βοήθεια με το Aspose.Slides για .NET, μη διστάσετε να επισκεφθείτε την ιστοσελίδα [Τεκμηρίωση Aspose.Slides](https://reference.aspose.com/slides/net/) ή απευθυνθείτε στο [Κοινότητα Άσποζ](https://forum.aspose.com/) για υποστήριξη.

## Συχνές ερωτήσεις (FAQs)

### Μπορώ να χρησιμοποιήσω προσαρμοσμένες εικόνες ως δείκτες για σημεία δεδομένων στο Aspose.Slides για .NET;
Ναι, μπορείτε να χρησιμοποιήσετε προσαρμοσμένες εικόνες ως δείκτες για σημεία δεδομένων στο Aspose.Slides για .NET, όπως φαίνεται σε αυτό το σεμινάριο.

### Πώς μπορώ να αλλάξω τον τύπο γραφήματος στο Aspose.Slides για .NET;
Μπορείτε να αλλάξετε τον τύπο γραφήματος καθορίζοντας έναν διαφορετικό τύπο `ChartType` κατά τη δημιουργία του γραφήματος, όπως "Μπάρα", "Πίτα" ή "Εμβαδόν".

### Είναι το Aspose.Slides για .NET συμβατό με τις πιο πρόσφατες εκδόσεις του PowerPoint;
Το Aspose.Slides για .NET έχει σχεδιαστεί για να λειτουργεί με διάφορες μορφές PowerPoint και ενημερώνεται τακτικά για να διατηρείται η συμβατότητα με τις πιο πρόσφατες εκδόσεις του PowerPoint.

### Πού μπορώ να βρω περισσότερα εκπαιδευτικά βίντεο και πόρους για το Aspose.Slides για .NET;
Μπορείτε να εξερευνήσετε επιπλέον εκπαιδευτικά βοηθήματα και πόρους στο [Τεκμηρίωση Aspose.Slides](https://reference.aspose.com/slides/net/).

### Υπάρχει διαθέσιμη δοκιμαστική έκδοση του Aspose.Slides για .NET;
Ναι, μπορείτε να δοκιμάσετε το Aspose.Slides για .NET κατεβάζοντας μια δωρεάν δοκιμαστική έκδοση από το [εδώ](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}