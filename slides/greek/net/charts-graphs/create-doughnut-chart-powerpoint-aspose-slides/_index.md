---
"date": "2025-04-15"
"description": "Μάθετε πώς να δημιουργείτε δυναμικά και οπτικά ελκυστικά γραφήματα ντόνατ σε παρουσιάσεις PowerPoint χρησιμοποιώντας την ισχυρή βιβλιοθήκη Aspose.Slides για .NET."
"title": "Πώς να δημιουργήσετε ένα γράφημα ντόνατ στο PowerPoint χρησιμοποιώντας το Aspose.Slides για .NET"
"url": "/el/net/charts-graphs/create-doughnut-chart-powerpoint-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Πώς να δημιουργήσετε ένα γράφημα ντόνατ στο PowerPoint χρησιμοποιώντας το Aspose.Slides για .NET
Η δημιουργία οπτικά ελκυστικών γραφημάτων είναι απαραίτητη για την αποτελεσματική παρουσίαση δεδομένων. Τα γραφήματα ντόνατ είναι ιδανικά για την απεικόνιση τμημάτων ενός συνόλου, καθιστώντας τα ιδανικά για οπτικοποίηση δεδομένων με βάση τα ποσοστά. Αυτό το σεμινάριο θα σας καθοδηγήσει στη δημιουργία ενός δυναμικού γραφήματος ντόνατ στο PowerPoint χρησιμοποιώντας την ισχυρή βιβλιοθήκη Aspose.Slides για .NET.

## Εισαγωγή
Οι παρουσιάσεις συχνά απαιτούν οπτικές αναπαραστάσεις σύνθετων συνόλων δεδομένων, όπου τα παραδοσιακά γραφήματα ράβδων ή γραμμών ενδέχεται να μην επαρκούν. Το γράφημα ντόνατ αναδεικνύεται σε ένα ευέλικτο εργαλείο για την αποτελεσματική επικοινωνία δεδομένων που βασίζονται σε ποσοστά με στυλ και σαφήνεια. Σε αυτό το σεμινάριο, θα εξερευνήσουμε πώς το Aspose.Slides για .NET απλοποιεί τη διαδικασία δημιουργίας αυτών των γραφημάτων απευθείας μέσα στο PowerPoint.

**Τι θα μάθετε:**
- Ρύθμιση του Aspose.Slides για .NET
- Οδηγίες βήμα προς βήμα για τη δημιουργία ενός γραφήματος ντόνατς
- Προσθήκη σειρών και κατηγοριών στο γράφημά σας
- Ρύθμιση παραμέτρων ετικετών δεδομένων για βελτιωμένη σαφήνεια
- Αποθήκευση της τελικής παρουσίασης

Ας δούμε πώς μπορείτε να αξιοποιήσετε το Aspose.Slides για .NET για να βελτιώσετε τις παρουσιάσεις σας με προσαρμοσμένα γραφήματα ντόνατ.

## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τα εξής στη διάθεσή σας:
- **Aspose.Slides για βιβλιοθήκη .NET**Διαθέσιμο μέσω NuGet ή απευθείας λήψης.
- **Περιβάλλον Ανάπτυξης**Το Visual Studio συνιστάται για έργα .NET.
- Βασική γνώση C# και εξοικείωση με τη δομή του PowerPoint.

## Ρύθμιση του Aspose.Slides για .NET
Για να ξεκινήσετε τη δημιουργία γραφημάτων, πρέπει πρώτα να ρυθμίσετε τη βιβλιοθήκη Aspose.Slides στο έργο σας. Ακολουθούν διάφοροι τρόποι για να την εγκαταστήσετε:

**Χρησιμοποιώντας το .NET CLI:**

```bash
dotnet add package Aspose.Slides
```

**Χρήση της Κονσόλας Διαχείρισης Πακέτων:**

```powershell
Install-Package Aspose.Slides
```

**Μέσω του περιβάλλοντος εργασίας χρήστη του NuGet Package Manager:**
Αναζητήστε το "Aspose.Slides" και εγκαταστήστε την πιο πρόσφατη έκδοση.

Μόλις εγκατασταθεί, μπορείτε να ξεκινήσετε τη ρύθμιση του έργου σας. Εάν είστε νέοι στο Aspose.Slides, σκεφτείτε να αποκτήσετε μια προσωρινή άδεια χρήσης ή μια δωρεάν δοκιμαστική έκδοση για να εξερευνήσετε όλες τις δυνατότητές του χωρίς περιορισμούς.

### Αρχικοποίηση του έργου σας
Δείτε πώς μπορείτε να αρχικοποιήσετε το Aspose.Slides στην εφαρμογή σας:

```csharp
using Aspose.Slides;

class Program
{
    static void Main()
    {
        // Δημιουργήστε μια παρουσία της κλάσης Presentation
        Presentation presentation = new Presentation();
        
        // Ο κώδικά σας για τον χειρισμό της παρουσίασης βρίσκεται εδώ
        
        // Αποθήκευση της παρουσίασης
        presentation.Save("output.pptx", SaveFormat.Pptx);
    }
}
```

## Οδηγός Εφαρμογής
### Δημιουργία γραφήματος ντόνατ
#### Επισκόπηση
Αρχικά, θα δημιουργήσουμε ένα κενό γράφημα ντόνατ σε μια διαφάνεια του PowerPoint. Αυτό χρησιμεύει ως βάση για την προσθήκη δεδομένων και την προσαρμογή της εμφάνισής του.

**Βήμα 1: Προσθήκη γραφήματος ντόνατ**

```csharp
using Aspose.Slides;

class CreateDoughnutChart
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        
        // Προσθήκη γραφήματος ντόνατ στην πρώτη διαφάνεια στη θέση (10, 10) με μέγεθος (500, 500)
        IChart chart = slide.getShapes().addChart(
            ChartType.Doughnut, 10, 10, 500, 500, false
        );

        // Διαγραφή υπαρχουσών σειρών και κατηγοριών
        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getCategories().clear();

        // Απενεργοποιήστε το υπόμνημα για πιο καθαρή εμφάνιση
        chart.setHasLegend(false);

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**Εξήγηση:**
- **προσθήκη γραφήματος**: Εισάγει ένα νέο γράφημα ντόνατ στη διαφάνεια.
- **getChartDataWorkbook**: Παρέχει πρόσβαση σε κελιά δεδομένων στο γράφημα για χειρισμό.

### Προσθήκη Σειρών και Κατηγοριών
#### Επισκόπηση
Στη συνέχεια, θα συμπληρώσουμε το γράφημά σας με ουσιαστικά δεδομένα προσθέτοντας σειρές και κατηγορίες.

**Βήμα 2: Προσθήκη Σειράς Δεδομένων**

```csharp
using Aspose.Slides;

class AddSeriesAndCategories
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        IChart chart = (IChart)slide.getShapes().get_Item(1);

        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

        // Προσθήκη σειράς
        for (int seriesIndex = 0; seriesIndex < 15; seriesIndex++)
        {
            IChartSeries series = chart.getChartData()
                .getSeries()
                .add(
                    workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
                    chart.getType()
                );

            // Προσαρμογή της τρύπας του ντόνατ και της γωνίας εκκίνησης
            series.setExplosion(0);
            series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
            series.getParentSeriesGroup().setFirstSliceAngle(351);
        }

        // Προσθήκη κατηγοριών
        for (int categoryIndex = 0; categoryIndex < 15; categoryIndex++)
        {
            chart.getChartData()
                .getCategories()
                .add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));

            for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
            {
                IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
                IChartDataPoint dataPoint = iCS
                    .getDataPoints()
                    .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

                // Μορφοποίηση του γεμίσματος και της γραμμής του σημείου δεδομένων
                dataPoint.getFormat().getFill().setFillType(FillType.Solid);
                dataPoint.getFormat().getLine()
                    .getFillFormat()
                    .setFillType(FillType.Solid);
                
                dataPoint.getFormat().getLine()
                    .getFillFormat()
                    .getSolidFillColor()
                    .setColor(Color.WHITE);
                
                dataPoint.getFormat().getLine().setWidth(1.0);
                dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
                dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
            }
        }

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**Εξήγηση:**
- **προσθέτω**: Εισάγει νέες σειρές και κατηγορίες στο γράφημα.
- **setDoughnutTropeSize**Ρυθμίζει το μέγεθος της τρύπας του ντόνατ, ενισχύοντας την οπτική του εμφάνιση.

### Ρύθμιση παραμέτρων ετικετών δεδομένων
#### Επισκόπηση
Οι ετικέτες δεδομένων παρέχουν πληροφορίες για τα δεδομένα του γραφήματός σας. Ας βελτιώσουμε την αναγνωσιμότητα προσαρμόζοντάς τες.

**Βήμα 3: Προσαρμογή ετικετών δεδομένων**

```csharp
using Aspose.Slides;

class ConfigureDataLabels
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        IChart chart = (IChart)slide.getShapes().get_Item(1);

        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

        for (int categoryIndex = 0; categoryIndex < 15; categoryIndex++)
        {
            for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
            {
                IChartSeries series = chart.getChartData().getSeries().get_Item(i);
                IChartDataPoint dataPoint = series
                    .getDataPoints()
                    .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

                // Προσαρμογή ετικετών δεδομένων
                IDataLabel lbl = dataPoint.getLabel();
                lbl.getDataLabelFormat().setTextFormat()
                    .setCenterText(NullableBool.True)
                    .setShowPercentage(true);
                lbl.setVisible(true);
            }
        }

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**Εξήγηση:**
- **IDataLabel**Προσαρμόζει τις ετικέτες δεδομένων για σαφήνεια και παρουσίαση.
- **setCenterText**, **εμφάνιση ποσοστού**Βελτιώστε την αναγνωσιμότητα της ετικέτας κεντράροντας το κείμενο και εμφανίζοντας ποσοστά.

## Σύναψη
Ακολουθώντας αυτόν τον οδηγό, μάθατε πώς να δημιουργήσετε ένα δυναμικό γράφημα ντόνατ στο PowerPoint χρησιμοποιώντας το Aspose.Slides για .NET. Αυτή η ισχυρή βιβλιοθήκη επιτρέπει εκτεταμένη προσαρμογή, επιτρέποντάς σας να προσαρμόσετε τα γραφήματά σας με ακρίβεια στις ανάγκες της παρουσίασής σας.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}