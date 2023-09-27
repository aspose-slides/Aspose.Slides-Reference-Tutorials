---
title: Entités du graphique et formatage
linktitle: Entités du graphique et formatage
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Apprenez à créer et formater des graphiques dynamiques dans PowerPoint à l'aide d'Aspose.Slides pour .NET. Guide étape par étape avec le code source.
type: docs
weight: 13
url: /fr/net/advanced-chart-customization/chart-entities/
---

## Introduction à Aspose.Slides et à la manipulation de graphiques

Aspose.Slides for .NET est une bibliothèque complète qui permet aux développeurs de créer, modifier et manipuler des présentations PowerPoint par programme. En ce qui concerne les graphiques, Aspose.Slides offre un large éventail de fonctionnalités pour ajouter, modifier et formater des graphiques dans les diapositives de présentation.

## Configuration de votre environnement de développement

 Pour commencer, assurez-vous de disposer d'un environnement de développement fonctionnel avec Aspose.Slides pour .NET installé. Vous pouvez télécharger la bibliothèque depuis[ici](https://releases.aspose.com/slides/net/).

## Ajout d'un graphique à une diapositive

Commençons par ajouter un graphique à une diapositive. Le code suivant montre comment créer une nouvelle présentation, ajouter une diapositive et y insérer un graphique :

```csharp
// Instancier un objet Présentation
Presentation presentation = new Presentation();

// Ajouter une diapositive
ISlide slide = presentation.Slides.AddEmptySlide();

//Ajouter un graphique à la diapositive
IChart chart = slide.Shapes.AddChart(ChartType.ClusteredColumn, 100, 100, 500, 300);
```

## Modification des données du graphique

Les graphiques ne sont rien sans données. Aspose.Slides vous permet de remplir facilement des graphiques avec des données. Voici comment modifier les données du graphique :

```csharp
// Accéder au classeur du graphique
IChartDataWorkbook workbook = chart.ChartData.ChartDataWorkbook;

// Accéder à la feuille de calcul du graphique
IChartDataWorksheet worksheet = workbook.Worksheets[0];

// Remplir les données du graphique
worksheet.Cells["A1"].Value = "Category";
worksheet.Cells["A2"].Value = "Apple";
worksheet.Cells["A3"].Value = "Banana";
// ...

worksheet.Cells["B1"].Value = "Value";
worksheet.Cells["B2"].Value = 25;
worksheet.Cells["B3"].Value = 40;
// ...
```

## Personnalisation de l'apparence du graphique

Le formatage d'un graphique améliore son attrait visuel. Explorons comment formater différents aspects d'un graphique :

## Formatage du titre et des axes du graphique

Vous pouvez formater le titre et les axes du graphique à l'aide du code suivant :

```csharp
chart.HasTitle = true;
chart.ChartTitle.TextFrame.Text = "Sales Report";

chart.Axes.HorizontalAxis.Title.TextFrame.Text = "Fruits";
chart.Axes.VerticalAxis.Title.TextFrame.Text = "Quantity";
```

## Application de styles de graphique

Appliquez des styles de graphique prédéfinis pour rendre votre graphique plus attrayant :

```csharp
chart.ChartStyle = ChartStylePreset.Style2;
```

## Ajustement des étiquettes de données

Les étiquettes de données fournissent un contexte au graphique. Modifiez-les comme ceci :

```csharp
IDataLabel label = chart.Series[0].DataPoints[0].Label;
label.ShowValue = true;
label.DataLabelFormat.TextFormat.PortionFormat.FontBold = NullableBool.True;
```

## Travailler avec des éléments de graphique

La gestion des éléments du graphique améliore votre contrôle sur la représentation visuelle du graphique. Explorons quelques techniques :

## Gestion des séries de données

Vous pouvez ajouter, supprimer et manipuler des séries de données comme ceci :

```csharp
IChartSeries series = chart.ChartData.Series.Add(worksheet.Cells, "A2:A3", "B2:B3");
```

## Gestion des légendes des graphiques

Les légendes fournissent des informations essentielles sur les composants du graphique :

```csharp
chart.Legend.Position = LegendPosition.Bottom;
```

## Manipulation des points de données

Ajustez les points de données individuellement pour mettre l’accent :

```csharp
chart.Series[0].DataPoints[0].Format.Fill.FillType = FillType.Solid;
chart.Series[0].DataPoints[0].Format.Fill.SolidFillColor.Color = Color.Red;
```

## Exportation et enregistrement de la présentation modifiée

Une fois que vous avez apporté les modifications souhaitées au graphique, vous pouvez enregistrer la présentation :

```csharp
presentation.Save("ModifiedPresentation.pptx", SaveFormat.Pptx);
```

## Conclusion

Dans ce guide, nous avons exploré le monde fascinant des entités graphiques et du formatage à l'aide d'Aspose.Slides pour .NET. Nous avons commencé par les bases de l'ajout et de la modification de graphiques, nous sommes plongés dans la personnalisation de leur apparence et avons même géré divers éléments du graphique. Aspose.Slides fournit aux développeurs une boîte à outils puissante pour créer par programmation des graphiques visuellement attrayants et informatifs.

## FAQ

### Comment installer Aspose.Slides pour .NET ?

 Vous pouvez télécharger Aspose.Slides pour .NET à partir de[ici](https://releases.aspose.com/slides/net/).

### Puis-je appliquer des styles personnalisés aux graphiques ?

Oui, vous pouvez appliquer des styles personnalisés aux graphiques en manipulant diverses propriétés du graphique.

### Comment ajouter des étiquettes de données aux points de données du graphique ?

 Vous pouvez ajouter des étiquettes de données aux points de données du graphique à l'aide de l'outil`DataLabel` propriété d'un point de données.

### Aspose.Slides convient-il uniquement aux développeurs avancés ?

Non, Aspose.Slides est conçu pour s'adresser aux développeurs de tous niveaux, des débutants aux experts.

### Puis-je exporter des graphiques vers différents formats à l’aide d’Aspose.Slides ?

Absolument! Aspose.Slides prend en charge l'exportation de présentations vers différents formats, notamment PowerPoint et PDF.