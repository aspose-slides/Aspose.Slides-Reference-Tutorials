---
"date": "2025-04-15"
"description": "Μάθετε πώς να δημιουργείτε οπτικά ελκυστικά γραφήματα στοιβαγμένων στηλών με βάση ποσοστά χρησιμοποιώντας το Aspose.Slides για .NET. Ακολουθήστε αυτόν τον οδηγό βήμα προς βήμα για σαφή οπτικοποίηση δεδομένων."
"title": "Πώς να δημιουργήσετε γραφήματα στοιβαγμένων στηλών με βάση ποσοστά στο .NET χρησιμοποιώντας το Aspose.Slides"
"url": "/el/net/charts-graphs/create-stacked-column-charts-asposeslides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Πώς να δημιουργήσετε ένα γράφημα στοιβαγμένων στηλών με βάση το ποσοστό χρησιμοποιώντας το Aspose.Slides για .NET

## Εισαγωγή

Στον τομέα της οπτικοποίησης δεδομένων, η σαφής και αποτελεσματική παρουσίαση των πληροφοριών είναι ζωτικής σημασίας για την αποτελεσματική λήψη αποφάσεων. Για την εύχρηστη εμφάνιση σύνθετων συνόλων δεδομένων, τα γραφήματα στοιβαγμένων στηλών με βάση τα ποσοστά είναι ιδανικά. Αυτός ο οδηγός θα σας καθοδηγήσει στη δημιουργία αυτών των γραφημάτων χρησιμοποιώντας το Aspose.Slides για .NET, μια ισχυρή βιβλιοθήκη σχεδιασμένη για τον χειρισμό αρχείων παρουσίασης.

Ακολουθώντας αυτό το σεμινάριο, θα μάθετε:
- Ρύθμιση δεδομένων γραφήματος και διαμόρφωση μορφών αριθμών.
- Προσθήκη σειρών και προσαρμογή της εμφάνισής τους.
- Μορφοποίηση ετικετών για βελτίωση της αναγνωσιμότητας.

Έτοιμοι να ξεκινήσετε; Ας ξεκινήσουμε με τις απαραίτητες προϋποθέσεις!

## Προαπαιτούμενα

Πριν δημιουργήσετε τα γραφήματα σωρευμένων στηλών που βασίζονται σε ποσοστά, βεβαιωθείτε ότι το περιβάλλον σας έχει ρυθμιστεί σωστά. Θα χρειαστείτε:

### Απαιτούμενες βιβλιοθήκες, εκδόσεις και εξαρτήσεις
- **Aspose.Slides για .NET**Βεβαιωθείτε ότι αυτή η βιβλιοθήκη είναι εγκατεστημένη.

### Απαιτήσεις Ρύθμισης Περιβάλλοντος
- Ένα περιβάλλον ανάπτυξης με εγκατεστημένο το .NET SDK.
- Visual Studio ή οποιοδήποτε συμβατό IDE για την εκτέλεση κώδικα C#.

### Προαπαιτούμενα Γνώσεων
- Βασική κατανόηση προγραμματισμού C#.
- Εξοικείωση με την εγκατάσταση έργων .NET και τη διαχείριση πακέτων.

## Ρύθμιση του Aspose.Slides για .NET

Για να ξεκινήσετε τη δημιουργία γραφημάτων με το Aspose.Slides, εγκαταστήστε πρώτα τη βιβλιοθήκη χρησιμοποιώντας μία από αυτές τις μεθόδους:

**.NET CLI**
```bash
dotnet add package Aspose.Slides
```

**Διαχειριστής πακέτων**
```powershell
Install-Package Aspose.Slides
```

**Διεπαφή χρήστη του διαχειριστή πακέτων NuGet**
- Αναζητήστε το "Aspose.Slides" και εγκαταστήστε την πιο πρόσφατη έκδοση.

### Βήματα απόκτησης άδειας χρήσης

Ξεκινήστε με μια δωρεάν δοκιμαστική περίοδο κατεβάζοντας μια προσωρινή άδεια χρήσης από [Ιστότοπος του Aspose](https://purchase.aspose.com/temporary-license/)Για συνεχή χρήση, σκεφτείτε να αγοράσετε μια πλήρη άδεια χρήσης. 

Μόλις ρυθμιστεί, ξεκινήστε το Aspose.Slides στο έργο σας:
```csharp
using Aspose.Slides;
```

## Οδηγός Εφαρμογής

Έχοντας έτοιμο το περιβάλλον, ας αναλύσουμε τη δημιουργία ενός γραφήματος σωρευμένων στηλών με βάση ποσοστά σε βήματα.

### Δημιουργία και διαμόρφωση του γραφήματος

#### Επισκόπηση
Δημιουργήστε μια παρουσία του `Presentation` κλάση, η οποία είναι απαραίτητη για την εργασία με διαφάνειες. Στη συνέχεια, προσθέστε και διαμορφώστε ένα γράφημα σωρευμένων στηλών στη διαφάνειά σας.

#### Προσθήκη γραφήματος με στοίβες στηλών
```csharp
// Δημιουργήστε μια παρουσία της κλάσης Presentation
document = new Presentation();

// Λήψη αναφοράς στην πρώτη διαφάνεια
slide = document.Slides[0];

// Προσθήκη γραφήματος PercentsStackedColumn στη θέση (20, 20) με μέγεθος (500x400)
chart = slide.Shapes.AddChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

#### Ρύθμιση μορφής αριθμών
Βεβαιωθείτε ότι τα δεδομένα σας εμφανίζονται ως ποσοστά:
```csharp
// Ρύθμιση παραμέτρων μορφής αριθμών για τον κατακόρυφο άξονα
columnChart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
columnChart.Axes.VerticalAxis.NumberFormat = "0.00%"; // Ορισμός μορφής αριθμού σε ποσοστό
```

#### Προσθήκη σειρών δεδομένων και σημείων
Διαγραφή υπαρχόντων δεδομένων σειράς και προσθήκη νέων:
```csharp
// Διαγραφή τυχόν υπαρχόντων δεδομένων σειράς
columnChart.ChartData.Series.Clear();

int defaultWorksheetIndex = 0;

// Βιβλίο εργασίας δεδομένων γραφήματος της Access
dataWorkbook = columnChart.ChartData.ChartDataWorkbook;

// Προσθήκη νέας σειράς δεδομένων "Κόκκινα"
series = columnChart.ChartData.Series.Add(dataWorkbook.GetCell(defaultWorksheetIndex, 0, 1, "Reds"), columnChart.Type);
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 1, 1, 0.30));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 2, 1, 0.50));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 3, 1, 0.80));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 4, 1, 0.65));

// Ορισμός χρώματος γεμίσματος για τη σειρά σε κόκκινο
series.Format.Fill.FillType = FillType.Solid;
series.Format.Fill.SolidFillColor.Color = System.Drawing.Color.Red;

// Ρύθμιση παραμέτρων ιδιοτήτων μορφής ετικέτας για τη σειρά "Κόκκινα"
series.Labels.DefaultDataLabelFormat.ShowValue = true;
series.Labels.DefaultDataLabelFormat.IsNumberFormatLinkedToSource = false;
series.Labels.DefaultDataLabelFormat.NumberFormat = "0.0%"; // Ορισμός μορφής ποσοστού
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FontHeight = 10;
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;

// Προσθήκη άλλης σειράς "Blues"
series2 = columnChart.ChartData.Series.Add(dataWorkbook.GetCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.Type);
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 4, 2, 0.35));

// Ορισμός χρώματος γεμίσματος για τη σειρά σε Μπλε
series2.Format.Fill.FillType = FillType.Solid;
series2.Format.Fill.SolidFillColor.Color = System.Drawing.Color.Blue;
series2.Labels.DefaultDataLabelFormat.ShowValue = true;
columnChart.Series[1].Labels.DefaultDataLabelFormat.IsNumberFormatLinkedToSource = false;
series2.Labels.DefaultDataLabelFormat.NumberFormat = "0.0%"; // Ορισμός μορφής ποσοστού
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FontHeight = 10;
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;
```

#### Αποθήκευση της παρουσίασης
Αποθηκεύστε την παρουσίασή σας σε ένα αρχείο:
```csharp
// Αποθήκευση της παρουσίασης σε μορφή PPTX
document.Save("YOUR_OUTPUT_DIRECTORY/SetDataLabelsPercentageSign_out.pptx");
```

### Συμβουλές αντιμετώπισης προβλημάτων
- Βεβαιωθείτε ότι όλοι οι χώροι ονομάτων έχουν εισαχθεί σωστά.
- Ελέγξτε για τυπογραφικά λάθη στα ονόματα ιδιοτήτων και στις κλήσεις μεθόδων.
- Επαληθεύστε ότι οι διαδρομές σας για την αποθήκευση αρχείων υπάρχουν και ότι έχετε τα σωστά δικαιώματα.

## Πρακτικές Εφαρμογές

Ακολουθούν ορισμένα σενάρια όπου τα γραφήματα σωρευμένων στηλών με βάση ποσοστά μπορούν να είναι πολύτιμα:
1. **Ανάλυση Πωλήσεων**: Οπτικοποιήστε την απόδοση του προϊόντος σε διαφορετικές περιοχές ως ποσοστό των συνολικών πωλήσεων.
2. **Κατανομή Προϋπολογισμού**Δείξτε πώς τα τμήματα κατανέμουν τον προϋπολογισμό τους σε σχέση με τις συνολικές δαπάνες της εταιρείας.
3. **Ερευνα αγοράς**Συγκρίνετε τις προτιμήσεις των καταναλωτών για διάφορες κατηγορίες προϊόντων με την πάροδο του χρόνου.
4. **Εκπαιδευτικά Δεδομένα**: Εμφάνιση της κατανομής των βαθμών των μαθητών σε διαφορετικά μαθήματα.
5. **Στατιστικά στοιχεία υγειονομικής περίθαλψης**: Αντιπροσωπεύουν δημογραφικά στοιχεία ασθενών σε πολλαπλές παθήσεις.

## Παράγοντες Απόδοσης

Για βέλτιστη απόδοση, λάβετε υπόψη:
- Περιορισμός του αριθμού των σημείων δεδομένων σε ό,τι είναι απαραίτητο.
- Προφόρτωση δεδομένων για ελαχιστοποίηση της επεξεργασίας κατά τον χρόνο εκτέλεσης.
- Χρήση αποτελεσματικών πρακτικών διαχείρισης μνήμης με το Aspose.Slides για .NET.

## Σύναψη

Συγχαρητήρια! Μάθατε με επιτυχία πώς να δημιουργείτε ένα γράφημα σωρευμένων στηλών με βάση ποσοστά χρησιμοποιώντας το Aspose.Slides για .NET. Αυτό το εργαλείο βελτιώνει τις παρουσιάσεις κάνοντας τα σύνθετα δεδομένα πιο κατανοητά και οπτικά ελκυστικά.

Επόμενα βήματα; Εξερευνήστε άλλους τύπους γραφημάτων που είναι διαθέσιμοι στο Aspose.Slides ή ενσωματώστε αυτήν τη λειτουργικότητα σε μεγαλύτερες εφαρμογές. Καλή κωδικοποίηση!

## Ενότητα Συχνών Ερωτήσεων

**Ε1: Μπορώ να χρησιμοποιήσω το Aspose.Slides δωρεάν;**
A1: Ναι, μπορείτε να ξεκινήσετε με μια δωρεάν δοκιμαστική έκδοση για να δοκιμάσετε τις δυνατότητες του Aspose.Slides.

**Ε2: Ποιοι τύποι γραφημάτων υποστηρίζονται από το Aspose.Slides για .NET;**
A2: Υποστηρίζει διάφορα γραφήματα όπως πίτα, ράβδους, στήλες, γραμμές και άλλα.

**Ε3: Πώς μπορώ να ξεκινήσω με το Aspose.Slides για .NET;**
A3: Εγκαταστήστε τη βιβλιοθήκη χρησιμοποιώντας NuGet ή .NET CLI όπως περιγράφεται παραπάνω. Ακολουθήστε την τεκμηρίωσή μας για να δημιουργήσετε το πρώτο σας γράφημα.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}