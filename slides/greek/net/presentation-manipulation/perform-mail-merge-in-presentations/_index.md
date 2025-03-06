---
title: Εκτελέστε συγχώνευση αλληλογραφίας στις παρουσιάσεις
linktitle: Εκτελέστε συγχώνευση αλληλογραφίας στις παρουσιάσεις
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Μάθετε τη συγχώνευση αλληλογραφίας σε παρουσιάσεις χρησιμοποιώντας το Aspose.Slides για .NET σε αυτόν τον οδηγό βήμα προς βήμα. Δημιουργήστε δυναμικές, εξατομικευμένες παρουσιάσεις χωρίς κόπο.
weight: 21
url: /el/net/presentation-manipulation/perform-mail-merge-in-presentations/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Εισαγωγή
Στον κόσμο της ανάπτυξης .NET, η δημιουργία δυναμικών και εξατομικευμένων παρουσιάσεων είναι μια κοινή απαίτηση. Ένα ισχυρό εργαλείο που απλοποιεί αυτή τη διαδικασία είναι το Aspose.Slides για .NET. Σε αυτό το σεμινάριο, θα εμβαθύνουμε στη συναρπαστική σφαίρα της εκτέλεσης συγχώνευσης αλληλογραφίας σε παρουσιάσεις χρησιμοποιώντας το Aspose.Slides για .NET.
## Προαπαιτούμενα
Πριν ξεκινήσουμε αυτό το ταξίδι, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
- Aspose.Slides for .NET Library: Βεβαιωθείτε ότι έχετε εγκαταστήσει τη βιβλιοθήκη Aspose.Slides for .NET. Μπορείτε να το κατεβάσετε από[εδώ](https://releases.aspose.com/slides/net/).
- Πρότυπο εγγράφου: Προετοιμάστε ένα πρότυπο παρουσίασης (π.χ. PresentationTemplate.pptx) που θα χρησιμεύσει ως βάση για τη συγχώνευση αλληλογραφίας.
- Πηγή δεδομένων: Χρειάζεστε μια πηγή δεδομένων για τη συγχώνευση αλληλογραφίας. Στο παράδειγμά μας, θα χρησιμοποιήσουμε δεδομένα XML (TestData.xml), αλλά το Aspose.Slides υποστηρίζει διάφορες πηγές δεδομένων όπως το RDBMS.
Τώρα, ας βουτήξουμε στα βήματα της εκτέλεσης συγχώνευσης αλληλογραφίας σε παρουσιάσεις χρησιμοποιώντας το Aspose.Slides για .NET.
## Εισαγωγή χώρων ονομάτων
Αρχικά, βεβαιωθείτε ότι εισάγετε τους απαραίτητους χώρους ονομάτων για να αξιοποιήσετε τις λειτουργίες που παρέχονται από το Aspose.Slides:
```csharp
using System;
using System.Collections.Generic;
using System.Data;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Examples.CSharp;
using Aspose.Slides.Export;
using DataTable = System.Data.DataTable;
```
## Βήμα 1: Ρυθμίστε τον Κατάλογο Εγγράφων σας
```csharp
string dataDir = "Your Document Directory";
string presTemplatePath = Path.Combine(dataDir, "PresentationTemplate.pptx");
string resultPath = Path.Combine(RunExamples.OutPath, "MailMergeResult");
// Ελέγξτε εάν υπάρχει διαδρομή αποτελέσματος
if (!Directory.Exists(resultPath))
    Directory.CreateDirectory(resultPath);
```
## Βήμα 2: Δημιουργήστε ένα σύνολο δεδομένων με χρήση δεδομένων XML
```csharp
using (DataSet dataSet = new DataSet())
{
    dataSet.ReadXml(dataPath);
    DataTableCollection dataTables = dataSet.Tables;
    DataTable usersTable = dataTables["TestTable"];
    DataTable staffListTable = dataTables["StaffList"];
    DataTable planFactTable = dataTables["Plan_Fact"];
```
## Βήμα 3: Κάντε βρόχο μέσω των εγγραφών και δημιουργήστε μεμονωμένες παρουσιάσεις
```csharp
foreach (DataRow userRow in usersTable.Rows)
{
    // δημιουργία αποτελέσματος (ατομικής) όνομα παρουσίασης
    string presPath = Path.Combine(resultPath, "PresFor_" + userRow["Name"] + ".pptx");
    // Φόρτωση προτύπου παρουσίασης
    using (Presentation pres = new Presentation(presTemplatePath))
    {
        // Συμπληρώστε τα πλαίσια κειμένου με δεδομένα από τον κύριο πίνακα
        ((AutoShape)pres.Slides[0].Shapes[0]).TextFrame.Text = "Chief of the department - " + userRow["Name"];
        ((AutoShape)pres.Slides[0].Shapes[4]).TextFrame.Text = userRow["Department"].ToString();
        // Λήψη εικόνας από τη βάση δεδομένων
        byte[] bytes = Convert.FromBase64String(userRow["Img"].ToString());
        //Εισαγάγετε την εικόνα στην κορνίζα της παρουσίασης
        IPPImage image = pres.Images.AddImage(bytes);
        IPictureFrame pf = pres.Slides[0].Shapes[1] as PictureFrame;
        pf.PictureFormat.Picture.Image.ReplaceImage(image);
        // Αποκτήστε και προετοιμάστε το πλαίσιο κειμένου για να το γεμίσετε με δεδομένα
        IAutoShape list = pres.Slides[0].Shapes[2] as IAutoShape;
        ITextFrame textFrame = list.TextFrame;
        textFrame.Paragraphs.Clear();
        Paragraph para = new Paragraph();
        para.Text = "Department Staff:";
        textFrame.Paragraphs.Add(para);
        // Συμπληρώστε τα στοιχεία προσωπικού
        FillStaffList(textFrame, userRow, staffListTable);
        // Συμπληρώστε τα δεδομένα του σχεδίου
        FillPlanFact(pres, userRow, planFactTable);
        pres.Save(presPath, SaveFormat.Pptx);
    }
}
```
## Βήμα 4: Συμπληρώστε το πλαίσιο κειμένου με δεδομένα ως λίστα
```csharp
static void FillStaffList(ITextFrame textFrame, DataRow userRow, DataTable staffListTable)
{
    foreach (DataRow listRow in staffListTable.Rows)
    {
        if (listRow["UserId"].ToString() == userRow["Id"].ToString())
        {
            Paragraph para = new Paragraph();
            para.ParagraphFormat.Bullet.Type = BulletType.Symbol;
            para.ParagraphFormat.Bullet.Char = Convert.ToChar(8226);
            para.Text = listRow["Name"].ToString();
            para.ParagraphFormat.Bullet.Color.ColorType = ColorType.RGB;
            para.ParagraphFormat.Bullet.Color.Color = Color.Black;
            para.ParagraphFormat.Bullet.IsBulletHardColor = NullableBool.True;
            para.ParagraphFormat.Bullet.Height = 100;
            textFrame.Paragraphs.Add(para);
        }
    }
}
```
## Βήμα 5: Συμπληρώστε το γράφημα δεδομένων από τον πίνακα δευτερεύοντος PlanFact
```csharp
static void FillPlanFact(Presentation pres, DataRow row, DataTable planFactTable)
{
    IChart chart = pres.Slides[0].Shapes[3] as Chart;
    IChartTitle chartTitle = chart.ChartTitle;
    chartTitle.TextFrameForOverriding.Text = row["Name"] + " : Plan / Fact";
    DataRow[] selRows = planFactTable.Select("UserId = " + row["Id"]);
    string range = chart.ChartData.GetRange();
    IChartDataWorkbook cellsFactory = chart.ChartData.ChartDataWorkbook;
    int worksheetIndex = 0;
    // Προσθήκη σημείων δεδομένων για σειρές γραμμών
    chart.ChartData.Series[0].DataPoints.AddDataPointForLineSeries
(cellsFactory.GetCell(worksheetIndex, 1, 1, double.Parse(selRows[0]["PlanData"].ToString())));
    chart.ChartData.Series[1].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 1, 2, double.Parse(selRows[0]["FactData"].ToString())));
    chart.ChartData.Series[0].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 2, 1, double.Parse(selRows[1]["PlanData"].ToString())));
    chart.ChartData.Series[1].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 2, 2, double.Parse(selRows[1]["FactData"].ToString())));
    chart.ChartData.Series[0].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 3, 1, double.Parse(selRows[2]["PlanData"].ToString())));
    chart.ChartData.Series[1].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 3, 2, double.Parse(selRows[2]["FactData"].ToString())));
    chart.ChartData.Series[0].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 3, 1, double.Parse(selRows[3]["PlanData"].ToString())));
    chart.ChartData.Series[1].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 3, 2, double.Parse(selRows[3]["FactData"].ToString())));
    chart.ChartData.SetRange(range);
}
```
Αυτά τα βήματα παρουσιάζουν έναν περιεκτικό οδηγό για την εκτέλεση συγχώνευσης αλληλογραφίας σε παρουσιάσεις χρησιμοποιώντας το Aspose.Slides για .NET. Τώρα, ας εξετάσουμε μερικές συχνές ερωτήσεις.
## Συχνές Ερωτήσεις
### 1. Είναι το Aspose.Slides για .NET συμβατό με διαφορετικές πηγές δεδομένων;
Ναι, το Aspose.Slides για .NET υποστηρίζει διάφορες πηγές δεδομένων, συμπεριλαμβανομένων των XML, RDBMS και άλλων.
### 2. Μπορώ να προσαρμόσω την εμφάνιση των κουκκίδων στην παρουσίαση που δημιουργείται;
 Σίγουρα! Έχετε τον πλήρη έλεγχο της εμφάνισης των κουκκίδων, όπως αποδεικνύεται στο`FillStaffList` μέθοδος.
### 3. Τι τύπους γραφημάτων μπορώ να δημιουργήσω χρησιμοποιώντας το Aspose.Slides για .NET;
Το Aspose.Slides για .NET υποστηρίζει ένα ευρύ φάσμα γραφημάτων, συμπεριλαμβανομένων γραμμικών γραφημάτων όπως φαίνεται στο παράδειγμά μας, γραφημάτων ράβδων, γραφημάτων πίτας και άλλα.
### 4. Πώς μπορώ να λάβω υποστήριξη ή να αναζητήσω βοήθεια με το Aspose.Slides για .NET;
 Για υποστήριξη και βοήθεια, μπορείτε να επισκεφτείτε το[Φόρουμ Aspose.Slides](https://forum.aspose.com/c/slides/11).
### 5. Μπορώ να δοκιμάσω το Aspose.Slides για .NET πριν το αγοράσω;
 Σίγουρα! Μπορείτε να επωφεληθείτε από μια δωρεάν δοκιμή του Aspose.Slides για .NET από[εδώ](https://releases.aspose.com/).
## συμπέρασμα
Σε αυτό το σεμινάριο, εξερευνήσαμε τις συναρπαστικές δυνατότητες του Aspose.Slides για .NET στην εκτέλεση συγχώνευσης αλληλογραφίας σε παρουσιάσεις. Ακολουθώντας τον οδηγό βήμα προς βήμα, μπορείτε να δημιουργήσετε δυναμικές και εξατομικευμένες παρουσιάσεις χωρίς κόπο. Αναβαθμίστε την εμπειρία ανάπτυξης .NET με το Aspose.Slides για απρόσκοπτη δημιουργία παρουσιάσεων.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
