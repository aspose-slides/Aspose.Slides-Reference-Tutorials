---
title: Personnalisation avancée des graphiques dans Aspose.Slides
linktitle: Personnalisation avancée des graphiques dans Aspose.Slides
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez la personnalisation avancée des graphiques dans Aspose.Slides pour .NET. Créez des graphiques visuellement attrayants avec des conseils étape par étape.
type: docs
weight: 10
url: /fr/net/advanced-chart-customization/advanced-chart-customization/
---

La création de graphiques visuellement attrayants et informatifs est une partie essentielle de la présentation des données dans de nombreuses applications. Aspose.Slides pour .NET fournit des outils robustes pour la personnalisation des graphiques, vous permettant d'affiner chaque aspect de vos graphiques. Dans ce didacticiel, nous explorerons les techniques avancées de personnalisation de graphiques à l'aide d'Aspose.Slides pour .NET.

## Conditions préalables

Avant de vous lancer dans la personnalisation avancée des graphiques avec Aspose.Slides pour .NET, assurez-vous que les conditions préalables suivantes sont en place :

1. Aspose.Slides pour la bibliothèque .NET : vous devez avoir la bibliothèque Aspose.Slides installée et correctement configurée dans votre projet .NET. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/slides/net/).

2. Un environnement de développement .NET : vous devez disposer d'un environnement de développement .NET, comprenant Visual Studio ou tout autre IDE de votre choix.

3. Connaissance de base de C# : une connaissance du langage de programmation C# sera utile, car nous écrireons du code C# pour fonctionner avec Aspose.Slides.

Maintenant, décomposons la personnalisation avancée des graphiques en plusieurs étapes pour vous guider tout au long du processus.

## Étape 1 : Créer une présentation

Tout d’abord, créez une nouvelle présentation à l’aide d’Aspose.Slides.

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "Your Document Directory";

// Créez un répertoire s'il n'est pas déjà présent.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// Instanciation de la présentation
Presentation pres = new Presentation();
```

Dans cette étape, nous lançons une nouvelle présentation qui contiendra notre graphique.

## Étape 2 : accéder à la première diapositive

Ensuite, accédez à la première diapositive de la présentation où vous souhaitez ajouter le graphique.

```csharp
// Accéder à la première diapositive
ISlide slide = pres.Slides[0];
```

Cet extrait de code vous permet de travailler avec la première diapositive de la présentation.

## Étape 3 : Ajout d'un exemple de graphique

Maintenant, ajoutons un exemple de graphique à la diapositive. Dans cet exemple, nous allons créer un graphique linéaire avec des marqueurs.

```csharp
// Ajout de l'exemple de graphique
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

Ici, nous précisons le type de graphique (LineWithMarkers) ainsi que sa position et ses dimensions sur la diapositive.

## Étape 4 : Définition du titre du graphique

Définissons un titre pour le graphique afin de fournir un contexte.

```csharp
// Définition du titre du graphique
chart.HasTitle = true;
chart.ChartTitle.AddTextFrameForOverriding("");
IPortion chartTitle = chart.ChartTitle.TextFrameForOverriding.Paragraphs[0].Portions[0];
chartTitle.Text = "Sample Chart";
chartTitle.PortionFormat.FillFormat.FillType = FillType.Solid;
chartTitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
chartTitle.PortionFormat.FontHeight = 20;
chartTitle.PortionFormat.FontBold = NullableBool.True;
chartTitle.PortionFormat.FontItalic = NullableBool.True;
```

Ce code définit un titre pour le graphique, en spécifiant son texte, son apparence et son style de police.

## Étape 5 : Personnaliser les principales lignes de la grille

Maintenant, personnalisons les principales lignes de la grille pour l'axe des valeurs.

```csharp
// Définition du format des lignes de grille principales pour l'axe des valeurs
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Blue;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.Width = 5;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.DashStyle = LineDashStyle.DashDot;
```

Cette étape configure l’apparence des principales lignes de grille sur l’axe des valeurs.

## Étape 6 : Personnaliser les lignes de grille mineures

De même, nous pouvons personnaliser les lignes de grille mineures pour l’axe des valeurs.

```csharp
// Définition du format des lignes de grille mineures pour l'axe des valeurs
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Red;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.Width = 3;
```

Ce code ajuste l'apparence des lignes de grille mineures sur l'axe des valeurs.

## Étape 7 : Définir le format du numéro de l'axe des valeurs

Personnalisez le format numérique de l'axe des valeurs.

```csharp
// Définition du format du numéro d'axe des valeurs
chart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
chart.Axes.VerticalAxis.DisplayUnit = DisplayUnitType.Thousands;
chart.Axes.VerticalAxis.NumberFormat = "0.0%";
```

Cette étape vous permet de formater les nombres affichés sur l'axe des valeurs.

## Étape 8 : Définir les valeurs maximales et minimales du graphique

Définissez les valeurs maximales et minimales du graphique.

```csharp
// Tableau de réglage des valeurs maximales et minimales
chart.Axes.VerticalAxis.IsAutomaticMajorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMaxValue = false;
chart.Axes.VerticalAxis.IsAutomaticMinorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMinValue = false;

chart.Axes.VerticalAxis.MaxValue = 15f;
chart.Axes.VerticalAxis.MinValue = -2f;
chart.Axes.VerticalAxis.MinorUnit = 0.5f;
chart.Axes.VerticalAxis.MajorUnit = 2.0f;
```

Ici, vous spécifiez la plage de valeurs que l'axe du graphique doit afficher.

## Étape 9 : Personnaliser les propriétés du texte de l'axe des valeurs

Vous pouvez également personnaliser les propriétés du texte de l'axe des valeurs.

```csharp
// Définition des propriétés du texte de l'axe des valeurs
IChartPortionFormat txtVal = chart.Axes.VerticalAxis.TextFormat.PortionFormat;
txtVal.FontBold = NullableBool.True;
txtVal.FontHeight = 16;
txtVal.FontItalic = NullableBool.True;
txtVal.FillFormat.FillType = FillType.Solid;
txtVal.FillFormat.SolidFillColor.Color = Color.DarkGreen;
txtVal.LatinFont = new FontData("Times New Roman");
```

Ce code vous permet d'ajuster le style de police et l'apparence des étiquettes de l'axe des valeurs.

## Étape 10 : Ajouter le titre de l'axe de valeur

Si votre graphique nécessite un titre pour l'axe des valeurs, vous pouvez l'ajouter à cette étape.

```csharp
// Titre de l’axe des valeurs de définition
chart.Axes.VerticalAxis.HasTitle = true;
chart.Axes.VerticalAxis.Title.AddTextFrameForOverriding("");
IPortion valtitle = chart.Axes.VerticalAxis.Title.TextFrameForOverriding.Paragraphs[0].Portions[0];
valtitle.Text = "Primary Axis";
valtitle.PortionFormat.FillFormat.FillType = FillType.Solid;
valtitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
valtitle.PortionFormat.FontHeight = 20;
valtitle.PortionFormat.FontBold = NullableBool.True;
valtitle.PortionFormat.FontItalic = NullableBool.True;
```

Dans cette étape, vous pouvez définir un titre pour l'axe des valeurs.

## Étape 11 : Personnaliser les principales lignes de grille pour l'axe des catégories

Concentrons-nous maintenant sur les principales lignes de la grille de l'axe des catégories.

```csharp
// Définition du format des lignes de quadrillage principales pour l'axe des catégories
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes

.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Green;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.Width = 5;
```

Ce code configure l'apparence des lignes principales du quadrillage sur l'axe des catégories.

## Étape 12 : Personnaliser les lignes de grille mineures pour l'axe des catégories

Semblable à l’axe des valeurs, vous pouvez personnaliser les lignes de grille mineures pour l’axe des catégories.

```csharp
// Définition du format des lignes de quadrillage mineures pour l'axe des catégories
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Yellow;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.Width = 3;
```

Ici, vous ajustez l’apparence des lignes de grille mineures sur l’axe des catégories.

## Étape 13 : Personnaliser les propriétés du texte de l'axe des catégories

Personnalisez les propriétés du texte pour les étiquettes de l’axe des catégories.

```csharp
// Définition des propriétés du texte de l'axe des catégories
IChartPortionFormat txtCat = chart.Axes.HorizontalAxis.TextFormat.PortionFormat;
txtCat.FontBold = NullableBool.True;
txtCat.FontHeight = 16;
txtCat.FontItalic = NullableBool.True;
txtCat.FillFormat.FillType = FillType.Solid;
txtCat.FillFormat.SolidFillColor.Color = Color.Blue;
txtCat.LatinFont = new FontData("Arial");
```

Ce code vous permet d'ajuster le style de police et l'apparence des étiquettes de l'axe des catégories.

## Étape 14 : Ajouter le titre de l'axe de catégorie

Vous pouvez également ajouter un titre à l’axe des catégories si nécessaire.

```csharp
// Définition du titre de la catégorie
chart.Axes.HorizontalAxis.HasTitle = true;
chart.Axes.HorizontalAxis.Title.AddTextFrameForOverriding("");

IPortion catTitle = chart.Axes.HorizontalAxis.Title.TextFrameForOverriding.Paragraphs[0].Portions[0];
catTitle.Text = "Sample Category";
catTitle.PortionFormat.FillFormat.FillType = FillType.Solid;
catTitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
catTitle.PortionFormat.FontHeight = 20;
catTitle.PortionFormat.FontBold = NullableBool.True;
catTitle.PortionFormat.FontItalic = NullableBool.True;
```

Dans cette étape, vous pouvez définir un titre pour l'axe des catégories.

## Étape 15 : personnalisations supplémentaires

Vous pouvez explorer d’autres personnalisations, telles que les légendes, les couleurs du mur arrière du graphique, du sol et de la zone de tracé. Ces personnalisations vous permettent d'améliorer l'attrait visuel de votre graphique.

```csharp
// Personnalisations supplémentaires (facultatif)

// Définition des propriétés du texte des légendes
IChartPortionFormat txtleg = chart.Legend.TextFormat.PortionFormat;
txtleg.FontBold = NullableBool.True;
txtleg.FontHeight = 16;
txtleg.FontItalic = NullableBool.True;
txtleg.FillFormat.FillType = FillType.Solid;
txtleg.FillFormat.SolidFillColor.Color = Color.DarkRed;

// Définir les légendes du graphique sans chevauchement du graphique
chart.Legend.Overlay = true;

// Tracer la première série sur l'axe des valeurs secondaire (si nécessaire)
// Chart.ChartData.Series[0].PlotOnSecondAxis = true;

// Définition de la couleur du mur arrière du tableau
chart.BackWall.Thickness = 1;
chart.BackWall.Format.Fill.FillType = FillType.Solid;
chart.BackWall.Format.Fill.SolidFillColor.Color = Color.Orange;

// Définition de la couleur du sol du tableau
chart.Floor.Format.Fill.FillType = FillType.Solid;
chart.Floor.Format.Fill.SolidFillColor.Color = Color.Red;

//Définition de la couleur de la zone de tracé
chart.PlotArea.Format.Fill.FillType = FillType.Solid;
chart.PlotArea.Format.Fill.SolidFillColor.Color = Color.LightCyan;

// Enregistrez la présentation
pres.Save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

Ces personnalisations supplémentaires sont facultatives et peuvent être appliquées en fonction de vos exigences spécifiques en matière de conception de graphiques.

## Conclusion

Dans ce guide étape par étape, nous avons exploré la personnalisation avancée des graphiques à l'aide d'Aspose.Slides pour .NET. Vous avez appris à créer une présentation, à ajouter un graphique et à affiner son apparence, notamment les lignes de grille, les étiquettes d'axe et d'autres éléments visuels. Grâce aux puissantes options de personnalisation fournies par Aspose.Slides, vous pouvez créer des graphiques qui transmettent efficacement vos données et engagent votre public.

 Si vous avez des questions ou rencontrez des difficultés lorsque vous travaillez avec Aspose.Slides pour .NET, n'hésitez pas à explorer la documentation.[ici](https://reference.aspose.com/slides/net/) ou demandez de l'aide dans Aspose.Slides[forum](https://forum.aspose.com/).

## FAQ

### Quelles versions de .NET sont prises en charge par Aspose.Slides pour .NET ?
Aspose.Slides pour .NET prend en charge diverses versions de .NET, notamment .NET Framework et .NET Core. Vous pouvez vous référer à la documentation pour la liste complète des versions prises en charge.

### Puis-je créer des graphiques à partir de sources de données telles que des fichiers Excel à l'aide d'Aspose.Slides pour .NET ?
Oui, Aspose.Slides pour .NET vous permet de créer des graphiques à partir de sources de données externes telles que des feuilles de calcul Excel. Vous pouvez explorer la documentation pour des exemples détaillés.

### Comment puis-je ajouter des étiquettes de données personnalisées à ma série de graphiques ?
 Pour ajouter des étiquettes de données personnalisées à votre série de graphiques, vous pouvez accéder au`DataLabels` propriété de la série et personnalisez les étiquettes selon vos besoins. Reportez-vous à la documentation pour obtenir des exemples de code et des exemples.

### Est-il possible d'exporter le graphique vers différents formats de fichiers, tels que PDF ou formats d'image ?
Oui, Aspose.Slides pour .NET propose des options pour exporter votre présentation avec des graphiques vers différents formats, notamment PDF et images. Vous pouvez utiliser la bibliothèque pour enregistrer votre travail dans le format de sortie souhaité.

### Où puis-je trouver plus de didacticiels et d’exemples pour Aspose.Slides pour .NET ?
 Vous pouvez trouver une multitude de didacticiels, d'exemples de code et de documentation sur Aspose.Slides.[site web](https://reference.aspose.com/slides/net/).