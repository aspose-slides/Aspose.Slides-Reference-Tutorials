---
title: Effectuer un publipostage dans des présentations
linktitle: Effectuer un publipostage dans des présentations
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez comment effectuer un publipostage dans des présentations à l'aide d'Aspose.Slides pour .NET dans ce guide complet étape par étape. Créez facilement des présentations personnalisées et dynamiques.
type: docs
weight: 21
url: /fr/net/presentation-manipulation/perform-mail-merge-in-presentations/
---

Dans le domaine du développement de logiciels, la création de présentations dynamiques et personnalisées est une exigence courante. Les entreprises ont souvent besoin de générer des présentations adaptées à des données spécifiques, et c'est là que la fonctionnalité de publipostage entre en jeu. Dans ce didacticiel, nous vous guiderons tout au long du processus de fusion et de publipostage dans des présentations à l'aide d'Aspose.Slides pour .NET.

## Introduction

Le publipostage est une technique puissante qui vous permet de remplir des modèles de présentation avec des données provenant de diverses sources, telles que des bases de données ou des fichiers XML. Dans ce didacticiel, nous nous concentrerons sur l'utilisation d'Aspose.Slides pour .NET pour effectuer un publipostage dans des présentations, étape par étape.

## Configuration de votre environnement

Avant de plonger dans le processus de fusion et de publipostage, vous devez configurer votre environnement de développement. Assurez-vous d'avoir les conditions préalables suivantes en place :

- Visual Studio ou tout autre environnement de développement C#.
-  Aspose.Slides pour la bibliothèque .NET installée. Vous pouvez le télécharger[ici](https://releases.aspose.com/slides/net/).

## Comprendre la source de données

Pour le publipostage, vous aurez besoin d’une source de données. Dans ce didacticiel, nous utiliserons un fichier XML comme source de données. Voici un exemple de ce à quoi pourrait ressembler votre source de données :

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

## Création du modèle de présentation

Pour effectuer un publipostage, vous aurez besoin d'un modèle de présentation (fichier PPTX) qui définit la mise en page de vos présentations finales. Vous pouvez créer ce modèle à l'aide de Microsoft PowerPoint ou de tout autre outil de votre choix.

## Processus de fusion et de publipostage

Passons maintenant au processus de fusion de courrier réel à l'aide d'Aspose.Slides pour .NET. Nous allons le décomposer en étapes :

1. Chargez le modèle de présentation.
2. Remplissez les zones de texte avec les données de la source de données.
3. Insérez des images dans la présentation.
4. Préparez et remplissez les blocs de texte.
5. Enregistrez les présentations individuelles.

Voici un extrait de code C# qui accomplit ces étapes :

```csharp
string presTemplatePath = Path.Combine(dataDir, "PresentationTemplate.pptx");
    string resultPath = Path.Combine(RunExamples.OutPath, "MailMergeResult");

    // Chemin d'accès aux données.
    // Les données XML sont l'un des exemples de sources de données MailMerge possibles (parmi les SGBDR et autres types de sources de données).
    string dataPath = Path.Combine(dataDir, "TestData.xml");

    // Vérifiez si le chemin du résultat existe
    if (!Directory.Exists(resultPath))
        Directory.CreateDirectory(resultPath);

    // Création d'un DataSet à l'aide de données XML
    using (DataSet dataSet = new DataSet())
    {
        dataSet.ReadXml(dataPath);

        DataTableCollection dataTables = dataSet.Tables;
        DataTable usersTable = dataTables["TestTable"];
        DataTable staffListTable = dataTables["StaffList"];
        DataTable planFactTable = dataTables["Plan_Fact"];

        // Pour tous les enregistrements de la table principale, nous créerons une présentation distincte
        foreach (DataRow userRow in usersTable.Rows)
        {
            // créer le nom de la présentation du résultat (individuel)
            string presPath = Path.Combine(resultPath, "PresFor_" + userRow["Name"] + ".pptx");

            //Charger le modèle de présentation
            using (Presentation pres = new Presentation(presTemplatePath))
            {
                // Remplissez les zones de texte avec les données de la table principale de la base de données
                ((AutoShape)pres.Slides[0].Shapes[0]).TextFrame.Text =
                    "Chief of the department - " + userRow["Name"];
                ((AutoShape)pres.Slides[0].Shapes[4]).TextFrame.Text = userRow["Department"].ToString();

                // Récupérer l'image de la base de données
                byte[] bytes = Convert.FromBase64String(userRow["Img"].ToString());

                // insérer l'image dans le cadre photo de la présentation
                IPPImage image = pres.Images.AddImage(bytes);
                IPictureFrame pf = pres.Slides[0].Shapes[1] as PictureFrame;
                pf.PictureFormat.Picture.Image.ReplaceImage(image);

                // Obtenez et préparez le cadre de texte pour le remplir avec des données
                IAutoShape list = pres.Slides[0].Shapes[2] as IAutoShape;
                ITextFrame textFrame = list.TextFrame;

                textFrame.Paragraphs.Clear();
                Paragraph para = new Paragraph();
                para.Text = "Department Staff:";
                textFrame.Paragraphs.Add(para);

                // remplir les données du personnel
                FillStaffList(textFrame, userRow, staffListTable);

                // remplir les données de fait du plan
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

// Remplit le graphique de données de la table planFact secondaire
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

## Sauvegarde du résultat

Une fois que vous avez terminé le processus de fusion et de publipostage pour tous les enregistrements de votre source de données, vous disposerez de présentations individuelles prêtes. Vous pouvez les enregistrer à l'emplacement souhaité.

## Conclusion

Effectuer un publipostage dans des présentations à l'aide d'Aspose.Slides pour .NET ouvre un monde de possibilités pour créer des présentations personnalisées et basées sur les données. Ce tutoriel vous a guidé à travers les étapes essentielles pour y parvenir en toute transparence.

## FAQ

**Q1: Is Aspose.Slides for .NET the only library for mail merge in presentations?**
A1 : Bien qu'Aspose.Slides pour .NET soit un choix puissant, d'autres bibliothèques et outils offrent également des fonctionnalités similaires. En fin de compte, cela dépend de vos besoins et préférences spécifiques.

**Q2: Can I use different data sources apart from XML files?**
A2 : Oui, Aspose.Slides pour .NET prend en charge diverses sources de données, notamment des bases de données et des structures de données personnalisées.

**Q3: How can I format the merged presentations further?**
A3 : Vous pouvez appliquer une mise en forme, des styles et des animations supplémentaires aux présentations fusionnées à l'aide du riche ensemble de fonctionnalités d'Aspose.Slides.

**Q4: Is there a trial version of Aspose.Slides for .NET available?**
 A4 : Oui, vous pouvez bénéficier d'un essai gratuit d'Aspose.Slides pour .NET[ici](https://releases.aspose.com/).

**Q5: Where can I get support for Aspose.Slides for .NET?**
 A5 : Pour une assistance technique et des discussions, vous pouvez visiter le[Forum Aspose.Slides](https://forum.aspose.com/).

Maintenant que vous avez appris à effectuer un publipostage dans des présentations avec Aspose.Slides pour .NET, vous pouvez commencer à créer des présentations dynamiques et riches en données pour vos projets. Bon codage !
