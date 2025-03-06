---
title: Colorisation de graphiques avec Aspose.Slides pour .NET
linktitle: Ajouter de la couleur aux points de données dans le graphique
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez comment ajouter de la couleur aux points de données dans un graphique avec Aspose.Slides pour .NET. Améliorez visuellement vos présentations et engagez efficacement votre public.
weight: 12
url: /fr/net/licensing-and-formatting/add-color-to-data-points/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


Dans ce guide étape par étape, nous vous guiderons tout au long du processus d'ajout de couleur aux points de données dans un graphique à l'aide d'Aspose.Slides pour .NET. Aspose.Slides est une bibliothèque puissante pour travailler avec des présentations PowerPoint dans des applications .NET. L'ajout de couleur aux points de données d'un graphique peut rendre vos présentations plus attrayantes et plus faciles à comprendre.

## Conditions préalables

Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :

1. Visual Studio : vous devez installer Visual Studio sur votre ordinateur.

2.  Aspose.Slides pour .NET : téléchargez et installez Aspose.Slides pour .NET à partir du[lien de téléchargement](https://releases.aspose.com/slides/net/).

3. Une compréhension de base de C# : Vous devez avoir une connaissance de base de la programmation C#.

4. Votre répertoire de documents : remplacez « Votre répertoire de documents » dans le code par le chemin réel d'accès à votre répertoire de documents.

## Importation d'espaces de noms

Avant de pouvoir travailler avec Aspose.Slides pour .NET, vous devez importer les espaces de noms nécessaires. 

```csharp
﻿using Aspose.Slides.Charts;
using Aspose.Slides.Export;
using Aspose.Slides;
```


Dans cet exemple, nous ajouterons de la couleur aux points de données d'un graphique en utilisant le type de graphique Sunburst.

```csharp
using (Presentation pres = new Presentation())
{
    // Le chemin d'accès au répertoire des documents.
    string dataDir = "Your Document Directory";

    IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.Sunburst, 100, 100, 450, 400);
    
    // Le reste du code sera ajouté dans les étapes suivantes.
}
```

## Étape 1 : Accéder aux points de données

Pour ajouter de la couleur à des points de données spécifiques dans un graphique, vous devez accéder à ces points de données. Dans cet exemple, nous ciblerons le point de données 3.

```csharp
IChartDataPointCollection dataPoints = chart.ChartData.Series[0].DataPoints;
dataPoints[3].DataPointLevels[0].Label.DataLabelFormat.ShowValue = true;
```

## Étape 2 : personnalisation des étiquettes de données

Maintenant, personnalisons les étiquettes de données pour le point de données 0. Nous allons masquer le nom de la catégorie et afficher le nom de la série.

```csharp
IDataLabel branch1Label = dataPoints[0].DataPointLevels[2].Label;
branch1Label.DataLabelFormat.ShowCategoryName = false;
branch1Label.DataLabelFormat.ShowSeriesName = true;
```

## Étape 3 : Définition du format du texte et de la couleur de remplissage

Nous pouvons encore améliorer l'apparence des étiquettes de données en définissant le format du texte et la couleur de remplissage. Dans cette étape, nous définirons la couleur du texte sur jaune pour le point de données 0.

```csharp
branch1Label.DataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
branch1Label.DataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = Color.Yellow;
```

## Étape 4 : Personnalisation de la couleur de remplissage des points de données

Modifions maintenant la couleur de remplissage du point de données 9. Nous allons lui attribuer une couleur spécifique.

```csharp
IFormat steam4Format = dataPoints[9].Format;
steam4Format.Fill.FillType = FillType.Solid;
steam4Format.Fill.SolidFillColor.Color = Color.FromArgb(0, 176, 240, 255);
```

## Étape 5 : enregistrement de la présentation

Après avoir personnalisé le graphique, vous pouvez enregistrer la présentation avec les modifications.

```csharp
pres.Save(dataDir + "AddColorToDataPoints.pptx", SaveFormat.Pptx);
```

Toutes nos félicitations! Vous avez réussi à ajouter de la couleur aux points de données d'un graphique à l'aide d'Aspose.Slides pour .NET. Cela peut grandement améliorer l’attrait visuel et la clarté de vos présentations.

## Conclusion

L'ajout de couleur aux points de données d'un graphique est un moyen puissant de rendre vos présentations plus attrayantes et informatives. Avec Aspose.Slides pour .NET, vous disposez des outils nécessaires pour créer des graphiques visuellement attrayants qui transmettent efficacement vos données.

## Foire aux questions (FAQ)

### Qu’est-ce qu’Aspose.Slides pour .NET ?
   Aspose.Slides for .NET est une bibliothèque qui permet aux développeurs .NET de travailler avec des présentations PowerPoint par programme.

### Puis-je personnaliser d’autres propriétés de graphique à l’aide d’Aspose.Slides ?
   Oui, vous pouvez personnaliser divers aspects des graphiques, tels que les étiquettes de données, les polices, les couleurs, etc., à l'aide d'Aspose.Slides pour .NET.

### Où puis-je trouver de la documentation pour Aspose.Slides pour .NET ?
    Vous pouvez trouver une documentation détaillée sur[lien vers la documentation](https://reference.aspose.com/slides/net/).

### Existe-t-il un essai gratuit disponible pour Aspose.Slides pour .NET ?
    Oui, vous pouvez télécharger un essai gratuit à partir de[ici](https://releases.aspose.com/).

### Comment puis-je obtenir du support pour Aspose.Slides pour .NET ?
    Pour obtenir de l'aide et des discussions, visitez le[Forum Aspose.Slides](https://forum.aspose.com/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
