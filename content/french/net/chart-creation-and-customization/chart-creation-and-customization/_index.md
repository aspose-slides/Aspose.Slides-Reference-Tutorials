---
title: Création et personnalisation de graphiques dans Aspose.Slides
linktitle: Création et personnalisation de graphiques dans Aspose.Slides
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez comment créer et personnaliser de superbes graphiques à l'aide d'Aspose.Slides pour .NET. Guide étape par étape avec des exemples de code.
type: docs
weight: 10
url: /fr/net/chart-creation-and-customization/chart-creation-and-customization/
---

## Introduction à Aspose.Slides

Aspose.Slides est une bibliothèque robuste qui fournit des API permettant de travailler avec des présentations PowerPoint dans divers langages de programmation, notamment .NET. Il permet aux développeurs de créer, manipuler et gérer différents éléments de présentations, tels que des diapositives, des formes, du texte et des graphiques.

## Mise en place de votre projet

Avant de commencer, assurez-vous que la bibliothèque Aspose.Slides est installée dans votre projet .NET. Vous pouvez le télécharger depuis le site Web Aspose ou l'installer via le gestionnaire de packages NuGet.

```csharp
// Installer Aspose.Slides via NuGet
Install-Package Aspose.Slides
```

## Créer un graphique

Pour créer un graphique à l'aide d'Aspose.Slides, procédez comme suit :

1. Importez les espaces de noms nécessaires :
```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
```

2. Initialiser une présentation :
```csharp
Presentation presentation = new Presentation();
ISlide slide = presentation.Slides.AddEmptySlide();
```

3. Ajoutez un graphique à la diapositive :
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.Column, 100, 100, 500, 300);
```

## Ajout de données au graphique

Ensuite, ajoutons des données à notre graphique :

1. Accédez au classeur du graphique :
```csharp
IChartDataWorkbook workbook = chart.ChartData.ChartDataWorkbook;
```

2. Ajoutez des catégories et des séries :
```csharp
workbook.AddCell(0, 1, "Category 1");
workbook.AddCell(0, 2, "Category 2");

IChartSeries series = chart.ChartData.Series.Add(workbook.GetCell(0, 1), chart.Type);
```

3. Définir les valeurs pour la série :
```csharp
series.DataPoints.AddDataPointForBarSeries(workbook.GetCell(0, 2));
```

## Personnalisation des éléments du graphique

Vous pouvez personnaliser divers éléments du graphique :

1. Personnaliser le titre du graphique :
```csharp
chart.HasTitle = true;
chart.ChartTitle.Text.Text = "Sales Data";
```

2. Modifier les propriétés de l'axe :
```csharp
chart.Axes.HorizontalAxis.HasTitle = true;
chart.Axes.HorizontalAxis.Title.Text.Text = "Months";
```

3. Ajustez le quadrillage et les graduations :
```csharp
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Gray;
```

## Application de styles et de couleurs

Améliorez l'apparence de votre graphique :

1. Appliquer le style de graphique :
```csharp
chart.ChartStyle = 5; // Choisissez un style souhaité
```

2. Définir les couleurs de la série :
```csharp
series.Format.Fill.FillType = FillType.Solid;
series.Format.Fill.SolidFillColor.Color = Color.Blue;
```

## Formatage des axes et des étiquettes

Formatage et étiquettes des axes de contrôle :

1. Formater les valeurs des axes :
```csharp
chart.Axes.HorizontalAxis.NumberFormat.FormatCode = "mm/dd";
```

2. Faire pivoter les étiquettes des axes :
```csharp
chart.Axes.HorizontalAxis.TextFormat.RotationAngle = 45;
```

## Ajout de titres et de légendes

Ajoutez des titres et des légendes pour améliorer la clarté :

1. Personnalisez les propriétés de la légende :
```csharp
chart.Legend.Position = LegendPosition.Bottom;
chart.Legend.TextFormat.PortionFormat.FontBold = NullableBool.True;
```

2. Définir les titres des axes :
```csharp
chart.Axes.VerticalAxis.Title.Text.Text = "Sales";
```

## Travailler avec plusieurs séries

Incorporez plusieurs séries pour une représentation complète des données :

1. Ajouter des séries supplémentaires :
```csharp
IChartSeries series2 = chart.ChartData.Series.Add(workbook.GetCell(0, 2), chart.Type);
```

2. Définir les valeurs pour la nouvelle série :
```csharp
series2.DataPoints.AddDataPointForBarSeries(workbook.GetCell(0, 3));
```

## Enregistrement et exportation de la présentation

Enfin, enregistrez et exportez votre présentation :

```csharp
presentation.Save("ChartPresentation.pptx", SaveFormat.Pptx);
```
## Conclusion

Dans ce didacticiel, nous avons expliqué comment créer, personnaliser et manipuler des graphiques à l'aide de la bibliothèque Aspose.Slides pour .NET. Aspose.Slides fournit un ensemble complet de fonctionnalités qui permettent aux développeurs de travailler par programmation avec des présentations PowerPoint et de gérer efficacement les tâches liées aux graphiques.

## FAQ

### Comment puis-je modifier le type de graphique après sa création ?

 Vous pouvez modifier le type de graphique en utilisant le`ChangeType` méthode sur l'objet graphique et en fournissant la méthode souhaitée`ChartType` valeur d'énumération.

### Puis-je appliquer des effets 3D à mon graphique ?

 Oui, vous pouvez ajouter des effets 3D à votre graphique en configurant le`Format.ThreeDFormat` propriétés de la série du graphique.

### Est-il possible d'intégrer des graphiques dans des applications Web ?

Absolument! Vous pouvez créer des graphiques à l'aide d'Aspose.Slides, puis les afficher dans des applications Web en exportant les diapositives sous forme d'images ou de HTML interactif.

### Puis-je personnaliser l’apparence de points de données individuels ?

 Certainement! Vous pouvez accéder à des points de données individuels à l'aide du`DataPoints`collection et leur appliquer un formatage.

### Où puis-je trouver plus d’informations sur Aspose.Slides pour .NET ?

 Pour une documentation détaillée et des exemples, visitez le[Aspose.Slides pour la documentation .NET](https://reference.aspose.com/slides/net).