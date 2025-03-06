---
title: Wykonywanie korespondencji seryjnej w prezentacjach
linktitle: Wykonywanie korespondencji seryjnej w prezentacjach
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Naucz się korespondencji seryjnej w prezentacjach przy użyciu Aspose.Slides dla .NET w tym przewodniku krok po kroku. Twórz dynamiczne, spersonalizowane prezentacje bez wysiłku.
weight: 21
url: /pl/net/presentation-manipulation/perform-mail-merge-in-presentations/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Wstęp
W świecie programowania .NET tworzenie dynamicznych i spersonalizowanych prezentacji jest powszechnym wymogiem. Jednym z potężnych narzędzi, które upraszcza ten proces, jest Aspose.Slides dla .NET. W tym samouczku zagłębimy się w fascynującą dziedzinę korespondencji seryjnej w prezentacjach przy użyciu Aspose.Slides dla .NET.
## Warunki wstępne
Zanim wyruszymy w tę podróż, upewnijmy się, że spełniamy następujące warunki wstępne:
- Biblioteka Aspose.Slides dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.Slides dla .NET. Można go pobrać z[Tutaj](https://releases.aspose.com/slides/net/).
- Szablon dokumentu: Przygotuj szablon prezentacji (np. PrezentacjaTemplate.pptx), który będzie podstawą korespondencji seryjnej.
- Źródło danych: do korespondencji seryjnej potrzebne jest źródło danych. W naszym przykładzie użyjemy danych XML (TestData.xml), ale Aspose.Slides obsługuje różne źródła danych, takie jak RDBMS.
Teraz przyjrzyjmy się etapom wykonywania korespondencji seryjnej w prezentacjach przy użyciu Aspose.Slides dla .NET.
## Importuj przestrzenie nazw
Po pierwsze, upewnij się, że zaimportowałeś niezbędne przestrzenie nazw, aby wykorzystać funkcje zapewniane przez Aspose.Slides:
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
// Sprawdź, czy ścieżka wyniku istnieje
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
## Krok 3: Przeglądaj rekordy w pętli i twórz indywidualne prezentacje
```csharp
foreach (DataRow userRow in usersTable.Rows)
{
    // utwórz nazwę prezentacji wynikowej (indywidualnej).
    string presPath = Path.Combine(resultPath, "PresFor_" + userRow["Name"] + ".pptx");
    // Załaduj szablon prezentacji
    using (Presentation pres = new Presentation(presTemplatePath))
    {
        // Wypełnij pola tekstowe danymi z tabeli głównej
        ((AutoShape)pres.Slides[0].Shapes[0]).TextFrame.Text = "Chief of the department - " + userRow["Name"];
        ((AutoShape)pres.Slides[0].Shapes[4]).TextFrame.Text = userRow["Department"].ToString();
        // Pobierz obraz z bazy danych
        byte[] bytes = Convert.FromBase64String(userRow["Img"].ToString());
        //Wstaw obraz do ramki obrazu prezentacji
        IPPImage image = pres.Images.AddImage(bytes);
        IPictureFrame pf = pres.Slides[0].Shapes[1] as PictureFrame;
        pf.PictureFormat.Picture.Image.ReplaceImage(image);
        // Pobierz i przygotuj ramkę tekstową do wypełnienia jej danymi
        IAutoShape list = pres.Slides[0].Shapes[2] as IAutoShape;
        ITextFrame textFrame = list.TextFrame;
        textFrame.Paragraphs.Clear();
        Paragraph para = new Paragraph();
        para.Text = "Department Staff:";
        textFrame.Paragraphs.Add(para);
        // Wypełnij dane personelu
        FillStaffList(textFrame, userRow, staffListTable);
        // Wypełnij dane faktów planu
        FillPlanFact(pres, userRow, planFactTable);
        pres.Save(presPath, SaveFormat.Pptx);
    }
}
```
## Krok 4: Wypełnij ramkę tekstową danymi w formie listy
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
## Krok 5: Wypełnij wykres danych z dodatkowej tabeli PlanFact
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
    // Dodaj punkty danych dla serii linii
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
Poniższe kroki przedstawiają kompleksowy przewodnik dotyczący wykonywania korespondencji seryjnej w prezentacjach przy użyciu Aspose.Slides dla .NET. Zajmijmy się teraz kilkoma często zadawanymi pytaniami.
## Często Zadawane Pytania
### 1. Czy Aspose.Slides for .NET jest kompatybilny z różnymi źródłami danych?
Tak, Aspose.Slides dla .NET obsługuje różne źródła danych, w tym XML, RDBMS i inne.
### 2. Czy mogę dostosować wygląd wypunktowań w wygenerowanej prezentacji?
 Z pewnością! Masz pełną kontrolę nad wyglądem wypunktowań, jak pokazano w`FillStaffList` metoda.
### 3. Jakie typy wykresów mogę tworzyć za pomocą Aspose.Slides dla .NET?
Aspose.Slides dla .NET obsługuje szeroką gamę wykresów, w tym wykresy liniowe, jak pokazano w naszym przykładzie, wykresy słupkowe, wykresy kołowe i inne.
### 4. Jak uzyskać pomoc lub poprosić o pomoc dotyczącą Aspose.Slides dla .NET?
 Aby uzyskać wsparcie i pomoc, możesz odwiedzić stronę[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### 5. Czy przed zakupem mogę wypróbować Aspose.Slides dla .NET?
 Z pewnością! Możesz skorzystać z bezpłatnej wersji próbnej Aspose.Slides dla .NET z[Tutaj](https://releases.aspose.com/).
## Wniosek
W tym samouczku zbadaliśmy ekscytujące możliwości Aspose.Slides dla .NET w wykonywaniu korespondencji seryjnej w prezentacjach. Postępując zgodnie ze szczegółowym przewodnikiem, możesz bez wysiłku tworzyć dynamiczne i spersonalizowane prezentacje. Podnieś swoje doświadczenie programistyczne .NET dzięki Aspose.Slides, aby płynnie generować prezentacje.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
