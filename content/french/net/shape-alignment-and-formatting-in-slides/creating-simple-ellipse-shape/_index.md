---
title: Création d'une forme d'ellipse simple dans des diapositives de présentation avec Aspose.Slides
linktitle: Création d'une forme d'ellipse simple dans des diapositives de présentation avec Aspose.Slides
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez comment créer une forme d'ellipse simple dans des diapositives de présentation à l'aide d'Aspose.Slides pour .NET. Ce guide étape par étape fournit le code source et les instructions pour ajouter, personnaliser et enregistrer des formes d'ellipse.
type: docs
weight: 11
url: /fr/net/shape-alignment-and-formatting-in-slides/creating-simple-ellipse-shape/
---

## Introduction à la création d'une forme d'ellipse simple dans les diapositives de présentation

Si vous souhaitez améliorer vos diapositives de présentation en ajoutant des formes visuellement attrayantes, Aspose.Slides for .NET fournit une solution puissante pour y parvenir. Dans ce guide étape par étape, nous vous guiderons tout au long du processus de création d'une forme d'ellipse simple dans vos diapositives de présentation à l'aide d'Aspose.Slides pour .NET.

## Conditions préalables

Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :

- Visual Studio ou tout autre environnement de développement .NET installé.
-  Aspose.Slides pour la bibliothèque .NET. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/slides/net/).

## Mise en place de votre projet

1. Créez un nouveau projet Visual Studio ou ouvrez-en un existant.
2. Ajoutez une référence à la bibliothèque Aspose.Slides for .NET dans votre projet.

## Créer une présentation

Pour commencer, créons une nouvelle présentation dans laquelle nous ajouterons notre forme d'ellipse.

```csharp
using Aspose.Slides;

// Créer une nouvelle présentation
Presentation presentation = new Presentation();
```

## Ajout d'une forme d'ellipse

Maintenant que notre présentation est prête, ajoutons une forme d'ellipse à une diapositive.

```csharp
// Accédez à la première diapositive de la présentation
ISlide slide = presentation.Slides[0];

// Définir les dimensions et la position de l'ellipse
float x = 100;   // Coordonnée X
float y = 100;   // Coordonnée Y
float width = 200;  // Largeur
float height = 100; // Hauteur

// Ajouter la forme d'ellipse à la diapositive
IAutoShape ellipseShape = slide.Shapes.AddAutoShape(ShapeType.Ellipse, x, y, width, height);
```

## Personnalisation de l'ellipse

Vous pouvez personnaliser l’apparence de la forme elliptique à l’aide de diverses propriétés.

```csharp
// Définir la couleur de remplissage de l'ellipse
ellipseShape.FillFormat.SolidFillColor.Color = Color.Blue;

//Définir la couleur et la largeur du contour
ellipseShape.LineFormat.FillFormat.SolidFillColor.Color = Color.Red;
ellipseShape.LineFormat.Width = 2;

// Ajouter un cadre de texte à l'ellipse
ITextFrame textFrame = ellipseShape.TextFrame;
textFrame.Text = "Hello, Aspose.Slides!";
```

## Sauvegarde de la présentation

Après avoir ajouté et personnalisé la forme de l'ellipse, il est temps de sauvegarder la présentation.

```csharp
// Enregistrez la présentation
presentation.Save("EllipsePresentation.pptx", SaveFormat.Pptx);
```

## Conclusion

Toutes nos félicitations! Vous avez réussi à créer une forme d'ellipse simple dans vos diapositives de présentation à l'aide d'Aspose.Slides pour .NET. Ce guide a couvert le processus de configuration de votre projet, de création d'une présentation, d'ajout d'une forme d'ellipse, de personnalisation de son apparence et d'enregistrement de la présentation finale.

## FAQ

### Comment puis-je modifier la position de la forme de l'ellipse ?

 Vous pouvez modifier le`x` et`y` coordonnées lors de l’ajout de la forme d’ellipse pour ajuster sa position sur la diapositive.

### Puis-je changer la couleur du contour de l'ellipse ?

 Oui, vous pouvez définir la couleur du contour à l'aide du`LineFormat.FillFormat.SolidFillColor.Color` propriété.

### Est-il possible d'ajouter du texte à l'intérieur de l'ellipse ?

 Absolument! Vous pouvez ajouter du texte à la forme de l'ellipse à l'aide de l'icône`TextFrame.Text` propriété.

### Quelles autres formes puis-je créer à l’aide d’Aspose.Slides pour .NET ?

Aspose.Slides pour .NET prend en charge diverses formes, notamment des rectangles, des lignes, des flèches, etc.

### Où puis-je trouver plus d’informations sur Aspose.Slides pour .NET ?

 Pour une documentation détaillée et des exemples, reportez-vous au[Aspose.Slides pour la documentation .NET](https://reference.aspose.com/slides/net/).