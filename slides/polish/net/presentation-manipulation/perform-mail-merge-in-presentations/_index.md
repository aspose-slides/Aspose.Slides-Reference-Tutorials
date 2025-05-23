---
"description": "Naucz się łączenia korespondencji seryjnej w prezentacjach przy użyciu Aspose.Slides dla .NET w tym przewodniku krok po kroku. Twórz dynamiczne, spersonalizowane prezentacje bez wysiłku."
"linktitle": "Wykonywanie korespondencji seryjnej w prezentacjach"
"second_title": "Aspose.Slides .NET API przetwarzania programu PowerPoint"
"title": "Wykonywanie korespondencji seryjnej w prezentacjach"
"url": "/pl/net/presentation-manipulation/perform-mail-merge-in-presentations/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Wykonywanie korespondencji seryjnej w prezentacjach

## Wstęp
świecie rozwoju .NET tworzenie dynamicznych i spersonalizowanych prezentacji jest powszechnym wymogiem. Jednym z potężnych narzędzi, które upraszcza ten proces, jest Aspose.Slides dla .NET. W tym samouczku zagłębimy się w fascynującą dziedzinę wykonywania korespondencji seryjnej w prezentacjach przy użyciu Aspose.Slides dla .NET.
## Wymagania wstępne
Zanim wyruszysz w tę podróż, upewnij się, że spełniasz następujące wymagania:
- Biblioteka Aspose.Slides dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.Slides dla .NET. Możesz ją pobrać z [Tutaj](https://releases.aspose.com/slides/net/).
- Szablon dokumentu: Przygotuj szablon prezentacji (np. PresentationTemplate.pptx), który będzie stanowił podstawę do korespondencji seryjnej.
- Źródło danych: Potrzebujesz źródła danych do korespondencji seryjnej. W naszym przykładzie użyjemy danych XML (TestData.xml), ale Aspose.Slides obsługuje różne źródła danych, takie jak RDBMS.
Przyjrzyjmy się teraz bliżej krokom wykonywania korespondencji seryjnej w prezentacjach przy użyciu Aspose.Slides dla platformy .NET.
## Importuj przestrzenie nazw
Po pierwsze, upewnij się, że zaimportowałeś niezbędne przestrzenie nazw, aby wykorzystać funkcjonalności udostępniane przez Aspose.Slides:
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
## Krok 1: Skonfiguruj katalog dokumentów
```csharp
string dataDir = "Your Document Directory";
string presTemplatePath = Path.Combine(dataDir, "PresentationTemplate.pptx");
string resultPath = Path.Combine(RunExamples.OutPath, "MailMergeResult");
// Sprawdź, czy ścieżka wyników istnieje
if (!Directory.Exists(resultPath))
    Directory.CreateDirectory(resultPath);
```
## Krok 2: Utwórz zestaw danych przy użyciu danych XML
```csharp
using (DataSet dataSet = new DataSet())
{
    dataSet.ReadXml(dataPath);
    DataTableCollection dataTables = dataSet.Tables;
    DataTable usersTable = dataTables["TestTable"];
    DataTable staffListTable = dataTables["StaffList"];
    DataTable planFactTable = dataTables["Plan_Fact"];
```
## Krok 3: Przejrzyj rekordy i utwórz indywidualne prezentacje
```csharp
foreach (DataRow userRow in usersTable.Rows)
{
    // utwórz nazwę prezentacji wyników (indywidualnej)
    string presPath = Path.Combine(resultPath, "PresFor_" + userRow["Name"] + ".pptx");
    // Załaduj szablon prezentacji
    using (Presentation pres = new Presentation(presTemplatePath))
    {
        // Wypełnij pola tekstowe danymi z tabeli głównej
        ((AutoShape)pres.Slides[0].Shapes[0]).TextFrame.Text = "Chief of the department - " + userRow["Name"];
        ((AutoShape)pres.Slides[0].Shapes[4]).TextFrame.Text = userRow["Department"].ToString();
        // Pobierz obraz z bazy danych
        byte[] bytes = Convert.FromBase64String(userRow["Img"].ToString());
        // Wstaw obraz do ramki prezentacji
        IPPImage image = pres.Images.AddImage(bytes);
        IPictureFrame pf = pres.Slides[0].Shapes[1] as PictureFrame;
        pf.PictureFormat.Picture.Image.ReplaceImage(image);
        // Pobierz i przygotuj ramkę tekstową, aby wypełnić ją danymi
        IAutoShape list = pres.Slides[0].Shapes[2] as IAutoShape;
        ITextFrame textFrame = list.TextFrame;
        textFrame.Paragraphs.Clear();
        Paragraph para = new Paragraph();
        para.Text = "Department Staff:";
        textFrame.Paragraphs.Add(para);
        // Wypełnij dane personelu
        FillStaffList(textFrame, userRow, staffListTable);
        // Wypełnij plan danymi faktycznymi
        FillPlanFact(pres, userRow, planFactTable);
        pres.Save(presPath, SaveFormat.Pptx);
    }
}
```
## Krok 4: Wypełnij ramkę tekstową danymi w postaci listy
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
## Krok 5: Wypełnij tabelę danych z tabeli faktów planu wtórnego
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
    // Dodaj punkty danych dla serii liniowych
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
Te kroki przedstawiają kompleksowy przewodnik dotyczący wykonywania korespondencji seryjnej w prezentacjach przy użyciu Aspose.Slides dla .NET. Teraz omówmy kilka często zadawanych pytań.
## Często zadawane pytania
### 1. Czy Aspose.Slides dla .NET jest kompatybilny z różnymi źródłami danych?
Tak, Aspose.Slides dla .NET obsługuje różne źródła danych, w tym XML, RDBMS i inne.
### 2. Czy mogę dostosować wygląd punktów wypunktowanych w wygenerowanej prezentacji?
Oczywiście! Masz pełną kontrolę nad wyglądem punktów wypunktowania, jak pokazano w `FillStaffList` metoda.
### 3. Jakie typy wykresów mogę tworzyć za pomocą Aspose.Slides dla .NET?
Aspose.Slides dla platformy .NET obsługuje szeroką gamę wykresów, w tym wykresy liniowe (jak w naszym przykładzie), wykresy słupkowe, wykresy kołowe i inne.
### 4. Jak uzyskać pomoc lub wsparcie dotyczące Aspose.Slides dla platformy .NET?
Aby uzyskać wsparcie i pomoc, możesz odwiedzić stronę [Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### 5. Czy mogę wypróbować Aspose.Slides dla .NET przed zakupem?
Oczywiście! Możesz skorzystać z bezpłatnej wersji próbnej Aspose.Slides dla .NET z [Tutaj](https://releases.aspose.com/).
## Wniosek
tym samouczku zbadaliśmy ekscytujące możliwości Aspose.Slides dla .NET w zakresie wykonywania korespondencji seryjnej w prezentacjach. Postępując zgodnie z przewodnikiem krok po kroku, możesz bez wysiłku tworzyć dynamiczne i spersonalizowane prezentacje. Podnieś poziom swojego doświadczenia w zakresie tworzenia .NET dzięki Aspose.Slides, aby bezproblemowo generować prezentacje.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}