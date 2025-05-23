---
"description": "Découvrez comment ajouter différentes courbes de tendance à vos graphiques avec Aspose.Slides pour .NET grâce à ce guide étape par étape. Améliorez facilement vos compétences en visualisation de données !"
"linktitle": "Lignes de tendance du graphique"
"second_title": "API de traitement PowerPoint Aspose.Slides .NET"
"title": "Exploration des courbes de tendance des graphiques dans Aspose.Slides pour .NET"
"url": "/fr/net/advanced-chart-customization/chart-trend-lines/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Exploration des courbes de tendance des graphiques dans Aspose.Slides pour .NET


Dans le monde de la visualisation et de la présentation de données, l'intégration de graphiques peut être un moyen efficace de transmettre des informations. Aspose.Slides pour .NET offre un ensemble complet d'outils pour travailler avec des graphiques, notamment la possibilité d'y ajouter des courbes de tendance. Dans ce tutoriel, nous allons explorer étape par étape le processus d'ajout de courbes de tendance à un graphique avec Aspose.Slides pour .NET. 

## Prérequis

Avant de commencer à travailler avec Aspose.Slides pour .NET, vous devez vous assurer que les conditions préalables suivantes sont en place :

1. Aspose.Slides pour .NET : Pour accéder à la bibliothèque et l'utiliser, vous devez avoir installé Aspose.Slides pour .NET. Vous pouvez la télécharger depuis le [page de téléchargement](https://releases.aspose.com/slides/net/).

2. Environnement de développement : vous devez disposer d’un environnement de développement configuré, de préférence à l’aide d’un environnement de développement intégré .NET comme Visual Studio.

3. Connaissances de base de C# : une compréhension fondamentale de la programmation C# est bénéfique, car nous utiliserons C# pour travailler avec Aspose.Slides pour .NET.

Maintenant que nous avons couvert les conditions préalables, décomposons le processus d'ajout de lignes de tendance à un graphique étape par étape.

## Importation d'espaces de noms

Tout d'abord, assurez-vous d'importer les espaces de noms nécessaires dans votre projet C#. Ces espaces de noms sont essentiels pour utiliser Aspose.Slides pour .NET.

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

## Étape 1 : Créer une présentation

Dans cette étape, nous créons une présentation vide avec laquelle travailler.

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "Your Document Directory";

// Créez un répertoire s'il n'est pas déjà présent.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// Créer une présentation vide
Presentation pres = new Presentation();
```

## Étape 2 : ajouter un graphique à la diapositive

Ensuite, nous ajoutons un graphique à colonnes groupées à une diapositive.

```csharp
// Création d'un graphique à colonnes groupées
IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## Étape 3 : ajouter des lignes de tendance au graphique

Nous ajoutons maintenant différents types de lignes de tendance à la série de graphiques.

### Ajout d'une ligne de tendance exponentielle

```csharp
// Ajout d'une ligne de tendance exponentielle pour la série de graphiques 1
ITrendline tredLineExp = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Exponential);
tredLineExp.DisplayEquation = false;
tredLineExp.DisplayRSquaredValue = false;
```

### Ajout d'une ligne de tendance linéaire

```csharp
// Ajout d'une ligne de tendance linéaire pour la série de graphiques 1
ITrendline tredLineLin = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Linear);
tredLineLin.Format.Line.FillFormat.FillType = FillType.Solid;
tredLineLin.Format.Line.FillFormat.SolidFillColor.Color = Color.Red;
```

### Ajout d'une ligne de tendance logarithmique

```csharp
// Ajout d'une ligne de tendance logarithmique pour la série de graphiques 2
ITrendline tredLineLog = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.Logarithmic);
tredLineLog.AddTextFrameForOverriding("New log trend line");
```

### Ajout d'une ligne de tendance moyenne mobile

```csharp
// Ajout d'une ligne de tendance moyenne mobile pour la série de graphiques 2
ITrendline tredLineMovAvg = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.MovingAverage);
tredLineMovAvg.Period = 3;
tredLineMovAvg.TrendlineName = "New TrendLine Name";
```

### Ajout d'une ligne de tendance polynomiale

```csharp
// Ajout d'une ligne de tendance polynomiale pour la série de graphiques 3
ITrendline tredLinePol = chart.ChartData.Series[2].TrendLines.Add(TrendlineType.Polynomial);
tredLinePol.Forward = 1;
tredLinePol.Order = 3;
```

### Ajout d'une ligne de tendance de puissance

```csharp
// Ajout d'une ligne de tendance de puissance pour la série de graphiques 3
ITrendline tredLinePower = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.Power);
tredLinePower.Backward = 1;
```

## Étape 4 : Enregistrer la présentation

Après avoir ajouté des lignes de tendance au graphique, enregistrez la présentation.

```csharp
// Sauvegarde de la présentation
pres.Save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

Et voilà ! Vous avez ajouté avec succès plusieurs courbes de tendance à votre graphique avec Aspose.Slides pour .NET.

## Conclusion

Aspose.Slides pour .NET est une bibliothèque polyvalente qui vous permet de créer et de manipuler facilement des graphiques. En suivant ce guide étape par étape, vous pourrez ajouter différents types de courbes de tendance à vos graphiques et ainsi améliorer la représentation visuelle de vos données.

### FAQ

### Où puis-je trouver la documentation d'Aspose.Slides pour .NET ?
Vous pouvez accéder à la documentation [ici](https://reference.aspose.com/slides/net/).

### Comment puis-je télécharger Aspose.Slides pour .NET ?
Vous pouvez télécharger Aspose.Slides pour .NET depuis la page de téléchargement [ici](https://releases.aspose.com/slides/net/).

### Existe-t-il un essai gratuit disponible pour Aspose.Slides pour .NET ?
Oui, vous pouvez essayer Aspose.Slides pour .NET gratuitement en visitant [ce lien](https://releases.aspose.com/).

### Où puis-je acheter Aspose.Slides pour .NET ?
Pour acheter Aspose.Slides pour .NET, visitez la page d'achat [ici](https://purchase.aspose.com/buy).

### Ai-je besoin d’une licence temporaire pour Aspose.Slides pour .NET ?
Vous pouvez obtenir une licence temporaire pour Aspose.Slides pour .NET auprès de [ce lien](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}