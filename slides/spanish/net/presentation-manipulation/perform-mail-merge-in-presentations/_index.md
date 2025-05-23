---
"description": "Aprenda a combinar correspondencia en presentaciones con Aspose.Slides para .NET con esta guía paso a paso. Cree presentaciones dinámicas y personalizadas sin esfuerzo."
"linktitle": "Realizar la combinación de correspondencia en presentaciones"
"second_title": "API de procesamiento de PowerPoint Aspose.Slides .NET"
"title": "Realizar la combinación de correspondencia en presentaciones"
"url": "/es/net/presentation-manipulation/perform-mail-merge-in-presentations/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Realizar la combinación de correspondencia en presentaciones

## Introducción
En el mundo del desarrollo .NET, crear presentaciones dinámicas y personalizadas es un requisito común. Una herramienta potente que simplifica este proceso es Aspose.Slides para .NET. En este tutorial, profundizaremos en el fascinante mundo de la combinación de correspondencia en presentaciones con Aspose.Slides para .NET.
## Prerrequisitos
Antes de embarcarnos en este viaje, asegúrese de tener los siguientes requisitos previos:
- Biblioteca Aspose.Slides para .NET: Asegúrate de tener instalada la biblioteca Aspose.Slides para .NET. Puedes descargarla desde [aquí](https://releases.aspose.com/slides/net/).
- Plantilla de documento: prepare una plantilla de presentación (por ejemplo, PresentationTemplate.pptx) que servirá como base para la combinación de correspondencia.
- Fuente de datos: Necesita una fuente de datos para la combinación de correspondencia. En nuestro ejemplo, usaremos datos XML (TestData.xml), pero Aspose.Slides admite diversas fuentes de datos, como RDBMS.
Ahora, profundicemos en los pasos para realizar la combinación de correspondencia en presentaciones usando Aspose.Slides para .NET.
## Importar espacios de nombres
En primer lugar, asegúrese de importar los espacios de nombres necesarios para aprovechar las funcionalidades proporcionadas por Aspose.Slides:
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
## Paso 1: Configure su directorio de documentos
```csharp
string dataDir = "Your Document Directory";
string presTemplatePath = Path.Combine(dataDir, "PresentationTemplate.pptx");
string resultPath = Path.Combine(RunExamples.OutPath, "MailMergeResult");
// Comprobar si existe la ruta del resultado
if (!Directory.Exists(resultPath))
    Directory.CreateDirectory(resultPath);
```
## Paso 2: Crear un conjunto de datos utilizando datos XML
```csharp
using (DataSet dataSet = new DataSet())
{
    dataSet.ReadXml(dataPath);
    DataTableCollection dataTables = dataSet.Tables;
    DataTable usersTable = dataTables["TestTable"];
    DataTable staffListTable = dataTables["StaffList"];
    DataTable planFactTable = dataTables["Plan_Fact"];
```
## Paso 3: Recorrer los registros y crear presentaciones individuales
```csharp
foreach (DataRow userRow in usersTable.Rows)
{
    // crear nombre de presentación de resultados (individual)
    string presPath = Path.Combine(resultPath, "PresFor_" + userRow["Name"] + ".pptx");
    // Cargar plantilla de presentación
    using (Presentation pres = new Presentation(presTemplatePath))
    {
        // Rellene los cuadros de texto con datos de la tabla principal
        ((AutoShape)pres.Slides[0].Shapes[0]).TextFrame.Text = "Chief of the department - " + userRow["Name"];
        ((AutoShape)pres.Slides[0].Shapes[4]).TextFrame.Text = userRow["Department"].ToString();
        // Obtener imagen de la base de datos
        byte[] bytes = Convert.FromBase64String(userRow["Img"].ToString());
        // Insertar imagen en el marco de la presentación
        IPPImage image = pres.Images.AddImage(bytes);
        IPictureFrame pf = pres.Slides[0].Shapes[1] as PictureFrame;
        pf.PictureFormat.Picture.Image.ReplaceImage(image);
        // Obtener y preparar el marco de texto para llenarlo con datos
        IAutoShape list = pres.Slides[0].Shapes[2] as IAutoShape;
        ITextFrame textFrame = list.TextFrame;
        textFrame.Paragraphs.Clear();
        Paragraph para = new Paragraph();
        para.Text = "Department Staff:";
        textFrame.Paragraphs.Add(para);
        // Completar datos del personal
        FillStaffList(textFrame, userRow, staffListTable);
        // Completar los datos de hechos del plan
        FillPlanFact(pres, userRow, planFactTable);
        pres.Save(presPath, SaveFormat.Pptx);
    }
}
```
## Paso 4: Llene el marco de texto con datos como una lista
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
## Paso 5: Complete el cuadro de datos de la tabla secundaria PlanFact
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
    // Agregar puntos de datos para series de líneas
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
Estos pasos ofrecen una guía completa sobre cómo combinar correspondencia en presentaciones con Aspose.Slides para .NET. A continuación, responderemos algunas preguntas frecuentes.
## Preguntas frecuentes
### 1. ¿Aspose.Slides para .NET es compatible con diferentes fuentes de datos?
Sí, Aspose.Slides para .NET admite varias fuentes de datos, incluidos XML, RDBMS y más.
### 2. ¿Puedo personalizar la apariencia de las viñetas en la presentación generada?
¡Por supuesto! Tienes control total sobre la apariencia de las viñetas, como se muestra en el `FillStaffList` método.
### 3. ¿Qué tipos de gráficos puedo crear usando Aspose.Slides para .NET?
Aspose.Slides para .NET admite una amplia gama de gráficos, incluidos gráficos de líneas como se muestra en nuestro ejemplo, gráficos de barras, gráficos circulares y más.
### 4. ¿Cómo puedo obtener soporte o solicitar asistencia con Aspose.Slides para .NET?
Para obtener ayuda y asistencia, puede visitar el [Foro de Aspose.Slides](https://forum.aspose.com/c/slides/11).
### 5. ¿Puedo probar Aspose.Slides para .NET antes de comprarlo?
¡Por supuesto! Puedes obtener una prueba gratuita de Aspose.Slides para .NET desde [aquí](https://releases.aspose.com/).
## Conclusión
En este tutorial, exploramos las interesantes funciones de Aspose.Slides para .NET para combinar correspondencia en presentaciones. Siguiendo la guía paso a paso, podrá crear presentaciones dinámicas y personalizadas sin esfuerzo. Mejore su experiencia de desarrollo .NET con Aspose.Slides para una generación de presentaciones fluida.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}