---
title: Récupérer un classeur à partir d'un graphique
linktitle: Récupérer un classeur à partir d'un graphique
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez comment récupérer un classeur à partir d'un graphique à l'aide d'Aspose.Slides pour .NET. Extrayez les données du graphique et créez des classeurs Excel par programmation.
type: docs
weight: 12
url: /fr/net/additional-chart-features/chart-recover-workbook/
---

## Introduction

Des accidents peuvent survenir et vous devrez peut-être récupérer un classeur à partir d'un graphique. Aspose.Slides for .NET vient à la rescousse dans de telles situations. Cette puissante bibliothèque vous permet d'extraire des données de graphiques dans des présentations et de les convertir en un nouveau classeur. Dans ce guide étape par étape, nous vous guiderons tout au long du processus de récupération d'un classeur à partir d'un graphique à l'aide d'Aspose.Slides pour .NET.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants en place :

- Visual Studio : téléchargez et installez Visual Studio, essentiel au développement .NET.
-  Aspose.Slides pour .NET : vous pouvez télécharger la bibliothèque à partir de[ici](https://downloads.aspose.com/slides/net).

## Étape 1 : Installer Aspose.Slides pour .NET

Si vous ne l'avez pas déjà fait, téléchargez et installez Aspose.Slides pour .NET. Cette bibliothèque fournit des fonctionnalités complètes pour travailler avec des présentations PowerPoint par programmation.

## Étape 2 : Charger la présentation

Pour commencer, créez un nouveau projet C# dans Visual Studio. Ajoutez des références aux assemblys Aspose.Slides nécessaires. Chargez la présentation PowerPoint contenant le graphique à partir duquel vous souhaitez récupérer les données.

```csharp
// Charger la présentation
Presentation presentation = new Presentation("your-presentation.pptx");
```

## Étape 3 : Identifiez le graphique

 Identifiez la diapositive et le graphique à partir desquels vous souhaitez récupérer des données. Vous pouvez accéder aux diapositives en utilisant le`presentation.Slides` collection et graphiques utilisant le`slide.Shapes` collection.

```csharp
// Obtenez la diapositive contenant le graphique
ISlide slide = presentation.Slides[0];

// Obtenez le graphique
IChart chart = null;
foreach (IShape shape in slide.Shapes)
{
    if (shape is IChart)
    {
        chart = (IChart)shape;
        break;
    }
}
```

## Étape 4 : Extraire les données du graphique

Extrayez les données du graphique à l'aide de l'API d'Aspose.Slides. Vous pouvez récupérer les valeurs des séries et catégories de graphiques.

```csharp
// Extraire les données du graphique
IChartData chartData = chart.ChartData;
```

## Étape 5 : Créer un nouveau classeur

Créez un nouveau classeur Excel à l'aide d'une bibliothèque comme EPPlus ou ClosedXML.

```csharp
// Créer un nouveau classeur Excel
using (var excelPackage = new ExcelPackage())
{
    var worksheet = excelPackage.Workbook.Worksheets.Add("Chart Data");
    // Ajoutez du code ici pour remplir les en-têtes de la feuille de calcul
}
```

## Étape 6 : Remplir le classeur avec les données du graphique

Remplissez la feuille de calcul Excel avec les données extraites du graphique.

```csharp
//Remplir la feuille de calcul Excel avec les données du graphique
int rowIndex = 2;
foreach (var series in chartData.Series)
{
    worksheet.Cells[rowIndex, 1].Value = series.Name;
    // Ajoutez du code ici pour remplir la feuille de calcul avec des données de série
    rowIndex++;
}
```

## Étape 7 : Enregistrez le classeur

Enregistrez le classeur Excel avec les données du graphique récupérées.

```csharp
// Enregistrez le classeur Excel
excelPackage.SaveAs(new FileInfo("recovered-workbook.xlsx"));
```

## Conclusion

La récupération d'un classeur à partir d'un graphique est facilitée avec Aspose.Slides pour .NET. En suivant ces étapes, vous pouvez extraire par programme les données d'un graphique dans une présentation PowerPoint et créer un nouveau classeur Excel avec les données récupérées. Ce processus peut sauver des vies en cas d’accident et les données doivent être récupérées.

## FAQ

### Comment installer Aspose.Slides pour .NET ?

 Vous pouvez télécharger Aspose.Slides pour .NET à partir de[ici](https://downloads.aspose.com/slides/net).

### Puis-je récupérer des données à partir de différents types de graphiques ?

Oui, Aspose.Slides pour .NET prend en charge différents types de graphiques, notamment les graphiques à barres, les graphiques linéaires, les diagrammes circulaires, etc.

### Aspose.Slides pour .NET est-il adapté à un usage professionnel ?

Absolument! Aspose.Slides for .NET est une bibliothèque robuste utilisée par les développeurs pour travailler efficacement avec des présentations PowerPoint.

### Existe-t-il des conditions de licence pour utiliser Aspose.Slides pour .NET ?

 Oui, Aspose.Slides pour .NET nécessite une licence valide pour une utilisation commerciale. Vous pouvez trouver les détails de la licence sur le[Site Aspose](https://purchase.aspose.com).

### Puis-je personnaliser l’apparence du classeur Excel récupéré ?

Oui, vous pouvez personnaliser l'apparence et le formatage du classeur Excel à l'aide de bibliothèques comme EPPlus ou ClosedXML.