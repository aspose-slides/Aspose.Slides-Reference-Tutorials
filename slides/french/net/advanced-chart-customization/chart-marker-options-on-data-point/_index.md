---
"description": "Apprenez à améliorer vos graphiques PowerPoint avec Aspose.Slides pour .NET. Personnalisez les marqueurs de points de données avec des images. Créez des présentations attrayantes."
"linktitle": "Options de marqueur de graphique sur le point de données"
"second_title": "API de traitement PowerPoint Aspose.Slides .NET"
"title": "Utilisation des options de marqueur de graphique sur un point de données dans Aspose.Slides .NET"
"url": "/fr/net/advanced-chart-customization/chart-marker-options-on-data-point/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Utilisation des options de marqueur de graphique sur un point de données dans Aspose.Slides .NET


Pour vos présentations et visualisations de données, Aspose.Slides pour .NET offre un large éventail de fonctionnalités puissantes pour créer, personnaliser et manipuler des graphiques. Dans ce tutoriel, nous découvrirons comment utiliser les options de marqueurs de points de données pour optimiser vos présentations graphiques. Ce guide étape par étape vous guidera tout au long du processus, des prérequis à l'importation des espaces de noms, en passant par la décomposition de chaque exemple en plusieurs étapes.

## Prérequis

Avant de nous plonger dans l’utilisation des options de marqueurs de graphique sur les points de données, assurez-vous que les conditions préalables suivantes sont en place :

- Aspose.Slides pour .NET : Assurez-vous d'avoir installé Aspose.Slides pour .NET. Vous pouvez le télécharger depuis le [site web](https://releases.aspose.com/slides/net/).

- Exemple de présentation : Pour ce tutoriel, nous utiliserons un exemple de présentation intitulé « Test.pptx ». Cette présentation devrait se trouver dans votre répertoire de documents.

Commençons maintenant par importer les espaces de noms nécessaires.

## Importer des espaces de noms

```csharp
﻿using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

Nous avons importé les espaces de noms requis et initialisé notre présentation. Passons maintenant à l'utilisation des options de marqueurs de graphique sur les points de données.

## Étape 1 : Création du graphique par défaut

```csharp

// Le chemin vers le répertoire des documents.
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");

ISlide slide = pres.Slides[0];

// Création du graphique par défaut
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

Nous créons un graphique par défaut de type « LineWithMarkers » sur la diapositive à un emplacement et une taille spécifiés.

## Étape 2 : Obtenir l'index de la feuille de calcul des données graphiques par défaut

```csharp
// Obtenir l'index de la feuille de calcul des données du graphique par défaut
int defaultWorksheetIndex = 0;
```

Ici, nous obtenons l'index de la feuille de calcul des données du graphique par défaut.

## Étape 3 : Obtenir la feuille de calcul des données du graphique

```csharp
// Obtenir la feuille de calcul des données du graphique
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```

Nous récupérons le classeur de données du graphique pour travailler avec les données du graphique.

## Étape 4 : Modification de la série de graphiques

```csharp
// Supprimer la série de démonstration
chart.ChartData.Series.Clear();

// Ajouter une nouvelle série
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);
```

Dans cette étape, nous supprimons toute série de démonstration existante et ajoutons une nouvelle série nommée « Série 1 » au graphique.

## Étape 5 : Définition du remplissage d'image pour les points de données

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

## Étape 6 : Modification de la taille du marqueur de série de graphiques

```csharp
// Modification de la taille du marqueur de la série de graphiques
series.Marker.Size = 15;
```

Ici, nous ajustons la taille du marqueur de la série de graphiques pour le rendre visuellement attrayant.

## Étape 7 : Enregistrer la présentation

```csharp
pres.Save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

Enfin, nous enregistrons la présentation avec les nouveaux paramètres du graphique.

## Conclusion

Aspose.Slides pour .NET vous permet de créer de superbes présentations graphiques avec diverses options de personnalisation. Dans ce tutoriel, nous avons mis l'accent sur l'utilisation des marqueurs de graphique sur les points de données pour améliorer la représentation visuelle de vos données. Avec Aspose.Slides pour .NET, vous pouvez donner une nouvelle dimension à vos présentations, les rendant plus attrayantes et informatives.

Si vous avez des questions ou avez besoin d'aide avec Aspose.Slides pour .NET, n'hésitez pas à visiter le [Documentation Aspose.Slides](https://reference.aspose.com/slides/net/) ou contactez le [Communauté Aspose](https://forum.aspose.com/) pour le soutien.

## Foire aux questions (FAQ)

### Puis-je utiliser des images personnalisées comme marqueurs pour les points de données dans Aspose.Slides pour .NET ?
Oui, vous pouvez utiliser des images personnalisées comme marqueurs pour les points de données dans Aspose.Slides pour .NET, comme démontré dans ce didacticiel.

### Comment puis-je modifier le type de graphique dans Aspose.Slides pour .NET ?
Vous pouvez modifier le type de graphique en spécifiant un autre `ChartType` lors de la création du graphique, par exemple « Barre », « Secteur » ou « Aire ».

### Aspose.Slides pour .NET est-il compatible avec les dernières versions de PowerPoint ?
Aspose.Slides pour .NET est conçu pour fonctionner avec différents formats PowerPoint et est régulièrement mis à jour pour maintenir la compatibilité avec les dernières versions de PowerPoint.

### Où puis-je trouver plus de tutoriels et de ressources pour Aspose.Slides pour .NET ?
Vous pouvez explorer des tutoriels et des ressources supplémentaires dans le [Documentation Aspose.Slides](https://reference.aspose.com/slides/net/).

### Existe-t-il une version d'essai d'Aspose.Slides pour .NET disponible ?
Oui, vous pouvez essayer Aspose.Slides pour .NET en téléchargeant une version d'essai gratuite à partir de [ici](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}