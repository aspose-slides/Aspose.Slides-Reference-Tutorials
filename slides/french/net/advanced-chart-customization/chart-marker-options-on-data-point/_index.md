---
title: Utilisation des options de marqueur de graphique sur un point de données dans Aspose.Slides .NET
linktitle: Options de marqueur de graphique sur le point de données
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez comment améliorer vos graphiques PowerPoint à l'aide d'Aspose.Slides pour .NET. Personnalisez les marqueurs de points de données avec des images. Créez des présentations attrayantes.
weight: 11
url: /fr/net/advanced-chart-customization/chart-marker-options-on-data-point/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utilisation des options de marqueur de graphique sur un point de données dans Aspose.Slides .NET


Lorsque vous travaillez avec des présentations et la visualisation de données, Aspose.Slides pour .NET offre un large éventail de fonctionnalités puissantes pour créer, personnaliser et manipuler des graphiques. Dans ce didacticiel, nous explorerons comment utiliser les options de marqueurs de graphique sur des points de données pour améliorer vos présentations graphiques. Ce guide étape par étape vous guidera tout au long du processus, en commençant par les prérequis et l'importation des espaces de noms, pour décomposer chaque exemple en plusieurs étapes.

## Conditions préalables

Avant de commencer à utiliser les options de marqueurs de graphique sur les points de données, assurez-vous que les conditions préalables suivantes sont remplies :

-  Aspose.Slides pour .NET : assurez-vous que Aspose.Slides pour .NET est installé. Vous pouvez le télécharger depuis le[site web](https://releases.aspose.com/slides/net/).

- Exemple de présentation : pour ce didacticiel, nous utiliserons un exemple de présentation nommé "Test.pptx". Vous devriez avoir cette présentation dans votre répertoire de documents.

Commençons maintenant par importer les espaces de noms nécessaires.

## Importer des espaces de noms

```csharp
﻿using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

Nous avons importé les espaces de noms requis et initialisé notre présentation. Passons maintenant à l’utilisation des options de marqueur de graphique sur les points de données.

## Étape 1 : Création du graphique par défaut

```csharp

// Le chemin d'accès au répertoire des documents.
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");

ISlide slide = pres.Slides[0];

//Création du graphique par défaut
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

Nous créons un graphique par défaut de type "LineWithMarkers" sur la diapositive à un emplacement et une taille spécifiés.

## Étape 2 : Obtenir l'index de la feuille de calcul des données graphiques par défaut

```csharp
// Obtention de l'index de la feuille de calcul des données graphiques par défaut
int defaultWorksheetIndex = 0;
```

Ici, nous obtenons l'index de la feuille de calcul de données graphiques par défaut.

## Étape 3 : Obtenir la feuille de calcul des données graphiques

```csharp
// Obtenir la feuille de calcul des données du graphique
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```

Nous récupérons le classeur de données graphiques pour travailler avec les données graphiques.

## Étape 4 : Modification de la série de graphiques

```csharp
// Supprimer la série de démonstration
chart.ChartData.Series.Clear();

// Ajouter une nouvelle série
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);
```

Au cours de cette étape, nous supprimons toute série de démonstration existante et ajoutons une nouvelle série nommée « Série 1 » au graphique.

## Étape 5 : Définition du remplissage d'image pour les points de données

```csharp
// Définir l'image pour les marqueurs
System.Drawing.Image img1 = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx1 = pres.Images.AddImage(img1);

System.Drawing.Image img2 = (System.Drawing.Image)new Bitmap(dataDir + "Tulips.jpg");
IPPImage imgx2 = pres.Images.AddImage(img2);

// Prenez la première série de graphiques
IChartSeries series = chart.ChartData.Series[0];

// Ajouter de nouveaux points de données avec remplissage d'image
IChartDataPoint point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 1, 1, (double)4.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, (double)2.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, (double)3.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 4, 1, (double)4.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;
```

Nous définissons des marqueurs d'image pour les points de données, vous permettant de personnaliser la façon dont chaque point de données apparaît sur le graphique.

## Étape 6 : Modification de la taille du marqueur de la série de graphiques

```csharp
// Modification de la taille du marqueur de série de graphiques
series.Marker.Size = 15;
```

Ici, nous ajustons la taille du marqueur de la série de graphiques pour le rendre visuellement attrayant.

## Étape 7 : Sauvegarde de la présentation

```csharp
pres.Save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

Enfin, nous enregistrons la présentation avec les nouveaux paramètres du graphique.

## Conclusion

Aspose.Slides pour .NET vous permet de créer de superbes présentations graphiques avec diverses options de personnalisation. Dans ce didacticiel, nous nous sommes concentrés sur l'utilisation des options de marqueurs de graphique sur les points de données pour améliorer la représentation visuelle de vos données. Avec Aspose.Slides pour .NET, vous pouvez faire passer vos présentations au niveau supérieur, les rendant plus attrayantes et informatives.

Si vous avez des questions ou avez besoin d'aide avec Aspose.Slides pour .NET, n'hésitez pas à visiter le[Documentation Aspose.Slides](https://reference.aspose.com/slides/net/) ou contactez le[Aspose la communauté](https://forum.aspose.com/) pour le soutien.

## Foire aux questions (FAQ)

### Puis-je utiliser des images personnalisées comme marqueurs pour les points de données dans Aspose.Slides for .NET ?
Oui, vous pouvez utiliser des images personnalisées comme marqueurs pour les points de données dans Aspose.Slides for .NET, comme démontré dans ce didacticiel.

### Comment puis-je modifier le type de graphique dans Aspose.Slides pour .NET ?
 Vous pouvez modifier le type de graphique en spécifiant un autre`ChartType` lors de la création du graphique, tel que « Barre », « Secteur » ou « Zone ».

### Aspose.Slides pour .NET est-il compatible avec les dernières versions de PowerPoint ?
Aspose.Slides for .NET est conçu pour fonctionner avec différents formats PowerPoint et est régulièrement mis à jour pour maintenir la compatibilité avec les dernières versions de PowerPoint.

### Où puis-je trouver plus de didacticiels et de ressources pour Aspose.Slides pour .NET ?
 Vous pouvez explorer des didacticiels et des ressources supplémentaires dans le[Documentation Aspose.Slides](https://reference.aspose.com/slides/net/).

### Existe-t-il une version d’essai d’Aspose.Slides pour .NET disponible ?
 Oui, vous pouvez essayer Aspose.Slides pour .NET en téléchargeant une version d'essai gratuite à partir de[ici](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
