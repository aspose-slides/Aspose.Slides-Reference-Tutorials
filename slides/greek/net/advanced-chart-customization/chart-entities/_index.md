---
title: Δημιουργία όμορφων γραφημάτων με το Aspose.Slides για .NET
linktitle: Οντότητες γραφήματος και μορφοποίηση
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Μάθετε πώς να δημιουργείτε εντυπωσιακά γραφήματα με το Aspose.Slides για .NET. Αναβαθμίστε το παιχνίδι οπτικοποίησης δεδομένων με τον αναλυτικό οδηγό μας.
type: docs
weight: 13
url: /el/net/advanced-chart-customization/chart-entities/
---

Στον σημερινό κόσμο που βασίζεται στα δεδομένα, η αποτελεσματική οπτικοποίηση δεδομένων είναι το κλειδί για τη μετάδοση πληροφοριών στο κοινό σας. Το Aspose.Slides for .NET είναι μια ισχυρή βιβλιοθήκη που σας δίνει τη δυνατότητα να δημιουργήσετε εκπληκτικές παρουσιάσεις και διαφάνειες, συμπεριλαμβανομένων εντυπωσιακών γραφημάτων. Σε αυτό το σεμινάριο, θα σας καθοδηγήσουμε στη διαδικασία δημιουργίας όμορφων γραφημάτων χρησιμοποιώντας το Aspose.Slides για .NET. Θα αναλύσουμε κάθε παράδειγμα σε πολλά βήματα για να σας βοηθήσουμε να κατανοήσετε και να εφαρμόσετε οντότητες και μορφοποίηση γραφημάτων. Λοιπόν, ας ξεκινήσουμε!

## Προαπαιτούμενα

Πριν ξεκινήσουμε τη δημιουργία όμορφων γραφημάτων με το Aspose.Slides για .NET, θα πρέπει να βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

1.  Aspose.Slides για .NET: Βεβαιωθείτε ότι έχετε εγκαταστήσει τη βιβλιοθήκη Aspose.Slides για .NET. Μπορείτε να το κατεβάσετε από το[δικτυακός τόπος](https://releases.aspose.com/slides/net/).

2. Περιβάλλον ανάπτυξης: Θα πρέπει να έχετε ένα περιβάλλον ανάπτυξης εργασίας με το Visual Studio ή οποιοδήποτε άλλο IDE που υποστηρίζει την ανάπτυξη .NET.

3. Βασικές γνώσεις C#: Η εξοικείωση με τον προγραμματισμό C# είναι απαραίτητη για αυτό το σεμινάριο.

Τώρα που έχουμε ταξινομήσει τις προϋποθέσεις μας, ας προχωρήσουμε στη δημιουργία όμορφων γραφημάτων με το Aspose.Slides για .NET.

## Εισαγωγή χώρων ονομάτων

Αρχικά, πρέπει να εισαγάγετε τους απαραίτητους χώρους ονομάτων για να εργαστείτε με το Aspose.Slides για .NET:

```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides.Charts;
```

## Βήμα 1: Δημιουργήστε μια παρουσίαση

Ξεκινάμε δημιουργώντας μια νέα παρουσίαση για να δουλέψουμε. Αυτή η παρουσίαση θα χρησιμεύσει ως καμβάς για το διάγραμμά μας.

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

## Βήμα 2: Πρόσβαση στην Πρώτη Διαφάνεια

Ας αποκτήσουμε πρόσβαση στην πρώτη διαφάνεια της παρουσίασης όπου θα τοποθετήσουμε το γράφημά μας.

```csharp
// Πρόσβαση στην πρώτη διαφάνεια
ISlide slide = pres.Slides[0];
```

## Βήμα 3: Προσθέστε ένα δείγμα γραφήματος

Τώρα, θα προσθέσουμε ένα δείγμα γραφήματος στη διαφάνειά μας. Σε αυτό το παράδειγμα, θα δημιουργήσουμε ένα γραμμικό γράφημα με δείκτες.

```csharp
// Προσθήκη του δείγματος γραφήματος
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## Βήμα 4: Ορισμός τίτλου γραφήματος

Θα δώσουμε στο γράφημά μας έναν τίτλο, καθιστώντας το πιο ενημερωτικό και οπτικά ελκυστικό.

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

## Βήμα 5: Προσαρμόστε τις γραμμές πλέγματος κάθετου άξονα

Σε αυτό το βήμα, θα προσαρμόσουμε τις γραμμές πλέγματος κάθετου άξονα για να κάνουμε το γράφημά μας πιο ελκυστικό οπτικά.

```csharp
// Ρύθμιση μορφής βασικών γραμμών πλέγματος για τον άξονα τιμών
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Blue;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.Width = 5;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.DashStyle = LineDashStyle.DashDot;

// Ρύθμιση της μορφής γραμμών δευτερεύοντος πλέγματος για τον άξονα τιμών
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Red;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.Width = 3;

// Ορισμός μορφής αριθμού άξονα τιμής
chart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
chart.Axes.VerticalAxis.DisplayUnit = DisplayUnitType.Thousands;
chart.Axes.VerticalAxis.NumberFormat = "0.0%";
```

## Βήμα 6: Καθορίστε το εύρος κάθετου άξονα

Σε αυτό το βήμα, θα ορίσουμε τις μέγιστες, ελάχιστες και μοναδιαίες τιμές για τον κατακόρυφο άξονα.

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

## Βήμα 7: Προσαρμογή κειμένου κάθετου άξονα

Τώρα θα προσαρμόσουμε την εμφάνιση του κειμένου στον κατακόρυφο άξονα.

```csharp
// Ρύθμιση ιδιοτήτων κειμένου άξονα τιμής
IChartPortionFormat txtVal = chart.Axes.VerticalAxis.TextFormat.PortionFormat;
txtVal.FontBold = NullableBool.True;
txtVal.FontHeight = 16;
txtVal.FontItalic = NullableBool.True;
txtVal.FillFormat.FillType = FillType.Solid;
txtVal.FillFormat.SolidFillColor.Color = Color.DarkGreen;
txtVal.LatinFont = new FontData("Times New Roman");

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

## Βήμα 8: Προσαρμόστε τις γραμμές πλέγματος οριζόντιων αξόνων

Τώρα, ας προσαρμόσουμε τις γραμμές πλέγματος για τον οριζόντιο άξονα.

```csharp
// Ρύθμιση μορφής βασικών γραμμών πλέγματος για τον άξονα κατηγορίας
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Green;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.Width = 5;

// Ρύθμιση της μορφής γραμμών δευτερεύοντος πλέγματος για τον άξονα κατηγορίας
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Yellow;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.Width = 3;

// Ρύθμιση ιδιοτήτων κειμένου άξονα κατηγορίας
IChartPortionFormat txtCat = chart.Axes.HorizontalAxis.TextFormat.PortionFormat;
txtCat.FontBold = NullableBool.True;
txtCat.FontHeight = 16;
txtCat.FontItalic = NullableBool.True;
txtCat.FillFormat.Fill

Type = FillType.Solid;
txtCat.FillFormat.SolidFillColor.Color = Color.Blue;
txtCat.LatinFont = new FontData("Arial");
```

## Βήμα 9: Προσαρμόστε τις ετικέτες οριζόντιου άξονα

Σε αυτό το βήμα, θα προσαρμόσουμε τη θέση και την περιστροφή των ετικετών οριζόντιου άξονα.

```csharp
// Ρύθμιση θέσης ετικέτας άξονα κατηγορίας
chart.Axes.HorizontalAxis.TickLabelPosition = TickLabelPositionType.Low;

// Ρύθμιση γωνίας περιστροφής ετικέτας άξονα κατηγορίας
chart.Axes.HorizontalAxis.TickLabelRotationAngle = 45;
```

## Βήμα 10: Προσαρμόστε τα Legends

Ας βελτιώσουμε τους θρύλους στο γράφημά μας για καλύτερη αναγνωσιμότητα.

```csharp
// Ρύθμιση ιδιοτήτων κειμένου Legends
IChartPortionFormat txtleg = chart.Legend.TextFormat.PortionFormat;
txtleg.FontBold = NullableBool.True;
txtleg.FontHeight = 16;
txtleg.FontItalic = NullableBool.True;
txtleg.FillFormat.FillType = FillType.Solid;
txtleg.FillFormat.SolidFillColor.Color = Color.DarkRed;

// Ορίστε θρύλους εμφάνισης γραφημάτων χωρίς επικαλυπτόμενο γράφημα
chart.Legend.Overlay = true;
```

## Βήμα 11: Προσαρμογή του φόντου γραφήματος

Θα προσαρμόσουμε τα χρώματα φόντου του γραφήματος, του πίσω τοίχου και του δαπέδου.

```csharp
// Ρύθμιση χρώματος πίσω τοίχου γραφήματος
chart.BackWall.Thickness = 1;
chart.BackWall.Format.Fill.FillType = FillType.Solid;
chart.BackWall.Format.Fill.SolidFillColor.Color = Color.Orange;

chart.Floor.Format.Fill.FillType = FillType.Solid;
chart.Floor.Format.Fill.SolidFillColor.Color = Color.Red;

//Ρύθμιση χρώματος περιοχής γραφήματος
chart.PlotArea.Format.Fill.FillType = FillType.Solid;
chart.PlotArea.Format.Fill.SolidFillColor.Color = Color.LightCyan;
```

## Βήμα 12: Αποθηκεύστε την παρουσίαση

Τέλος, ας αποθηκεύσουμε την παρουσίασή μας με το μορφοποιημένο γράφημα.

```csharp
// Αποθήκευση παρουσίασης
pres.Save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## συμπέρασμα

Η δημιουργία όμορφων και ενημερωτικών γραφημάτων στις παρουσιάσεις σας είναι πλέον ευκολότερη από ποτέ με το Aspose.Slides για .NET. Σε αυτό το σεμινάριο, έχουμε καλύψει τα βασικά βήματα για την προσαρμογή διαφόρων πτυχών ενός γραφήματος, καθιστώντας το οπτικά ελκυστικό και ενημερωτικό. Με αυτές τις τεχνικές, μπορείτε να δημιουργήσετε εντυπωσιακά γραφήματα που μεταφέρουν αποτελεσματικά τα δεδομένα σας στο κοινό σας.

Ξεκινήστε να πειραματίζεστε με το Aspose.Slides για .NET και ανεβάστε την οπτικοποίηση των δεδομένων σας στο επόμενο επίπεδο!

## Συχνές Ερωτήσεις

### 1. Τι είναι το Aspose.Slides για .NET;

Το Aspose.Slides for .NET είναι μια ισχυρή βιβλιοθήκη που επιτρέπει στους προγραμματιστές .NET να δημιουργούν, να χειρίζονται και να μετατρέπουν παρουσιάσεις του Microsoft PowerPoint. Παρέχει ένα ευρύ φάσμα δυνατοτήτων για εργασία με διαφάνειες, σχήματα, γραφήματα και άλλα.

### 2. Πού μπορώ να κατεβάσω το Aspose.Slides για .NET;

 Μπορείτε να κάνετε λήψη του Aspose.Slides για .NET από τον ιστότοπο[εδώ](https://releases.aspose.com/slides/net/).

### 3. Υπάρχει διαθέσιμη δωρεάν δοκιμή για το Aspose.Slides για .NET;

 Ναι, μπορείτε να λάβετε μια δωρεάν δοκιμή του Aspose.Slides για .NET από[εδώ](https://releases.aspose.com/).

### 4. Πώς μπορώ να αποκτήσω μια προσωρινή άδεια χρήσης για το Aspose.Slides για .NET;

 Εάν χρειάζεστε μια προσωρινή άδεια, μπορείτε να αποκτήσετε μια από[αυτός ο σύνδεσμος](https://purchase.aspose.com/temporary-license/).

### 5. Υπάρχει κοινότητα ή φόρουμ υποστήριξης για το Aspose.Slides για .NET;

 Ναι, μπορείτε να βρείτε την κοινότητα Aspose.Slides και το φόρουμ υποστήριξης[εδώ](https://forum.aspose.com/).
