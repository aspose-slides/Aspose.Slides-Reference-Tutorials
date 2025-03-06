---
title: Προηγμένη προσαρμογή γραφήματος στο Aspose.Slides
linktitle: Προηγμένη προσαρμογή γραφήματος στο Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Μάθετε σύνθετη προσαρμογή γραφήματος στο Aspose.Slides για .NET. Δημιουργήστε οπτικά ελκυστικά γραφήματα με οδηγίες βήμα προς βήμα.
weight: 10
url: /el/net/advanced-chart-customization/advanced-chart-customization/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


Η δημιουργία οπτικά ελκυστικών και ενημερωτικών διαγραμμάτων είναι ουσιαστικό μέρος της παρουσίασης δεδομένων σε πολλές εφαρμογές. Το Aspose.Slides για .NET παρέχει ισχυρά εργαλεία για την προσαρμογή γραφημάτων, επιτρέποντάς σας να προσαρμόσετε με ακρίβεια κάθε πτυχή των γραφημάτων σας. Σε αυτό το σεμινάριο, θα εξερευνήσουμε προηγμένες τεχνικές προσαρμογής γραφημάτων χρησιμοποιώντας το Aspose.Slides για .NET.

## Προαπαιτούμενα

Πριν ξεκινήσετε την προηγμένη προσαρμογή γραφημάτων με το Aspose.Slides για .NET, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

1. Aspose.Slides for .NET Library: Πρέπει να έχετε εγκαταστήσει και να ρυθμίσετε σωστά τη βιβλιοθήκη Aspose.Slides στο έργο σας .NET. Μπορείτε να το κατεβάσετε από[εδώ](https://releases.aspose.com/slides/net/).

2. Περιβάλλον ανάπτυξης .NET: Θα πρέπει να έχετε ρυθμίσει ένα περιβάλλον ανάπτυξης .NET, συμπεριλαμβανομένου του Visual Studio ή οποιουδήποτε άλλου IDE της επιλογής σας.

3. Βασικές γνώσεις C#: Η εξοικείωση με τη γλώσσα προγραμματισμού C# θα είναι χρήσιμη, καθώς θα γράφουμε κώδικα C# για να δουλέψουμε με το Aspose.Slides.

Τώρα, ας αναλύσουμε την προηγμένη προσαρμογή γραφήματος σε πολλά βήματα για να σας καθοδηγήσουμε στη διαδικασία.

## Βήμα 1: Δημιουργήστε μια παρουσίαση

Αρχικά, δημιουργήστε μια νέα παρουσίαση χρησιμοποιώντας το Aspose.Slides.

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "Your Document Directory";

// Δημιουργήστε κατάλογο εάν δεν υπάρχει ήδη.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// Στιγμιαία παρουσίαση
Presentation pres = new Presentation();
```

Σε αυτό το βήμα, ξεκινάμε μια νέα παρουσίαση που θα κρατήσει το γράφημά μας.

## Βήμα 2: Πρόσβαση στην Πρώτη Διαφάνεια

Στη συνέχεια, αποκτήστε πρόσβαση στην πρώτη διαφάνεια της παρουσίασης όπου θέλετε να προσθέσετε το γράφημα.

```csharp
// Πρόσβαση στην πρώτη διαφάνεια
ISlide slide = pres.Slides[0];
```

Αυτό το απόσπασμα κώδικα σάς επιτρέπει να εργαστείτε με την πρώτη διαφάνεια της παρουσίασης.

## Βήμα 3: Προσθήκη δείγματος γραφήματος

Τώρα, ας προσθέσουμε ένα δείγμα γραφήματος στη διαφάνεια. Σε αυτό το παράδειγμα, θα δημιουργήσουμε ένα γραμμικό γράφημα με δείκτες.

```csharp
// Προσθήκη του δείγματος γραφήματος
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

Εδώ, καθορίζουμε τον τύπο του γραφήματος (LineWithMarkers) και τη θέση και τις διαστάσεις του στη διαφάνεια.

## Βήμα 4: Ρύθμιση τίτλου γραφήματος

Ας ορίσουμε έναν τίτλο για το γράφημα για να παρέχει το πλαίσιο.

```csharp
// Ρύθμιση τίτλου γραφήματος
chart.HasTitle = true;
chart.ChartTitle.AddTextFrameForOverriding("");
IPortion chartTitle = chart.ChartTitle.TextFrameForOverriding.Paragraphs[0].Portions[0];
chartTitle.Text = "Sample Chart";
chartTitle.PortionFormat.FillFormat.FillType = FillType.Solid;
chartTitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
chartTitle.PortionFormat.FontHeight = 20;
chartTitle.PortionFormat.FontBold = NullableBool.True;
chartTitle.PortionFormat.FontItalic = NullableBool.True;
```

Αυτός ο κώδικας ορίζει έναν τίτλο για το γράφημα, προσδιορίζοντας το κείμενο, την εμφάνιση και το στυλ γραμματοσειράς του.

## Βήμα 5: Προσαρμόστε τις κύριες γραμμές πλέγματος

Τώρα, ας προσαρμόσουμε τις κύριες γραμμές πλέγματος για τον άξονα τιμών.

```csharp
// Ρύθμιση μορφής βασικών γραμμών πλέγματος για τον άξονα τιμών
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Blue;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.Width = 5;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.DashStyle = LineDashStyle.DashDot;
```

Αυτό το βήμα διαμορφώνει την εμφάνιση των κύριων γραμμών πλέγματος στον άξονα τιμών.

## Βήμα 6: Προσαρμόστε τις μικρές γραμμές πλέγματος

Ομοίως, μπορούμε να προσαρμόσουμε τις δευτερεύουσες γραμμές πλέγματος για τον άξονα τιμών.

```csharp
// Ρύθμιση της μορφής γραμμών δευτερεύοντος πλέγματος για τον άξονα τιμών
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Red;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.Width = 3;
```

Αυτός ο κωδικός προσαρμόζει την εμφάνιση δευτερευόντων γραμμών πλέγματος στον άξονα τιμών.

## Βήμα 7: Καθορίστε τη μορφή αριθμού άξονα τιμής

Προσαρμόστε τη μορφή αριθμών για τον άξονα τιμών.

```csharp
// Ορισμός μορφής αριθμού άξονα τιμής
chart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
chart.Axes.VerticalAxis.DisplayUnit = DisplayUnitType.Thousands;
chart.Axes.VerticalAxis.NumberFormat = "0.0%";
```

Αυτό το βήμα σάς επιτρέπει να μορφοποιήσετε τους αριθμούς που εμφανίζονται στον άξονα τιμών.

## Βήμα 8: Ορίστε τις μέγιστες και ελάχιστες τιμές γραφήματος

Καθορίστε τις μέγιστες και ελάχιστες τιμές για το γράφημα.

```csharp
// Ρύθμιση μέγιστων, ελάχιστων τιμών γραφήματος
chart.Axes.VerticalAxis.IsAutomaticMajorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMaxValue = false;
chart.Axes.VerticalAxis.IsAutomaticMinorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMinValue = false;

chart.Axes.VerticalAxis.MaxValue = 15f;
chart.Axes.VerticalAxis.MinValue = -2f;
chart.Axes.VerticalAxis.MinorUnit = 0.5f;
chart.Axes.VerticalAxis.MajorUnit = 2.0f;
```

Εδώ, καθορίζετε το εύρος τιμών που πρέπει να εμφανίζει ο άξονας του γραφήματος.

## Βήμα 9: Προσαρμόστε τις ιδιότητες κειμένου του άξονα τιμών

Μπορείτε επίσης να προσαρμόσετε τις ιδιότητες κειμένου του άξονα τιμών.

```csharp
// Ρύθμιση ιδιοτήτων κειμένου άξονα τιμής
IChartPortionFormat txtVal = chart.Axes.VerticalAxis.TextFormat.PortionFormat;
txtVal.FontBold = NullableBool.True;
txtVal.FontHeight = 16;
txtVal.FontItalic = NullableBool.True;
txtVal.FillFormat.FillType = FillType.Solid;
txtVal.FillFormat.SolidFillColor.Color = Color.DarkGreen;
txtVal.LatinFont = new FontData("Times New Roman");
```

Αυτός ο κώδικας σάς επιτρέπει να προσαρμόσετε το στυλ γραμματοσειράς και την εμφάνιση των ετικετών του άξονα τιμών.

## Βήμα 10: Προσθήκη τίτλου άξονα αξίας

Εάν το γράφημά σας απαιτεί έναν τίτλο για τον άξονα τιμών, μπορείτε να τον προσθέσετε με αυτό το βήμα.

```csharp
// Ρύθμιση τίτλου άξονα τιμής
chart.Axes.VerticalAxis.HasTitle = true;
chart.Axes.VerticalAxis.Title.AddTextFrameForOverriding("");
IPortion valtitle = chart.Axes.VerticalAxis.Title.TextFrameForOverriding.Paragraphs[0].Portions[0];
valtitle.Text = "Primary Axis";
valtitle.PortionFormat.FillFormat.FillType = FillType.Solid;
valtitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
valtitle.PortionFormat.FontHeight = 20;
valtitle.PortionFormat.FontBold = NullableBool.True;
valtitle.PortionFormat.FontItalic = NullableBool.True;
```

Σε αυτό το βήμα, μπορείτε να ορίσετε έναν τίτλο για τον άξονα τιμών.

## Βήμα 11: Προσαρμόστε τις κύριες γραμμές πλέγματος για τον άξονα κατηγορίας

Τώρα, ας εστιάσουμε στις κύριες γραμμές πλέγματος για τον άξονα της κατηγορίας.

```csharp
// Ρύθμιση μορφής βασικών γραμμών πλέγματος για τον άξονα κατηγορίας
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes

.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Green;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.Width = 5;
```

Αυτός ο κώδικας διαμορφώνει την εμφάνιση των κύριων γραμμών πλέγματος στον άξονα της κατηγορίας.

## Βήμα 12: Προσαρμόστε τις μικρές γραμμές πλέγματος για τον άξονα κατηγορίας

Παρόμοια με τον άξονα τιμών, μπορείτε να προσαρμόσετε τις δευτερεύουσες γραμμές πλέγματος για τον άξονα της κατηγορίας.

```csharp
// Ρύθμιση της μορφής γραμμών δευτερεύοντος πλέγματος για τον άξονα κατηγορίας
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Yellow;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.Width = 3;
```

Εδώ, προσαρμόζετε την εμφάνιση των δευτερευόντων γραμμών πλέγματος στον άξονα της κατηγορίας.

## Βήμα 13: Προσαρμόστε τις ιδιότητες κειμένου του άξονα κατηγορίας

Προσαρμόστε τις ιδιότητες κειμένου για τις ετικέτες των αξόνων κατηγορίας.

```csharp
// Ρύθμιση ιδιοτήτων κειμένου άξονα κατηγορίας
IChartPortionFormat txtCat = chart.Axes.HorizontalAxis.TextFormat.PortionFormat;
txtCat.FontBold = NullableBool.True;
txtCat.FontHeight = 16;
txtCat.FontItalic = NullableBool.True;
txtCat.FillFormat.FillType = FillType.Solid;
txtCat.FillFormat.SolidFillColor.Color = Color.Blue;
txtCat.LatinFont = new FontData("Arial");
```

Αυτός ο κώδικας σάς επιτρέπει να προσαρμόσετε το στυλ γραμματοσειράς και την εμφάνιση των ετικετών των αξόνων κατηγορίας.

## Βήμα 14: Προσθήκη τίτλου άξονα κατηγορίας

Μπορείτε επίσης να προσθέσετε έναν τίτλο στον άξονα της κατηγορίας εάν χρειάζεται.

```csharp
// Ρύθμιση τίτλου κατηγορίας
chart.Axes.HorizontalAxis.HasTitle = true;
chart.Axes.HorizontalAxis.Title.AddTextFrameForOverriding("");

IPortion catTitle = chart.Axes.HorizontalAxis.Title.TextFrameForOverriding.Paragraphs[0].Portions[0];
catTitle.Text = "Sample Category";
catTitle.PortionFormat.FillFormat.FillType = FillType.Solid;
catTitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
catTitle.PortionFormat.FontHeight = 20;
catTitle.PortionFormat.FontBold = NullableBool.True;
catTitle.PortionFormat.FontItalic = NullableBool.True;
```

Σε αυτό το βήμα, μπορείτε να ορίσετε έναν τίτλο για τον άξονα της κατηγορίας.

## Βήμα 15: Πρόσθετες προσαρμογές

Μπορείτε να εξερευνήσετε περαιτέρω προσαρμογές, όπως θρύλους, χρώματα πίσω τοίχου, δαπέδου και γραφικής παράστασης. Αυτές οι προσαρμογές σάς επιτρέπουν να βελτιώσετε την οπτική ελκυστικότητα του γραφήματος σας.

```csharp
// Πρόσθετες προσαρμογές (προαιρετικά)

// Ρύθμιση ιδιοτήτων κειμένου Legends
IChartPortionFormat txtleg = chart.Legend.TextFormat.PortionFormat;
txtleg.FontBold = NullableBool.True;
txtleg.FontHeight = 16;
txtleg.FontItalic = NullableBool.True;
txtleg.FillFormat.FillType = FillType.Solid;
txtleg.FillFormat.SolidFillColor.Color = Color.DarkRed;

// Ορίστε θρύλους εμφάνισης γραφημάτων χωρίς επικαλυπτόμενο γράφημα
chart.Legend.Overlay = true;

// Σχεδίαση της πρώτης σειράς σε άξονα δευτερεύουσας τιμής (αν χρειάζεται)
// Chart.ChartData.Series[0].PlotOnSecondAxis = true;

// Ρύθμιση χρώματος πίσω τοίχου γραφήματος
chart.BackWall.Thickness = 1;
chart.BackWall.Format.Fill.FillType = FillType.Solid;
chart.BackWall.Format.Fill.SolidFillColor.Color = Color.Orange;

// Ρύθμιση χρώματος δαπέδου γραφήματος
chart.Floor.Format.Fill.FillType = FillType.Solid;
chart.Floor.Format.Fill.SolidFillColor.Color = Color.Red;

//Ρύθμιση χρώματος περιοχής γραφήματος
chart.PlotArea.Format.Fill.FillType = FillType.Solid;
chart.PlotArea.Format.Fill.SolidFillColor.Color = Color.LightCyan;

// Αποθηκεύστε την παρουσίαση
pres.Save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

Αυτές οι πρόσθετες προσαρμογές είναι προαιρετικές και μπορούν να εφαρμοστούν με βάση τις συγκεκριμένες απαιτήσεις σχεδίασης γραφήματος.

## συμπέρασμα

Σε αυτόν τον οδηγό βήμα προς βήμα, εξερευνήσαμε την προηγμένη προσαρμογή γραφημάτων χρησιμοποιώντας το Aspose.Slides για .NET. Έχετε μάθει πώς να δημιουργείτε μια παρουσίαση, να προσθέτετε ένα γράφημα και να ρυθμίζετε με ακρίβεια την εμφάνισή της, συμπεριλαμβανομένων γραμμών πλέγματος, ετικετών αξόνων και άλλων οπτικών στοιχείων. Με τις ισχυρές επιλογές προσαρμογής που παρέχονται από το Aspose.Slides, μπορείτε να δημιουργήσετε γραφήματα που μεταφέρουν αποτελεσματικά τα δεδομένα σας και προσελκύουν το κοινό σας.

 Εάν έχετε οποιεσδήποτε ερωτήσεις ή αντιμετωπίζετε προκλήσεις κατά την εργασία με το Aspose.Slides για .NET, μη διστάσετε να εξερευνήσετε την τεκμηρίωση[εδώ](https://reference.aspose.com/slides/net/) ή ζητήστε βοήθεια στο Aspose.Slides[δικαστήριο](https://forum.aspose.com/).

## Συχνές ερωτήσεις

### Ποιες εκδόσεις του .NET υποστηρίζονται από το Aspose.Slides για .NET;
Το Aspose.Slides for .NET υποστηρίζει διάφορες εκδόσεις .NET, συμπεριλαμβανομένων των .NET Framework και .NET Core. Μπορείτε να ανατρέξετε στην τεκμηρίωση για την πλήρη λίστα των υποστηριζόμενων εκδόσεων.

### Μπορώ να δημιουργήσω γραφήματα από πηγές δεδομένων, όπως αρχεία Excel, χρησιμοποιώντας το Aspose.Slides για .NET;
Ναι, το Aspose.Slides για .NET σάς επιτρέπει να δημιουργείτε γραφήματα από εξωτερικές πηγές δεδομένων, όπως υπολογιστικά φύλλα Excel. Μπορείτε να εξερευνήσετε την τεκμηρίωση για λεπτομερή παραδείγματα.

### Πώς μπορώ να προσθέσω προσαρμοσμένες ετικέτες δεδομένων στη σειρά γραφημάτων μου;
 Για να προσθέσετε προσαρμοσμένες ετικέτες δεδομένων στη σειρά γραφημάτων σας, μπορείτε να αποκτήσετε πρόσβαση στο`DataLabels` ιδιοκτησία της σειράς και προσαρμόστε τις ετικέτες όπως απαιτείται. Ανατρέξτε στην τεκμηρίωση για δείγματα κώδικα και παραδείγματα.

### Είναι δυνατή η εξαγωγή του γραφήματος σε διαφορετικές μορφές αρχείων, όπως μορφές PDF ή εικόνας;
Ναι, το Aspose.Slides for .NET παρέχει επιλογές για εξαγωγή της παρουσίασής σας με γραφήματα σε διάφορες μορφές, συμπεριλαμβανομένων μορφών PDF και εικόνας. Μπορείτε να χρησιμοποιήσετε τη βιβλιοθήκη για να αποθηκεύσετε την εργασία σας στην επιθυμητή μορφή εξόδου.

### Πού μπορώ να βρω περισσότερα μαθήματα και παραδείγματα για το Aspose.Slides για .NET;
 Μπορείτε να βρείτε πληθώρα εκπαιδευτικών προγραμμάτων, παραδειγμάτων κώδικα και τεκμηρίωσης στο Aspose.Slides[δικτυακός τόπος](https://reference.aspose.com/slides/net/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
