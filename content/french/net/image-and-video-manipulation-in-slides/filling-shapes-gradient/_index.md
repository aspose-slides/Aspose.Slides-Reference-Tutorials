---
title: Remplissage de formes avec dégradé dans les diapositives de présentation à l'aide d'Aspose.Slides
linktitle: Remplissage de formes avec dégradé dans les diapositives de présentation à l'aide d'Aspose.Slides
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Apprenez à améliorer vos diapositives de présentation avec des dégradés captivants à l'aide d'Aspose.Slides pour .NET. Suivez ce guide étape par étape avec le code source complet pour remplir les formes avec des dégradés, du linéaire au radial, en ajoutant de la profondeur et de la dimension.
type: docs
weight: 21
url: /fr/net/image-and-video-manipulation-in-slides/filling-shapes-gradient/
---

## Introduction à Aspose.Slides pour .NET

Aspose.Slides for .NET est une bibliothèque puissante qui permet aux développeurs de créer, manipuler et convertir des présentations PowerPoint par programme. Il offre un large éventail de fonctionnalités pour travailler avec des diapositives, des formes, du texte, des images, etc. Dans ce guide, nous nous concentrerons sur la façon d'utiliser Aspose.Slides pour appliquer des dégradés aux formes dans une présentation.

## Ajout de formes aux diapositives

Avant de nous plonger dans les dégradés, commençons par ajouter des formes aux diapositives à l'aide d'Aspose.Slides. Voici un exemple simple d'ajout d'une forme de rectangle à une diapositive :

```csharp
// Ajouter une nouvelle forme de rectangle à la diapositive
var slide = presentation.Slides[0];
var rectangle = slide.Shapes.AddRectangle(100, 100, 200, 150);
```

## Comprendre les dégradés

Les dégradés sont des mélanges progressifs de deux couleurs ou plus qui créent une transition douce entre elles. Ils peuvent être linéaires ou radiaux et ajoutent de la profondeur et de la dimension aux formes.

## Remplissage de formes avec des dégradés linéaires

 Pour remplir une forme avec un dégradé linéaire à l'aide d'Aspose.Slides, vous devez créer un`LinearGradientFill` objet et appliquez-le à la forme. Voici un exemple :

```csharp
// Créer un remplissage dégradé linéaire
var gradientFill = new LinearGradientFill();
gradientFill.Angle = 45; // Définir l'angle du dégradé

// Ajouter des points de dégradé
gradientFill.GradientStops.Add(0, Color.Blue);
gradientFill.GradientStops.Add(1, Color.White);

// Appliquer le remplissage dégradé à la forme
rectangle.FillFormat.FillType = FillType.Gradient;
rectangle.FillFormat.GradientFormat.GradientShape = GradientShape.Linear;
rectangle.FillFormat.GradientFormat.LinearGradientFormat = gradientFill;
```

## Application de dégradés radiaux aux formes

Les dégradés radiaux créent un mélange circulaire de couleurs, rayonnant à partir d'un point central. Voici comment appliquer un remplissage dégradé radial à l'aide d'Aspose.Slides :

```csharp
// Créer un remplissage dégradé radial
var gradientFill = new RadialGradientFill();

// Ajouter des points de dégradé
gradientFill.GradientStops.Add(0, Color.Green);
gradientFill.GradientStops.Add(1, Color.Yellow);

// Appliquer le remplissage dégradé à la forme
rectangle.FillFormat.FillType = FillType.Gradient;
rectangle.FillFormat.GradientFormat.GradientShape = GradientShape.Radial;
rectangle.FillFormat.GradientFormat.RadialGradientFormat = gradientFill;
```

## Combiner dégradés et transparence

Vous pouvez améliorer l'impact visuel des dégradés en appliquant de la transparence à la forme. Cela crée un mélange élégant de couleurs et permet à l’arrière-plan de transparaître légèrement.

```csharp
// Appliquer de la transparence à la forme
rectangle.FillFormat.Transparency = 0.5; //Ajuster le niveau de transparence
```

## Travailler avec plusieurs arrêts de dégradé

Les points de dégradé définissent les couleurs et les positions dans un dégradé. En ajoutant plusieurs points de dégradé, vous pouvez créer des dégradés plus complexes et visuellement attrayants.

```csharp
// Ajouter plusieurs arrêts de dégradé
gradientFill.GradientStops.Add(0, Color.Red);
gradientFill.GradientStops.Add(0.5, Color.Yellow);
gradientFill.GradientStops.Add(1, Color.Blue);
```

## Ajouter du code source à votre projet

 Pour utiliser Aspose.Slides pour .NET, vous devez ajouter la bibliothèque à votre projet. Vous pouvez télécharger la bibliothèque sur le site :[Téléchargez Aspose.Slides pour .NET](https://releases.aspose.com/slides/net/).

## Compilation et exécution du projet

Une fois que vous avez ajouté la bibliothèque Aspose.Slides à votre projet, vous pouvez commencer à écrire du code pour créer et manipuler des diapositives de présentation. Assurez-vous d'inclure les espaces de noms nécessaires :

```csharp
using Aspose.Slides;
using Aspose.Slides.Fill;
```

## Personnalisations et effets supplémentaires

 Aspose.Slides propose diverses options et effets de personnalisation que vous pouvez appliquer aux formes et aux dégradés. Explorez la documentation pour des fonctionnalités plus avancées :[Documentation Aspose.Slides pour .NET](https://reference.aspose.com/slides/net/).

## Exporter la présentation

Après avoir appliqué des dégradés et des personnalisations à votre présentation, vous pouvez l'enregistrer dans différents formats, tels que PPTX ou PDF :

```csharp
// Enregistrer la présentation dans un fichier
presentation.Save("MyPresentation.pptx", SaveFormat.Pptx);
```

## Conclusion

Remplir des formes avec des dégradés peut rehausser l'attrait visuel de vos diapositives de présentation, les rendant plus attrayantes et visuellement impressionnantes. Aspose.Slides pour .NET fournit les outils dont vous avez besoin pour appliquer facilement des dégradés, vous permettant de créer des présentations époustouflantes qui captivent votre public.

## FAQ

### Comment télécharger Aspose.Slides pour .NET ?

 Vous pouvez télécharger la bibliothèque Aspose.Slides pour .NET à partir de la page des versions :[Téléchargez Aspose.Slides pour .NET](https://releases.aspose.com/slides/net/).

### Puis-je appliquer de la transparence à des formes remplies de dégradé ?

 Oui, vous pouvez appliquer de la transparence aux formes remplies de dégradés à l'aide de l'option`Transparency` propriété du`FillFormat`.

### Les dégradés radiaux sont-ils meilleurs que les dégradés linéaires ?

Le choix entre les dégradés radiaux et linéaires dépend du design et de l'effet que vous souhaitez obtenir. Les dégradés radiaux créent un mélange circulaire, tandis que les dégradés linéaires créent une transition linéaire douce entre les couleurs.

### Puis-je personnaliser la position des points de dégradé ?

Oui, vous pouvez personnaliser la position et la couleur des arrêts de dégradé dans un remplissage dégradé. Cela vous permet de créer des effets de dégradé uniques et complexes.

### Aspose.Slides est-il adapté à d’autres manipulations PowerPoint ?

Oui, Aspose.Slides offre un large éventail de fonctionnalités pour travailler avec des présentations PowerPoint, notamment l'ajout de diapositives, de texte, d'images, d'animations, etc.