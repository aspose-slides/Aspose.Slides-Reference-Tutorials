---
"date": "2025-04-15"
"description": "Μάθετε πώς να βελτιώσετε τις παρουσιάσεις σας με γραφήματα διασποράς χρησιμοποιώντας το Aspose.Slides για .NET. Ακολουθήστε αυτόν τον ολοκληρωμένο οδηγό για να δημιουργήσετε και να προσαρμόσετε γραφήματα αποτελεσματικά."
"title": "Προσθήκη γραφημάτων διασποράς σε παρουσιάσεις χρησιμοποιώντας το Aspose.Slides .NET® - Ένας οδηγός βήμα προς βήμα"
"url": "/el/net/charts-graphs/aspose-slides-net-scatter-charts-presentation-guide/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Προσθήκη γραφημάτων διασποράς σε παρουσιάσεις χρησιμοποιώντας το Aspose.Slides .NET: Οδηγός βήμα προς βήμα

## Εισαγωγή
Θέλετε να βελτιώσετε τις παρουσιάσεις σας ενσωματώνοντας γραφήματα διασποράς χωρίς κόπο; Με τη δύναμη του Aspose.Slides για .NET, η δημιουργία και η προσαρμογή γραφημάτων γίνεται παιχνιδάκι. Αυτό το σεμινάριο θα σας καθοδηγήσει στην προσθήκη γραφημάτων διασποράς στις διαφάνειές σας χρησιμοποιώντας το Aspose.Slides για .NET. Κατακτώντας αυτές τις τεχνικές, θα παρουσιάζετε δεδομένα πιο αποτελεσματικά και θα δημιουργείτε οπτικά ελκυστικές παρουσιάσεις.

**Τι θα μάθετε:**
- Ρύθμιση του Aspose.Slides για .NET στο έργο σας
- Δημιουργία νέας παρουσίασης και πρόσβαση στην πρώτη της διαφάνεια
- Προσθήκη γραφημάτων διασποράς με ομαλές γραμμές σε διαφάνειες
- Διαγραφή υπαρχουσών σειρών και προσθήκη νέων σε γραφήματα
- Τροποποίηση σημείων δεδομένων και στυλ δεικτών για βελτιωμένη οπτικοποίηση
- Αποθήκευση της παρουσίασης σε έναν καθορισμένο κατάλογο

Ας ξεκινήσουμε εξετάζοντας τις προϋποθέσεις.

## Προαπαιτούμενα
Πριν από την υλοποίηση του Aspose.Slides για .NET, βεβαιωθείτε ότι έχετε τα εξής:
- **Aspose.Slides για τη βιβλιοθήκη .NET**Έκδοση 23.7 ή νεότερη.
- **Περιβάλλον Ανάπτυξης**Visual Studio 2019 ή νεότερη έκδοση με .NET Framework 4.6.1+ ή .NET Core/5+.
- **Βασικές γνώσεις C#**Εξοικείωση με τον αντικειμενοστρεφή προγραμματισμό σε C#.

## Ρύθμιση του Aspose.Slides για .NET
Για να ξεκινήσετε να χρησιμοποιείτε το Aspose.Slides, πρέπει να εγκαταστήσετε τη βιβλιοθήκη στο έργο σας. Δείτε πώς:

**Χρησιμοποιώντας το .NET CLI:**
```bash
dotnet add package Aspose.Slides
```

**Χρήση της Κονσόλας Διαχείρισης Πακέτων:**
```powershell
Install-Package Aspose.Slides
```

**Διεπαφή χρήστη του διαχειριστή πακέτων NuGet:**
- Αναζητήστε το "Aspose.Slides" και εγκαταστήστε την πιο πρόσφατη έκδοση.

### Απόκτηση Άδειας
Μπορείτε να ξεκινήσετε με μια δωρεάν δοκιμαστική περίοδο ή να υποβάλετε αίτηση για μια προσωρινή άδεια χρήσης για να εξερευνήσετε όλες τις λειτουργίες. Για να αγοράσετε, ακολουθήστε τα εξής βήματα:
1. Επίσκεψη [Αγορά Aspose.Slides](https://purchase.aspose.com/buy) για να αγοράσετε μια πλήρη άδεια χρήσης.
2. Για προσωρινή άδεια, επισκεφθείτε την ιστοσελίδα [Σελίδα Προσωρινής Άδειας Χρήσης](https://purchase.aspose.com/temporary-license/).

Μόλις λάβετε το αρχείο άδειας χρήσης, προσθέστε το στο έργο σας χρησιμοποιώντας:
```csharp
Aspose.Slides.License license = new Aspose.Slides.License();
license.SetLicense("Aspose.Slides.lic");
```

## Οδηγός Εφαρμογής
Θα αναλύσουμε την υλοποίηση σε λογικά τμήματα με βάση τα χαρακτηριστικά.

### Δημιουργία παρουσίασης και προσθήκη διαφάνειας
Αυτή η ενότητα δείχνει πώς να δημιουργήσετε μια παρουσίαση και να αποκτήσετε πρόσβαση στην πρώτη της διαφάνεια.

#### Επισκόπηση
Ξεκινήστε δημιουργώντας μια παρουσία του `Presentation` κλάση, η οποία αντιπροσωπεύει το αρχείο PowerPoint σας. Η πρόσβαση σε διαφάνειες είναι απλή χρησιμοποιώντας αυτό το μοντέλο αντικειμένου.

#### Βήματα Υλοποίησης
**Βήμα 1: Αρχικοποίηση παρουσίασης**
```csharp
using Aspose.Slides;

// Δημιουργία νέας παρουσίασης
t Presentation pres = new Presentation();
```
Αυτός ο κώδικας αρχικοποιεί ένα νέο έγγραφο παρουσίασης.

**Βήμα 2: Πρόσβαση στην Πρώτη Διαφάνεια**
```csharp
// Πρόσβαση στην πρώτη διαφάνεια της παρουσίασης
ISlide slide = pres.Slides[0];
```
Εδώ, `pres.Slides[0]` έχει πρόσβαση στην πρώτη κιόλας διαφάνεια. 

### Προσθήκη γραφήματος διασποράς σε διαφάνεια
Τώρα ας προσθέσουμε ένα γράφημα διασποράς στην παρουσίασή σας.

#### Επισκόπηση
Η προσθήκη γραφημάτων μπορεί να σας βοηθήσει να αναπαραστήσετε δεδομένα οπτικά σε παρουσιάσεις. Το Aspose.Slides απλοποιεί την ενσωμάτωση διαφόρων τύπων γραφημάτων, συμπεριλαμβανομένων των διαγραμμάτων διασποράς.

#### Βήματα Υλοποίησης
**Βήμα 1: Δημιουργία και προσθήκη γραφήματος διασποράς**
```csharp
using Aspose.Slides.Charts;

// Δημιουργήστε και προσθέστε ένα προεπιλεγμένο γράφημα διασποράς με ομαλές γραμμές
IChart chart = slide.Shapes.AddChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
Αυτό το τμήμα κώδικα προσθέτει ένα γράφημα διασποράς στην καθορισμένη θέση και μέγεθος.

### Εκκαθάριση και προσθήκη σειρών σε δεδομένα γραφήματος
#### Επισκόπηση
Ενδέχεται να χρειαστεί να προσαρμόσετε το γράφημά σας διαγράφοντας τις υπάρχουσες σειρές και προσθέτοντας νέες. Αυτή η ενότητα καλύπτει αυτήν τη λειτουργικότητα.

#### Βήματα Υλοποίησης
**Βήμα 1: Βιβλίο εργασίας δεδομένων γραφήματος πρόσβασης**
```csharp
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;

// Διαγραφή τυχόν προϋπάρχουσας σειράς
chart.ChartData.Series.Clear();
```
Αυτός ο κώδικας διαγράφει τα υπάρχοντα δεδομένα για να ξεκινήσει από την αρχή με νέες σειρές.

**Βήμα 2: Προσθήκη νέας σειράς**
```csharp
// Προσθήκη νέας σειράς με το όνομα "Σειρά 1"
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);

// Προσθήκη άλλης σειράς με το όνομα "Σειρά 2"
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.Type);
```
Αυτά τα βήματα προσθέτουν δύο νέες σειρές στο γράφημα.

### Τροποποίηση σημείων δεδομένων πρώτης σειράς και στυλ δείκτη
#### Επισκόπηση
Προσαρμόστε τα σημεία δεδομένων και τα στυλ δεικτών για καλύτερη οπτικοποίηση των διαγραμμάτων διασποράς σας.

#### Βήματα Υλοποίησης
**Βήμα 1: Πρόσβαση και προσθήκη σημείων δεδομένων**
```csharp
IChartSeries series = chart.ChartData.Series[0];

// Προσθέστε τα σημεία δεδομένων (1, 3) και (2, 10)
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, 1), fact.GetCell(defaultWorksheetIndex, 2, 2, 3));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, 2), fact.GetCell(defaultWorksheetIndex, 3, 2, 10));
```
**Βήμα 2: Τροποποίηση στυλ δείκτη**
```csharp
// Αλλαγή του τύπου σειράς και τροποποίηση του στυλ δείκτη
series.Type = ChartType.ScatterWithStraightLinesAndMarkers;
series.Marker.Size = 10;
series.Marker.Symbol = MarkerStyleType.Star;
```
### Τροποποίηση σημείων δεδομένων δεύτερης σειράς και στυλ δείκτη
#### Επισκόπηση
Ομοίως, προσαρμόστε τη δεύτερη σειρά για να προσαρμόσετε τις ανάγκες της παρουσίασής σας.

#### Βήματα Υλοποίησης
**Βήμα 1: Πρόσβαση και προσθήκη πολλαπλών σημείων δεδομένων**
```csharp
// Αποκτήστε πρόσβαση στη δεύτερη σειρά γραφημάτων
series = chart.ChartData.Series[1];

// Προσθήκη πολλαπλών σημείων δεδομένων
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 2, 3, 5), fact.GetCell(defaultWorksheetIndex, 2, 4, 2));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 3, 3, 3), fact.GetCell(defaultWorksheetIndex, 3, 4, 1));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 4, 3, 2), fact.GetCell(defaultWorksheetIndex, 4, 4, 2));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 5, 3, 5), fact.GetCell(defaultWorksheetIndex, 5, 4, 1));
```
**Βήμα 2: Τροποποίηση στυλ δείκτη**
```csharp
// Αλλαγή μεγέθους και συμβόλου δείκτη για τη δεύτερη σειρά
series.Marker.Size = 10;
series.Marker.Symbol = MarkerStyleType.Circle;
```
### Αποθήκευση παρουσίασης
Τέλος, αποθηκεύστε την παρουσίασή σας σε έναν καθορισμένο κατάλογο.

#### Βήματα Υλοποίησης
**Βήμα 1: Ορισμός καταλόγου**
Βεβαιωθείτε ότι ο κατάλογος εξόδου υπάρχει. Εάν όχι, δημιουργήστε τον:
```csharp
using Aspose.Slides.Export;
using System.IO;

string YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
bool isExists = Directory.Exists(YOUR_DOCUMENT_DIRECTORY);
if (!isExists) 
    Directory.CreateDirectory(YOUR_DOCUMENT_DIRECTORY);

// Αποθήκευση της παρουσίασης
pres.Save(YOUR_DOCUMENT_DIRECTORY + "\AsposeChart_out.pptx", SaveFormat.Pptx);
```
Αυτός ο κώδικας αποθηκεύει το αρχείο της παρουσίασής σας σε μια καθορισμένη τοποθεσία.

## Σύναψη
Έχετε πλέον προσθέσει με επιτυχία γραφήματα διασποράς στις παρουσιάσεις σας χρησιμοποιώντας το Aspose.Slides για .NET. Συνεχίστε να εξερευνάτε πρόσθετες λειτουργίες και προσαρμογές που είναι διαθέσιμες στη βιβλιοθήκη για να βελτιώσετε τις δεξιότητές σας στην οπτικοποίηση δεδομένων.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}