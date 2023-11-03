---
title: Realizar combinación de correspondencia en presentaciones
linktitle: Realizar combinación de correspondencia en presentaciones
second_title: Aspose.Slides API de procesamiento de PowerPoint .NET
description: Aprenda a realizar combinación de correspondencia en presentaciones usando Aspose.Slides para .NET en esta guía completa paso a paso. Crea presentaciones personalizadas y dinámicas con facilidad.
type: docs
weight: 21
url: /es/net/presentation-manipulation/perform-mail-merge-in-presentations/
---

En el ámbito del desarrollo de software, la creación de presentaciones dinámicas y personalizadas es un requisito común. Las empresas a menudo necesitan generar presentaciones adaptadas a datos específicos, y aquí es donde entra en juego la funcionalidad de combinación de correspondencia. En este tutorial, lo guiaremos a través del proceso de realizar combinación de correspondencia en presentaciones usando Aspose.Slides para .NET.

## Introducción

La combinación de correspondencia es una técnica poderosa que le permite completar plantillas de presentación con datos de diversas fuentes, como bases de datos o archivos XML. En este tutorial, nos centraremos en el uso de Aspose.Slides para .NET para realizar combinación de correspondencia en presentaciones paso a paso.

## Configurando su entorno

Antes de sumergirnos en el proceso de combinación de correspondencia, debe configurar su entorno de desarrollo. Asegúrese de cumplir los siguientes requisitos previos:

- Visual Studio o cualquier otro entorno de desarrollo C#.
-  Aspose.Slides para la biblioteca .NET instalada. Puedes descargarlo[aquí](https://releases.aspose.com/slides/net/).

## Comprender la fuente de datos

Para combinar correspondencia, necesitará una fuente de datos. En este tutorial, usaremos un archivo XML como nuestra fuente de datos. A continuación se muestra un ejemplo de cómo podría verse su fuente de datos:

```xml
<!-- TestData.xml -->
<?xml version="1.0" encoding="UTF-8"?>
<MailMerge>
    <TestTable>
        <Id>1</Id>
        <Code>105</Code>
        <Name>Samuel Ellington</Name>
        <Department>Legal Department</Department> <Img></Img>
    </TestTable>
    <StaffList>
        <Id>18</Id>
        <UserId>1</UserId>
        <Name>Amelia Walker</Name>
    </StaffList>
    <Plan_Fact>
        <Id>1</Id>
        <UserId>1</UserId>
        <OnDate>2020/01</OnDate>
        <PlanData>2,0</PlanData>
        <FactData>2,8</FactData>
    </Plan_Fact>
</MailMerge>
```

## Creando la plantilla de presentación

Para realizar una combinación de correspondencia, necesitará una plantilla de presentación (archivo PPTX) que defina el diseño de sus presentaciones finales. Puede crear esta plantilla usando Microsoft PowerPoint o cualquier otra herramienta de su elección.

## Proceso de combinación de correo

Ahora, profundicemos en el proceso de combinación de correo real usando Aspose.Slides para .NET. Lo dividiremos en pasos:

1. Cargue la plantilla de presentación.
2. Llene los cuadros de texto con datos de la fuente de datos.
3. Insertar imágenes en la presentación.
4. Preparar y rellenar marcos de texto.
5. Guarde las presentaciones individuales.

Aquí hay un fragmento de código C# que realiza estos pasos:

```csharp
string presTemplatePath = Path.Combine(dataDir, "PresentationTemplate.pptx");
    string resultPath = Path.Combine(RunExamples.OutPath, "MailMergeResult");

    // Camino a los datos.
    // Los datos XML son uno de los ejemplos de posibles fuentes de datos de MailMerge (entre RDBMS y otros tipos de fuentes de datos).
    string dataPath = Path.Combine(dataDir, "TestData.xml");

    // Comprobar si existe la ruta del resultado
    if (!Directory.Exists(resultPath))
        Directory.CreateDirectory(resultPath);

    // Creando un conjunto de datos usando datos XML
    using (DataSet dataSet = new DataSet())
    {
        dataSet.ReadXml(dataPath);

        DataTableCollection dataTables = dataSet.Tables;
        DataTable usersTable = dataTables["TestTable"];
        DataTable staffListTable = dataTables["StaffList"];
        DataTable planFactTable = dataTables["Plan_Fact"];

        // Para todos los registros en la tabla principal crearemos una presentación separada
        foreach (DataRow userRow in usersTable.Rows)
        {
            // crear resultado (individual) nombre de presentación
            string presPath = Path.Combine(resultPath, "PresFor_" + userRow["Name"] + ".pptx");

            // Cargar plantilla de presentación
            using (Presentation pres = new Presentation(presTemplatePath))
            {
                // Llene cuadros de texto con datos de la tabla principal de la base de datos
                ((AutoShape)pres.Slides[0].Shapes[0]).TextFrame.Text =
                    "Chief of the department - " + userRow["Name"];
                ((AutoShape)pres.Slides[0].Shapes[4]).TextFrame.Text = userRow["Department"].ToString();

                // Obtener imagen de la base de datos
                byte[] bytes = Convert.FromBase64String(userRow["Img"].ToString());

                // insertar imagen en el marco de la presentación
                IPPImage image = pres.Images.AddImage(bytes);
                IPictureFrame pf = pres.Slides[0].Shapes[1] as PictureFrame;
                pf.PictureFormat.Picture.Image.ReplaceImage(image);

                // Obtenga y prepare el marco de texto para llenarlo con datos
                IAutoShape list = pres.Slides[0].Shapes[2] as IAutoShape;
                ITextFrame textFrame = list.TextFrame;

                textFrame.Paragraphs.Clear();
                Paragraph para = new Paragraph();
                para.Text = "Department Staff:";
                textFrame.Paragraphs.Add(para);

                // llenar datos del personal
                FillStaffList(textFrame, userRow, staffListTable);

                // llenar datos de hechos del plan
                FillPlanFact(pres, userRow, planFactTable);

                pres.Save(presPath, SaveFormat.Pptx);
            }
        }
    }

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

// Llena el gráfico de datos de la tabla de hechos del plan secundario
static void FillPlanFact(Presentation pres, DataRow row, DataTable planFactTable)
{
    IChart chart = pres.Slides[0].Shapes[3] as Chart;
    IChartTitle chartTitle = chart.ChartTitle;
    chartTitle.TextFrameForOverriding.Text = row["Name"] + " : Plan / Fact";

    DataRow[] selRows = planFactTable.Select("UserId = " + row["Id"]);
    string range = chart.ChartData.GetRange();

    IChartDataWorkbook cellsFactory = chart.ChartData.ChartDataWorkbook;
    int worksheetIndex = 0;

    chart.ChartData.Series[0].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 1, 1,
            double.Parse(selRows[0]["PlanData"].ToString())));
    chart.ChartData.Series[1].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 1, 2,
            double.Parse(selRows[0]["FactData"].ToString())));

    chart.ChartData.Series[0].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 2, 1,
            double.Parse(selRows[1]["PlanData"].ToString())));
    chart.ChartData.Series[1].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 2, 2,
            double.Parse(selRows[1]["FactData"].ToString())));

    chart.ChartData.Series[0].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 3, 1,
            double.Parse(selRows[2]["PlanData"].ToString())));
    chart.ChartData.Series[1].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 3, 2,
            double.Parse(selRows[2]["FactData"].ToString())));

    chart.ChartData.Series[0].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 3, 1,
            double.Parse(selRows[3]["PlanData"].ToString())));
    chart.ChartData.Series[1].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 3, 2,
            double.Parse(selRows[3]["FactData"].ToString())));

    chart.ChartData.SetRange(range);
}		
```

## Guardar el resultado

Una vez que haya completado el proceso de combinación de correspondencia para todos los registros en su fuente de datos, tendrá presentaciones individuales listas. Puede guardarlos en la ubicación que desee.

## Conclusión

Realizar combinación de correspondencia en presentaciones usando Aspose.Slides para .NET abre un mundo de posibilidades para crear presentaciones personalizadas y basadas en datos. Este tutorial lo ha guiado a través de los pasos esenciales para lograrlo sin problemas.

## Preguntas frecuentes

**Q1: Is Aspose.Slides for .NET the only library for mail merge in presentations?**
R1: Si bien Aspose.Slides para .NET es una opción poderosa, otras bibliotecas y herramientas también ofrecen una funcionalidad similar. En última instancia, depende de sus requisitos y preferencias específicos.

**Q2: Can I use different data sources apart from XML files?**
R2: Sí, Aspose.Slides para .NET admite varias fuentes de datos, incluidas bases de datos y estructuras de datos personalizadas.

**Q3: How can I format the merged presentations further?**
R3: Puede aplicar formatos, estilos y animaciones adicionales a las presentaciones fusionadas utilizando el rico conjunto de funciones de Aspose.Slides.

**Q4: Is there a trial version of Aspose.Slides for .NET available?**
 R4: Sí, puede obtener una prueba gratuita de Aspose.Slides para .NET[aquí](https://releases.aspose.com/).

**Q5: Where can I get support for Aspose.Slides for .NET?**
 R5: Para soporte técnico y discusiones, puede visitar el[Foro Aspose.Slides](https://forum.aspose.com/).

Ahora que ha aprendido cómo realizar combinación de correspondencia en presentaciones con Aspose.Slides para .NET, puede comenzar a crear presentaciones dinámicas y ricas en datos para sus proyectos. ¡Feliz codificación!
