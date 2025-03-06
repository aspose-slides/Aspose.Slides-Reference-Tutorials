---
title: Εξερεύνηση γραμμών τάσης γραφήματος στο Aspose.Slides για .NET
linktitle: Γραμμές τάσης γραφήματος
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Μάθετε πώς να προσθέτετε διάφορες γραμμές τάσης σε γραφήματα χρησιμοποιώντας το Aspose.Slides για .NET σε αυτόν τον αναλυτικό οδηγό. Βελτιώστε τις δεξιότητες οπτικοποίησης δεδομένων σας με ευκολία!
weight: 12
url: /el/net/advanced-chart-customization/chart-trend-lines/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


Στον κόσμο της οπτικοποίησης και της παρουσίασης δεδομένων, η ενσωμάτωση γραφημάτων μπορεί να είναι ένας ισχυρός τρόπος για την αποτελεσματική μετάδοση πληροφοριών. Το Aspose.Slides for .NET παρέχει ένα σύνολο εργαλείων με πλούσια χαρακτηριστικά για εργασία με γραφήματα, συμπεριλαμβανομένης της δυνατότητας προσθήκης γραμμών τάσης στα γραφήματα σας. Σε αυτό το σεμινάριο, θα εμβαθύνουμε στη διαδικασία προσθήκης γραμμών τάσης σε ένα γράφημα με τρόπο βήμα προς βήμα χρησιμοποιώντας το Aspose.Slides για .NET. 

## Προαπαιτούμενα

Προτού αρχίσουμε να εργαζόμαστε με το Aspose.Slides για .NET, θα πρέπει να βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:

1. Aspose.Slides για .NET: Για να αποκτήσετε πρόσβαση στη βιβλιοθήκη και να τη χρησιμοποιήσετε, πρέπει να έχετε εγκατεστημένο το Aspose.Slides για .NET. Μπορείτε να πάρετε τη βιβλιοθήκη από το[σελίδα λήψης](https://releases.aspose.com/slides/net/).

2. Περιβάλλον ανάπτυξης: Θα πρέπει να έχετε ρυθμίσει ένα περιβάλλον ανάπτυξης, κατά προτίμηση χρησιμοποιώντας ένα ενσωματωμένο περιβάλλον ανάπτυξης .NET όπως το Visual Studio.

3. Βασικές γνώσεις C#: Η βασική κατανόηση του προγραμματισμού C# είναι επωφελής, καθώς θα χρησιμοποιήσουμε C# για να εργαστούμε με Aspose.Slides για .NET.

Τώρα που καλύψαμε τις προϋποθέσεις, ας αναλύσουμε τη διαδικασία προσθήκης γραμμών τάσης σε ένα γράφημα βήμα προς βήμα.

## Εισαγωγή χώρων ονομάτων

Πρώτα, βεβαιωθείτε ότι έχετε εισαγάγει τους απαραίτητους χώρους ονομάτων στο έργο σας C#. Αυτοί οι χώροι ονομάτων είναι απαραίτητοι για την εργασία με το Aspose.Slides για .NET.

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

## Βήμα 1: Δημιουργήστε μια παρουσίαση

Σε αυτό το βήμα, δημιουργούμε μια κενή παρουσίαση για εργασία.

```csharp
// Η διαδρομή προς τον κατάλογο εγγράφων.
string dataDir = "Your Document Directory";

// Δημιουργήστε κατάλογο εάν δεν υπάρχει ήδη.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// Δημιουργία κενής παρουσίασης
Presentation pres = new Presentation();
```

## Βήμα 2: Προσθέστε ένα γράφημα στη διαφάνεια

Στη συνέχεια, προσθέτουμε ένα γράφημα ομαδοποιημένης στήλης σε μια διαφάνεια.

```csharp
// Δημιουργία γραφήματος στηλών ομαδοποίησης
IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## Βήμα 3: Προσθέστε γραμμές τάσης στο γράφημα

Τώρα, προσθέτουμε διάφορους τύπους γραμμών τάσης στη σειρά γραφημάτων.

### Προσθήκη εκθετικής γραμμής τάσης

```csharp
// Προσθήκη εκθετικής γραμμής τάσης για τη σειρά γραφημάτων 1
ITrendline tredLineExp = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Exponential);
tredLineExp.DisplayEquation = false;
tredLineExp.DisplayRSquaredValue = false;
```

### Προσθήκη γραμμικής γραμμής τάσης

```csharp
// Προσθήκη γραμμικής γραμμής τάσης για τη σειρά γραφημάτων 1
ITrendline tredLineLin = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Linear);
tredLineLin.Format.Line.FillFormat.FillType = FillType.Solid;
tredLineLin.Format.Line.FillFormat.SolidFillColor.Color = Color.Red;
```

### Προσθήκη λογαριθμικής γραμμής τάσης

```csharp
// Προσθήκη λογαριθμικής γραμμής τάσης για τη σειρά γραφημάτων 2
ITrendline tredLineLog = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.Logarithmic);
tredLineLog.AddTextFrameForOverriding("New log trend line");
```

### Προσθήκη γραμμής τάσης κινούμενου μέσου όρου

```csharp
// Προσθήκη γραμμής τάσης κινητού μέσου όρου για τη σειρά γραφημάτων 2
ITrendline tredLineMovAvg = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.MovingAverage);
tredLineMovAvg.Period = 3;
tredLineMovAvg.TrendlineName = "New TrendLine Name";
```

### Προσθήκη πολυωνυμικής γραμμής τάσης

```csharp
// Προσθήκη πολυωνυμικής γραμμής τάσης για τη σειρά γραφημάτων 3
ITrendline tredLinePol = chart.ChartData.Series[2].TrendLines.Add(TrendlineType.Polynomial);
tredLinePol.Forward = 1;
tredLinePol.Order = 3;
```

### Προσθήκη γραμμής τάσης ισχύος

```csharp
// Προσθήκη γραμμής τάσης ισχύος για τη σειρά γραφημάτων 3
ITrendline tredLinePower = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.Power);
tredLinePower.Backward = 1;
```

## Βήμα 4: Αποθηκεύστε την Παρουσίαση

Αφού προσθέσετε γραμμές τάσης στο γράφημα, αποθηκεύστε την παρουσίαση.

```csharp
// Αποθήκευση παρουσίασης
pres.Save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

Αυτό είναι! Προσθέσατε με επιτυχία διάφορες γραμμές τάσεων στο γράφημά σας χρησιμοποιώντας το Aspose.Slides για .NET.

## συμπέρασμα

Το Aspose.Slides for .NET είναι μια ευέλικτη βιβλιοθήκη που σας επιτρέπει να δημιουργείτε και να χειρίζεστε γραφήματα με ευκολία. Ακολουθώντας αυτόν τον οδηγό βήμα προς βήμα, μπορείτε να προσθέσετε διαφορετικούς τύπους γραμμών τάσης στα γραφήματα σας, βελτιώνοντας την οπτική αναπαράσταση των δεδομένων σας.

### Συχνές ερωτήσεις

### Πού μπορώ να βρω την τεκμηρίωση για το Aspose.Slides για .NET;
 Μπορείτε να αποκτήσετε πρόσβαση στην τεκμηρίωση[εδώ](https://reference.aspose.com/slides/net/).

### Πώς μπορώ να κατεβάσω το Aspose.Slides για .NET;
 Μπορείτε να κάνετε λήψη του Aspose.Slides για .NET από τη σελίδα λήψης[εδώ](https://releases.aspose.com/slides/net/).

### Υπάρχει διαθέσιμη δωρεάν δοκιμή για το Aspose.Slides για .NET;
 Ναι, μπορείτε να δοκιμάσετε το Aspose.Slides για .NET δωρεάν επισκεπτόμενοι[αυτός ο σύνδεσμος](https://releases.aspose.com/).

### Πού μπορώ να αγοράσω Aspose.Slides για .NET;
 Για να αγοράσετε Aspose.Slides για .NET, επισκεφτείτε τη σελίδα αγοράς[εδώ](https://purchase.aspose.com/buy).

### Χρειάζομαι μια προσωρινή άδεια χρήσης για το Aspose.Slides για .NET;
 Μπορείτε να αποκτήσετε μια προσωρινή άδεια χρήσης για το Aspose.Slides για .NET από[αυτός ο σύνδεσμος](https://purchase.aspose.com/temporary-license/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
