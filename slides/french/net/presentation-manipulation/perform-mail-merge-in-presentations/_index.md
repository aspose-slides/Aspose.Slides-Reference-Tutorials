---
"description": "Apprenez le publipostage dans vos présentations avec Aspose.Slides pour .NET grâce à ce guide étape par étape. Créez facilement des présentations dynamiques et personnalisées."
"linktitle": "Effectuer un publipostage dans les présentations"
"second_title": "API de traitement PowerPoint Aspose.Slides .NET"
"title": "Effectuer un publipostage dans les présentations"
"url": "/fr/net/presentation-manipulation/perform-mail-merge-in-presentations/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Effectuer un publipostage dans les présentations

## Introduction
Dans le monde du développement .NET, la création de présentations dynamiques et personnalisées est une nécessité courante. Aspose.Slides pour .NET est un outil puissant qui simplifie ce processus. Dans ce tutoriel, nous explorerons le monde fascinant du publipostage dans les présentations avec Aspose.Slides pour .NET.
## Prérequis
Avant de vous lancer dans ce voyage, assurez-vous de disposer des prérequis suivants :
- Bibliothèque Aspose.Slides pour .NET : Assurez-vous d'avoir installé la bibliothèque Aspose.Slides pour .NET. Vous pouvez la télécharger ici. [ici](https://releases.aspose.com/slides/net/).
- Modèle de document : préparez un modèle de présentation (par exemple, PresentationTemplate.pptx) qui servira de base pour le publipostage.
- Source de données : Vous avez besoin d'une source de données pour le publipostage. Dans notre exemple, nous utiliserons des données XML (TestData.xml), mais Aspose.Slides prend en charge diverses sources de données, comme les SGBDR.
Maintenant, plongeons dans les étapes de réalisation du publipostage dans les présentations à l’aide d’Aspose.Slides pour .NET.
## Importer des espaces de noms
Tout d’abord, assurez-vous d’importer les espaces de noms nécessaires pour tirer parti des fonctionnalités fournies par Aspose.Slides :
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
## Étape 1 : Configurez votre répertoire de documents
```csharp
string dataDir = "Your Document Directory";
string presTemplatePath = Path.Combine(dataDir, "PresentationTemplate.pptx");
string resultPath = Path.Combine(RunExamples.OutPath, "MailMergeResult");
// Vérifier si le chemin du résultat existe
if (!Directory.Exists(resultPath))
    Directory.CreateDirectory(resultPath);
```
## Étape 2 : Créer un ensemble de données à l'aide de données XML
```csharp
using (DataSet dataSet = new DataSet())
{
    dataSet.ReadXml(dataPath);
    DataTableCollection dataTables = dataSet.Tables;
    DataTable usersTable = dataTables["TestTable"];
    DataTable staffListTable = dataTables["StaffList"];
    DataTable planFactTable = dataTables["Plan_Fact"];
```
## Étape 3 : Parcourir les enregistrements et créer des présentations individuelles
```csharp
foreach (DataRow userRow in usersTable.Rows)
{
    // créer un nom de présentation de résultat (individuel)
    string presPath = Path.Combine(resultPath, "PresFor_" + userRow["Name"] + ".pptx");
    // Modèle de présentation de chargement
    using (Presentation pres = new Presentation(presTemplatePath))
    {
        // Remplissez les zones de texte avec les données du tableau principal
        ((AutoShape)pres.Slides[0].Shapes[0]).TextFrame.Text = "Chief of the department - " + userRow["Name"];
        ((AutoShape)pres.Slides[0].Shapes[4]).TextFrame.Text = userRow["Department"].ToString();
        // Obtenir l'image de la base de données
        byte[] bytes = Convert.FromBase64String(userRow["Img"].ToString());
        // Insérer une image dans le cadre photo de la présentation
        IPPImage image = pres.Images.AddImage(bytes);
        IPictureFrame pf = pres.Slides[0].Shapes[1] as PictureFrame;
        pf.PictureFormat.Picture.Image.ReplaceImage(image);
        // Obtenir et préparer le cadre de texte pour le remplir avec des données
        IAutoShape list = pres.Slides[0].Shapes[2] as IAutoShape;
        ITextFrame textFrame = list.TextFrame;
        textFrame.Paragraphs.Clear();
        Paragraph para = new Paragraph();
        para.Text = "Department Staff:";
        textFrame.Paragraphs.Add(para);
        // Remplir les données du personnel
        FillStaffList(textFrame, userRow, staffListTable);
        // Remplir les données factuelles du plan
        FillPlanFact(pres, userRow, planFactTable);
        pres.Save(presPath, SaveFormat.Pptx);
    }
}
```
## Étape 4 : Remplir le cadre de texte avec des données sous forme de liste
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
## Étape 5 : Remplir le graphique de données à partir de la table PlanFact secondaire
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
    // Ajouter des points de données pour les séries de lignes
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
Ces étapes présentent un guide complet sur la réalisation de publipostage dans des présentations avec Aspose.Slides pour .NET. Voyons maintenant quelques questions fréquemment posées.
## Questions fréquemment posées
### 1. Aspose.Slides pour .NET est-il compatible avec différentes sources de données ?
Oui, Aspose.Slides pour .NET prend en charge diverses sources de données, notamment XML, RDBMS, etc.
### 2. Puis-je personnaliser l’apparence des puces dans la présentation générée ?
Bien sûr ! Vous avez un contrôle total sur l'apparence des puces, comme le montre la `FillStaffList` méthode.
### 3. Quels types de graphiques puis-je créer à l’aide d’Aspose.Slides pour .NET ?
Aspose.Slides pour .NET prend en charge une large gamme de graphiques, notamment les graphiques linéaires comme illustré dans notre exemple, les graphiques à barres, les graphiques à secteurs, etc.
### 4. Comment puis-je obtenir de l'aide ou demander de l'aide avec Aspose.Slides pour .NET ?
Pour obtenir de l'aide et de l'assistance, vous pouvez visiter le [Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### 5. Puis-je essayer Aspose.Slides pour .NET avant de l'acheter ?
Bien sûr ! Vous pouvez bénéficier d'un essai gratuit d'Aspose.Slides pour .NET à partir de [ici](https://releases.aspose.com/).
## Conclusion
Dans ce tutoriel, nous avons exploré les fonctionnalités intéressantes d'Aspose.Slides pour .NET pour le publipostage dans les présentations. En suivant le guide étape par étape, vous pouvez créer facilement des présentations dynamiques et personnalisées. Améliorez votre expérience de développement .NET avec Aspose.Slides pour une génération de présentations fluide.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}