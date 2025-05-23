---
"description": "Apprenez à créer des graphiques époustouflants avec Aspose.Slides pour .NET. Améliorez votre visualisation de données grâce à notre guide étape par étape."
"linktitle": "Entités et formatage du graphique"
"second_title": "API de traitement PowerPoint Aspose.Slides .NET"
"title": "Créer de superbes graphiques avec Aspose.Slides pour .NET"
"url": "/fr/net/advanced-chart-customization/chart-entities/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Créer de superbes graphiques avec Aspose.Slides pour .NET


Dans un monde où les données sont omniprésentes, une visualisation efficace est essentielle pour transmettre l'information à votre public. Aspose.Slides pour .NET est une bibliothèque puissante qui vous permet de créer des présentations et des diapositives époustouflantes, notamment des graphiques accrocheurs. Dans ce tutoriel, nous vous guiderons pas à pas dans la création de superbes graphiques avec Aspose.Slides pour .NET. Nous décomposerons chaque exemple en plusieurs étapes pour vous aider à comprendre et à implémenter les entités et le formatage des graphiques. Alors, c'est parti !

## Prérequis

Avant de nous lancer dans la création de superbes graphiques avec Aspose.Slides pour .NET, vous devez vous assurer que vous disposez des conditions préalables suivantes :

1. Aspose.Slides pour .NET : Assurez-vous d'avoir installé la bibliothèque Aspose.Slides pour .NET. Vous pouvez la télécharger depuis le [site web](https://releases.aspose.com/slides/net/).

2. Environnement de développement : vous devez disposer d’un environnement de développement fonctionnel avec Visual Studio ou tout autre IDE prenant en charge le développement .NET.

3. Connaissances de base en C# : la familiarité avec la programmation C# est essentielle pour ce didacticiel.

Maintenant que nous avons trié nos prérequis, passons à la création de magnifiques graphiques avec Aspose.Slides pour .NET.

## Importer des espaces de noms

Tout d’abord, vous devez importer les espaces de noms nécessaires pour travailler avec Aspose.Slides pour .NET :

```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides.Charts;
```

## Étape 1 : Créer une présentation

Nous commençons par créer une nouvelle présentation. Cette présentation servira de canevas pour notre graphique.

```csharp
// Le chemin vers le répertoire des documents.
string dataDir = "Your Document Directory";

// Créez un répertoire s'il n'est pas déjà présent.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// Instanciation de la présentation
Presentation pres = new Presentation();
```

## Étape 2 : Accéder à la première diapositive

Accédons à la première diapositive de la présentation où nous placerons notre graphique.

```csharp
// Accéder à la première diapositive
ISlide slide = pres.Slides[0];
```

## Étape 3 : Ajouter un exemple de graphique

Nous allons maintenant ajouter un exemple de graphique à notre diapositive. Dans cet exemple, nous allons créer un graphique linéaire avec des marqueurs.

```csharp
// Ajout du graphique d'échantillon
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## Étape 4 : Définir le titre du graphique

Nous donnerons un titre à notre graphique, le rendant plus informatif et visuellement attrayant.

```csharp
// Titre du tableau de réglage
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

## Étape 5 : Personnaliser les lignes de la grille de l’axe vertical

Dans cette étape, nous allons personnaliser les lignes de la grille de l’axe vertical pour rendre notre graphique plus attrayant visuellement.

```csharp
// Définition du format des lignes principales de la grille pour l'axe des valeurs
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Blue;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.Width = 5;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.DashStyle = LineDashStyle.DashDot;

// Définition du format des lignes de grille mineures pour l'axe des valeurs
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Red;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.Width = 3;

// Format du numéro de l'axe des valeurs de réglage
chart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
chart.Axes.VerticalAxis.DisplayUnit = DisplayUnitType.Thousands;
chart.Axes.VerticalAxis.NumberFormat = "0.0%";
```

## Étape 6 : Définir la plage de l’axe vertical

Dans cette étape, nous allons définir les valeurs maximales, minimales et unitaires pour l’axe vertical.

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

## Étape 7 : Personnaliser le texte de l’axe vertical

Nous allons maintenant personnaliser l’apparence du texte sur l’axe vertical.

```csharp
// Définition des propriétés du texte de l'axe des valeurs
IChartPortionFormat txtVal = chart.Axes.VerticalAxis.TextFormat.PortionFormat;
txtVal.FontBold = NullableBool.True;
txtVal.FontHeight = 16;
txtVal.FontItalic = NullableBool.True;
txtVal.FillFormat.FillType = FillType.Solid;
txtVal.FillFormat.SolidFillColor.Color = Color.DarkGreen;
txtVal.LatinFont = new FontData("Times New Roman");

// Définition du titre de l'axe des valeurs
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

## Étape 8 : Personnaliser les lignes de la grille de l’axe horizontal

Maintenant, personnalisons les lignes de la grille pour l’axe horizontal.

```csharp
// Définition du format des lignes de grille principales pour l'axe des catégories
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Green;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.Width = 5;

// Définition du format des lignes de grille mineures pour l'axe des catégories
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Yellow;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.Width = 3;

// Définition des propriétés du texte de l'axe des catégories
IChartPortionFormat txtCat = chart.Axes.HorizontalAxis.TextFormat.PortionFormat;
txtCat.FontBold = NullableBool.True;
txtCat.FontHeight = 16;
txtCat.FontItalic = NullableBool.True;
txtCat.FillFormat.Fill

Type = FillType.Solid;
txtCat.FillFormat.SolidFillColor.Color = Color.Blue;
txtCat.LatinFont = new FontData("Arial");
```

## Étape 9 : Personnaliser les étiquettes de l’axe horizontal

Dans cette étape, nous allons ajuster la position et la rotation des étiquettes de l’axe horizontal.

```csharp
// Définition de la position de l'étiquette de l'axe des catégories
chart.Axes.HorizontalAxis.TickLabelPosition = TickLabelPositionType.Low;

// Définition de l'angle de rotation de l'étiquette de l'axe des catégories
chart.Axes.HorizontalAxis.TickLabelRotationAngle = 45;
```

## Étape 10 : Personnaliser les légendes

Améliorons les légendes de notre graphique pour une meilleure lisibilité.

```csharp
// Définition des propriétés du texte des légendes
IChartPortionFormat txtleg = chart.Legend.TextFormat.PortionFormat;
txtleg.FontBold = NullableBool.True;
txtleg.FontHeight = 16;
txtleg.FontItalic = NullableBool.True;
txtleg.FillFormat.FillType = FillType.Solid;
txtleg.FillFormat.SolidFillColor.Color = Color.DarkRed;

// Définir l'affichage des légendes du graphique sans chevauchement du graphique
chart.Legend.Overlay = true;
```

## Étape 11 : Personnaliser l’arrière-plan du graphique

Nous personnaliserons les couleurs d’arrière-plan du graphique, du mur arrière et du sol.

```csharp
// Tableau de réglage de la couleur du mur arrière
chart.BackWall.Thickness = 1;
chart.BackWall.Format.Fill.FillType = FillType.Solid;
chart.BackWall.Format.Fill.SolidFillColor.Color = Color.Orange;

chart.Floor.Format.Fill.FillType = FillType.Solid;
chart.Floor.Format.Fill.SolidFillColor.Color = Color.Red;

// Définition de la couleur de la zone de tracé
chart.PlotArea.Format.Fill.FillType = FillType.Solid;
chart.PlotArea.Format.Fill.SolidFillColor.Color = Color.LightCyan;
```

## Étape 12 : Enregistrer la présentation

Enfin, enregistrons notre présentation avec le graphique formaté.

```csharp
// Enregistrer la présentation
pres.Save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## Conclusion

Créer des graphiques attrayants et informatifs pour vos présentations est désormais plus facile que jamais avec Aspose.Slides pour .NET. Dans ce tutoriel, nous avons abordé les étapes essentielles pour personnaliser différents aspects d'un graphique et le rendre visuellement attrayant et informatif. Grâce à ces techniques, vous pouvez créer des graphiques percutants qui transmettent efficacement vos données à votre public.

Commencez à expérimenter avec Aspose.Slides pour .NET et faites passer votre visualisation de données au niveau supérieur !

## Questions fréquemment posées

### 1. Qu'est-ce qu'Aspose.Slides pour .NET ?

Aspose.Slides pour .NET est une bibliothèque puissante qui permet aux développeurs .NET de créer, manipuler et convertir des présentations Microsoft PowerPoint. Elle offre un large éventail de fonctionnalités pour travailler avec des diapositives, des formes, des graphiques, etc.

### 2. Où puis-je télécharger Aspose.Slides pour .NET ?

Vous pouvez télécharger Aspose.Slides pour .NET à partir du site Web [ici](https://releases.aspose.com/slides/net/).

### 3. Existe-t-il un essai gratuit disponible pour Aspose.Slides pour .NET ?

Oui, vous pouvez obtenir un essai gratuit d'Aspose.Slides pour .NET à partir de [ici](https://releases.aspose.com/).

### 4. Comment puis-je obtenir une licence temporaire pour Aspose.Slides pour .NET ?

Si vous avez besoin d'un permis temporaire, vous pouvez en obtenir un auprès de [ce lien](https://purchase.aspose.com/temporary-license/).

### 5. Existe-t-il une communauté ou un forum d'assistance pour Aspose.Slides pour .NET ?

Oui, vous pouvez trouver la communauté et le forum d'assistance Aspose.Slides [ici](https://forum.aspose.com/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}