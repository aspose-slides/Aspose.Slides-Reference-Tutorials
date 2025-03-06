---
title: Executar mala direta em apresentações
linktitle: Executar mala direta em apresentações
second_title: API de processamento de PowerPoint Aspose.Slides .NET
description: Aprenda mala direta em apresentações usando Aspose.Slides for .NET neste guia passo a passo. Crie apresentações dinâmicas e personalizadas sem esforço.
weight: 21
url: /pt/net/presentation-manipulation/perform-mail-merge-in-presentations/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introdução
No mundo do desenvolvimento .NET, a criação de apresentações dinâmicas e personalizadas é um requisito comum. Uma ferramenta poderosa que simplifica esse processo é o Aspose.Slides for .NET. Neste tutorial, nos aprofundaremos no fascinante reino de realizar mala direta em apresentações usando Aspose.Slides for .NET.
## Pré-requisitos
Antes de embarcarmos nesta jornada, certifique-se de ter os seguintes pré-requisitos em vigor:
- Biblioteca Aspose.Slides for .NET: Certifique-se de ter a biblioteca Aspose.Slides for .NET instalada. Você pode baixá-lo em[aqui](https://releases.aspose.com/slides/net/).
- Modelo de documento: Prepare um modelo de apresentação (por exemplo, PresentationTemplate.pptx) que servirá como base para mala direta.
- Fonte de dados: você precisa de uma fonte de dados para mala direta. Em nosso exemplo, usaremos dados XML (TestData.xml), mas Aspose.Slides suporta várias fontes de dados como RDBMS.
Agora, vamos mergulhar nas etapas de execução de mala direta em apresentações usando Aspose.Slides for .NET.
## Importar namespaces
Em primeiro lugar, certifique-se de importar os namespaces necessários para aproveitar as funcionalidades fornecidas pelo Aspose.Slides:
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
## Etapa 1: configure seu diretório de documentos
```csharp
string dataDir = "Your Document Directory";
string presTemplatePath = Path.Combine(dataDir, "PresentationTemplate.pptx");
string resultPath = Path.Combine(RunExamples.OutPath, "MailMergeResult");
// Verifique se o caminho do resultado existe
if (!Directory.Exists(resultPath))
    Directory.CreateDirectory(resultPath);
```
## Etapa 2: Criar um DataSet usando dados XML
```csharp
using (DataSet dataSet = new DataSet())
{
    dataSet.ReadXml(dataPath);
    DataTableCollection dataTables = dataSet.Tables;
    DataTable usersTable = dataTables["TestTable"];
    DataTable staffListTable = dataTables["StaffList"];
    DataTable planFactTable = dataTables["Plan_Fact"];
```
## Etapa 3: percorrer os registros e criar apresentações individuais
```csharp
foreach (DataRow userRow in usersTable.Rows)
{
    // criar nome da apresentação do resultado (individual)
    string presPath = Path.Combine(resultPath, "PresFor_" + userRow["Name"] + ".pptx");
    // Carregar modelo de apresentação
    using (Presentation pres = new Presentation(presTemplatePath))
    {
        // Preencha as caixas de texto com dados da tabela principal
        ((AutoShape)pres.Slides[0].Shapes[0]).TextFrame.Text = "Chief of the department - " + userRow["Name"];
        ((AutoShape)pres.Slides[0].Shapes[4]).TextFrame.Text = userRow["Department"].ToString();
        // Obtenha imagem do banco de dados
        byte[] bytes = Convert.FromBase64String(userRow["Img"].ToString());
        //Insira a imagem no porta-retratos da apresentação
        IPPImage image = pres.Images.AddImage(bytes);
        IPictureFrame pf = pres.Slides[0].Shapes[1] as PictureFrame;
        pf.PictureFormat.Picture.Image.ReplaceImage(image);
        // Obtenha e prepare o quadro de texto para preenchê-lo com dados
        IAutoShape list = pres.Slides[0].Shapes[2] as IAutoShape;
        ITextFrame textFrame = list.TextFrame;
        textFrame.Paragraphs.Clear();
        Paragraph para = new Paragraph();
        para.Text = "Department Staff:";
        textFrame.Paragraphs.Add(para);
        // Preencha os dados da equipe
        FillStaffList(textFrame, userRow, staffListTable);
        // Preencha os dados factuais do plano
        FillPlanFact(pres, userRow, planFactTable);
        pres.Save(presPath, SaveFormat.Pptx);
    }
}
```
## Etapa 4: preencher o quadro de texto com dados como uma lista
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
## Etapa 5: preencher o gráfico de dados da tabela PlanFact secundária
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
    // Adicionar pontos de dados para séries de linhas
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
Estas etapas demonstram um guia abrangente sobre como realizar mala direta em apresentações usando Aspose.Slides for .NET. Agora, vamos responder a algumas perguntas frequentes.
## perguntas frequentes
### 1. O Aspose.Slides for .NET é compatível com diferentes fontes de dados?
Sim, Aspose.Slides for .NET oferece suporte a várias fontes de dados, incluindo XML, RDBMS e muito mais.
### 2. Posso personalizar a aparência dos marcadores na apresentação gerada?
 Certamente! Você tem controle total sobre a aparência dos marcadores, conforme demonstrado no`FillStaffList` método.
### 3. Que tipos de gráficos posso criar usando Aspose.Slides for .NET?
Aspose.Slides for .NET oferece suporte a uma ampla variedade de gráficos, incluindo gráficos de linhas conforme mostrado em nosso exemplo, gráficos de barras, gráficos de pizza e muito mais.
### 4. Como obtenho suporte ou assistência com Aspose.Slides for .NET?
 Para suporte e assistência, você pode visitar o[Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### 5. Posso experimentar o Aspose.Slides for .NET antes de comprar?
 Certamente! Você pode aproveitar uma avaliação gratuita do Aspose.Slides for .NET em[aqui](https://releases.aspose.com/).
## Conclusão
Neste tutorial, exploramos os recursos interessantes do Aspose.Slides for .NET na realização de mala direta em apresentações. Seguindo o guia passo a passo, você pode criar apresentações dinâmicas e personalizadas sem esforço. Eleve sua experiência de desenvolvimento .NET com Aspose.Slides para geração de apresentações perfeita.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
