---
"date": "2025-04-15"
"description": "Μάθετε πώς να δημιουργείτε δυναμικά γραφήματα ντόνατ χρησιμοποιώντας το Aspose.Slides για .NET. Ακολουθήστε αυτόν τον οδηγό για οδηγίες βήμα προς βήμα, συμπεριλαμβανομένης της εγκατάστασης και των προηγμένων λειτουργιών."
"title": "Οδηγός βήμα προς βήμα - Δημιουργία γραφήματος ντόνατ με το Aspose.Slides .NET | Γραφήματα & Διαγράμματα"
"url": "/el/net/charts-graphs/create-doughnut-chart-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Οδηγός βήμα προς βήμα: Δημιουργήστε γράφημα ντόνατ με το Aspose.Slides .NET

## Εισαγωγή

Φανταστείτε ότι σας έχει ανατεθεί η παρουσίαση αποτελεσμάτων ανάλυσης δεδομένων στην ομάδα ή τους πελάτες σας και χρειάζεστε έναν ελκυστικό τρόπο για να απεικονίσετε τις πληροφορίες. Εισάγετε το γράφημα ντόνατ—ένα ευέλικτο εργαλείο που μπορεί να μετατρέψει τους ακατέργαστους αριθμούς σε εύκολα κατανοητές πληροφορίες. Με το Aspose.Slides για .NET, η δημιουργία ενός προσαρμοσμένου γραφήματος ντόνατ στις διαφάνειες της παρουσίασής σας είναι απλή και αποτελεσματική. Αυτός ο οδηγός θα σας καθοδηγήσει στη χρήση του Aspose.Slides για να δημιουργήσετε ένα οπτικά ελκυστικό γράφημα ντόνατ, με προσαρμοσμένες διαμορφώσεις σειρών.

**Τι θα μάθετε:**
- Ρύθμιση του περιβάλλοντος ανάπτυξής σας με το Aspose.Slides για .NET
- Δημιουργία και προσαρμογή γραφημάτων ντόνατ σε παρουσιάσεις
- Υλοποίηση προηγμένων λειτουργιών όπως ονόματα κατηγοριών και γραμμές ηγέτη
- Βελτιστοποίηση απόδοσης για μεγάλα σύνολα δεδομένων

Ας δούμε αναλυτικά τις απαραίτητες προϋποθέσεις για να ξεκινήσετε.

## Προαπαιτούμενα

Πριν από την εφαρμογή αυτής της λειτουργίας, βεβαιωθείτε ότι το περιβάλλον ανάπτυξής σας έχει ρυθμιστεί σωστά. Αυτό το σεμινάριο προϋποθέτει βασικές γνώσεις προγραμματισμού .NET και εξοικείωση με το Visual Studio ή ένα παρόμοιο IDE.

### Απαιτούμενες βιβλιοθήκες και εκδόσεις
- **Aspose.Slides για .NET**: Βεβαιωθείτε για τη συμβατότητα με την πιο πρόσφατη έκδοση ελέγχοντας τα [επίσημη τεκμηρίωση](https://reference.aspose.com/slides/net/).

### Απαιτήσεις Ρύθμισης Περιβάλλοντος
- Ένα λειτουργικό περιβάλλον .NET.
- Πρόσβαση σε ένα πρόγραμμα επεξεργασίας κώδικα, όπως το Visual Studio.

### Προαπαιτούμενα Γνώσεων
- Βασική κατανόηση του C# και του .NET framework.
- Εξοικείωση με έννοιες λογισμικού παρουσιάσεων (προαιρετική αλλά χρήσιμη).

## Ρύθμιση του Aspose.Slides για .NET

Για να ξεκινήσετε να χρησιμοποιείτε το Aspose.Slides στο έργο σας, πρέπει να το εγκαταστήσετε μέσω του NuGet. Ακολουθούν οι διαθέσιμες μέθοδοι:

**Χρησιμοποιώντας το .NET CLI:**
```bash
dotnet add package Aspose.Slides
```

**Χρήση του Διαχειριστή Πακέτων:**
```powershell
Install-Package Aspose.Slides
```

**Διεπαφή χρήστη του διαχειριστή πακέτων NuGet:**
Αναζητήστε το "Aspose.Slides" και εγκαταστήστε την πιο πρόσφατη έκδοση.

### Βήματα απόκτησης άδειας χρήσης

1. **Δωρεάν δοκιμή**: Ξεκινήστε με ένα [δωρεάν δοκιμή](https://releases.aspose.com/slides/net/) για να εξερευνήσετε βασικές λειτουργίες.
2. **Προσωρινή Άδεια**Αποκτήστε μια προσωρινή άδεια χρήσης εάν χρειάζεστε πρόσβαση σε όλες τις λειτουργίες για σκοπούς αξιολόγησης, μεταβαίνοντας στη διεύθυνση [εδώ](https://purchase.aspose.com/temporary-license/).
3. **Αγορά**Για εμπορική χρήση, αγοράστε μια άδεια χρήσης από το [Ιστότοπος Aspose](https://purchase.aspose.com/buy).

Μόλις εγκατασταθεί και αδειοδοτηθεί, αρχικοποιήστε το Aspose.Slides στο έργο σας:
```csharp
using Aspose.Slides;

// Αρχικοποίηση του Aspose.Slides για .NET
var presentation = new Presentation();
```

## Οδηγός Εφαρμογής

### Δημιουργία νέας παρουσίασης και προσθήκη γραφήματος ντόνατ

#### Επισκόπηση
Θα ξεκινήσουμε δημιουργώντας μια νέα παρουσίαση και προσθέτοντας ένα γράφημα ντόνατ στην πρώτη διαφάνεια. Αυτή η ενότητα καλύπτει τη φόρτωση μιας υπάρχουσας παρουσίασης, την πρόσβαση σε διαφάνειες και την εισαγωγή γραφημάτων.

**Βήμα 1: Φόρτωση ή δημιουργία παρουσίασης**
Αρχικά, καθορίστε τον κατάλογο εγγράφων σας και φορτώστε μια υπάρχουσα παρουσίαση:
```csharp
string dataDir = \@"YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "testc.pptx");
```
Αν δεν έχετε υπάρχον αρχείο, δημιουργήστε ένα νέο με `new Presentation()`.

**Βήμα 2: Πρόσβαση στην πρώτη διαφάνεια**
Αποκτήστε πρόσβαση στην πρώτη διαφάνεια όπου θα προσθέσουμε το γράφημά μας:
```csharp
ISlide slide = pres.Slides[0];
```

**Βήμα 3: Προσθήκη γραφήματος ντόνατ**
Προσθέστε ένα γράφημα ντόνατ σε καθορισμένες συντεταγμένες και διαστάσεις:
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### Ρύθμιση παραμέτρων του βιβλίου εργασίας δεδομένων

#### Επισκόπηση
Αυτή η ενότητα εξηγεί τον τρόπο ρύθμισης παραμέτρων του βιβλίου εργασίας δεδομένων που σχετίζεται με το γράφημα δακτυλίου σας.

**Βήμα 4: Πρόσβαση και διαγραφή υπαρχόντων δεδομένων**
Αποκτήστε πρόσβαση στο βιβλίο εργασίας δεδομένων του γραφήματος. Στη συνέχεια, διαγράψτε τυχόν υπάρχουσες σειρές ή κατηγορίες:
```csharp
IChartDataWorkbook workBook = chart.ChartData.ChartDataWorkbook;
chart.ChartData.Series.Clear();
chart.ChartData.Categories.Clear();
```

**Βήμα 5: Απενεργοποίηση υπομνήματος και προσθήκη σειράς**
Απενεργοποιήστε το υπόμνημα για να διατηρήσετε το γράφημα καθαρό και, στη συνέχεια, προσθέστε έως και 15 σειρές με προσαρμοσμένες διαμορφώσεις:
```csharp
chart.HasLegend = false;

int seriesIndex = 0;
while (seriesIndex < 15)
{
    IChartSeries series = chart.ChartData.Series.Add(workBook.GetCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.Type);
    series.Explosion = 0;
    series.ParentSeriesGroup.DoughnutHoleSize = (byte)20;
    series.ParentSeriesGroup.FirstSliceAngle = 351;
    seriesIndex++;
}
```

### Προσθήκη κατηγοριών και σημείων δεδομένων

#### Επισκόπηση
Τώρα, ας συμπληρώσουμε το γράφημα με κατηγορίες και σημεία δεδομένων για κάθε σειρά.

**Βήμα 6: Προσθήκη κατηγοριών**
Κάντε επανάληψη για να προσθέσετε 15 κατηγορίες:
```csharp
int categoryIndex = 0;
while (categoryIndex < 15)
{
    chart.ChartData.Categories.Add(workBook.GetCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
```

**Βήμα 7: Συμπλήρωση σημείων δεδομένων**
Προσθέστε σημεία δεδομένων για κάθε σειρά εντός της τρέχουσας κατηγορίας:
```csharp
int i = 0;
while (i < chart.ChartData.Series.Count)
{
    IChartSeries iCS = chart.ChartData.Series[i];
    IChartDataPoint dataPoint = iCS.DataPoints.AddDataPointForDoughnutSeries(workBook.GetCell(0, categoryIndex + 1, i + 1, 1));

    // Προσαρμόστε την εμφάνιση
    dataPoint.Format.Fill.FillType = FillType.Solid;
    dataPoint.Format.Line.FillFormat.FillType = FillType.Solid;
    dataPoint.Format.Line.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;
    dataPoint.Format.Line.Width = 1;
    dataPoint.Format.Line.Style = LineStyle.Single;
    dataPoint.Format.Line.DashStyle = LineDashStyle.Solid;

    // Ρύθμιση παραμέτρων μορφής ετικέτας για την τελευταία σειρά
    if (i == chart.ChartData.Series.Count - 1)
    {
        IDataLabel lbl = dataPoint.Label;
        lbl.TextFormat.TextBlockFormat.AutofitType = TextAutofitType.Shape;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FontBold = NullableBool.True;
        lbl.DataLabelFormat.TextFormat.PortionFormat.LatinFont = new FontData("DINPro-Bold");
        lbl.DataLabelFormat.TextFormat.PortionFormat.FontHeight = 12;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.LightGray;
        lbl.DataLabelFormat.Format.Line.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;

        // Ρύθμιση παραμέτρων εμφάνισης ετικέτας
        lbl.DataLabelFormat.ShowValue = false;
        lbl.DataLabelFormat.ShowCategoryName = true;
        lbl.DataLabelFormat.ShowSeriesName = false;
        lbl.DataLabelFormat.ShowLeaderLines = true;

        chart.ValidateChartLayout();
        lbl.AsILayoutable.X += 0.5f;
        lbl.AsILayoutable.Y += 0.5f;
    }
    i++;
}
categoryIndex++;
```

### Αποθήκευση της παρουσίασης

**Βήμα 8: Αποθήκευση του αρχείου**
Τέλος, αποθηκεύστε την παρουσίασή σας σε έναν καθορισμένο κατάλογο:
```csharp
pres.Save(dataDir + "chart.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}