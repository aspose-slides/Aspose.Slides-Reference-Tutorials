---
title: Création d'une vignette avec un facteur d'échelle pour la forme dans Aspose.Slides
linktitle: Création d'une vignette avec un facteur d'échelle pour la forme dans Aspose.Slides
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Apprenez à créer des présentations attrayantes à l'aide d'Aspose.Slides pour .NET ! Suivez notre guide étape par étape avec le code source complet pour créer des vignettes avec des facteurs de mise à l'échelle pour les formes.
type: docs
weight: 12
url: /fr/net/image-and-video-manipulation-in-slides/creating-thumbnail-scaling-factor-shape/
---

# Introduction à la création d'une vignette avec un facteur d'échelle pour la forme

Dans le monde en évolution rapide d’aujourd’hui, le contenu visuel joue un rôle crucial dans une communication efficace. Les présentations, qu'elles soient commerciales, éducatives ou de divertissement, s'appuient souvent sur des visuels captivants pour transmettre des idées. Aspose.Slides pour .NET offre une solution puissante pour améliorer votre processus de création de présentation en fournissant des outils pour manipuler et personnaliser des formes, des images et d'autres éléments. Dans ce guide étape par étape, nous découvrirons comment créer une miniature d'une forme avec un facteur de mise à l'échelle spécifique à l'aide d'Aspose.Slides pour .NET.

## Conditions préalables

Avant de nous lancer dans la mise en œuvre, assurez-vous que les conditions préalables suivantes sont en place :

- Visual Studio installé sur votre système.
- Connaissance de base de la programmation C#.
-  Aspose.Slides pour la bibliothèque .NET. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/slides/net/).

## Mise en place du projet

1. Ouvrez Visual Studio et créez un nouveau projet. Choisissez le modèle de projet approprié (par exemple, application console).
2. Nommez votre projet et spécifiez l'emplacement où vous souhaitez l'enregistrer.
3. Cliquez sur "Créer" pour générer le projet.

## Ajout d'Aspose.Slides au projet

1. Cliquez avec le bouton droit sur votre projet dans l'Explorateur de solutions.
2. Sélectionnez « Gérer les packages NuGet… »
3. Recherchez « Aspose.Slides » et installez le package.

## Chargement d'une présentation

Pour commencer, vous avez besoin d’une présentation PowerPoint avec laquelle travailler. Supposons que vous ayez une présentation nommée « sample.pptx ».

```csharp
using Aspose.Slides;

// Charger la présentation
using var presentation = new Presentation("sample.pptx");
```

## Accès et modification des formes

Avant de créer une vignette, vous devez accéder à la forme que vous souhaitez modifier. Les formes dans Aspose.Slides sont organisées en collections de diapositives.

```csharp
// Accédez à la première diapositive
var slide = presentation.Slides[0];

// Accédez à la forme (supposons que ce soit un rectangle)
var shape = slide.Shapes[0];
```

## Création d'une vignette avec facteur d'échelle

Vient maintenant la partie passionnante : créer une vignette avec un facteur d’échelle spécifique. Cela implique de créer une copie de la forme originale et d'ajuster sa taille.

```csharp
// Créer une copie de la forme
var thumbnailShape = shape.Clone();

// Définir le facteur d'échelle (par exemple, 0,5 pour 50 %)
double scalingFactor = 0.5;

// Ajuster la largeur et la hauteur de la vignette
thumbnailShape.Width *= scalingFactor;
thumbnailShape.Height *= scalingFactor;
```

## Enregistrement de la présentation modifiée

Après avoir créé la vignette, vous pouvez enregistrer la présentation modifiée.

```csharp
// Ajouter la forme modifiée à la diapositive
slide.Shapes.AddClone(thumbnailShape);

// Enregistrez la présentation
presentation.Save("modified_sample.pptx", SaveFormat.Pptx);
```

## Conclusion

Dans ce guide, nous avons expliqué comment utiliser Aspose.Slides pour .NET pour créer une miniature d'une forme avec un facteur d'échelle spécifique. Nous avons couvert l'ensemble du processus, depuis la configuration du projet et le chargement d'une présentation jusqu'à l'accès et la modification des formes. La manipulation du contenu visuel est désormais à portée de main, vous permettant de créer des présentations attrayantes qui transmettent efficacement votre message.

## FAQ

### Comment puis-je télécharger la bibliothèque Aspose.Slides pour .NET ?

 Vous pouvez télécharger la bibliothèque Aspose.Slides pour .NET à partir de[ici](https://releases.aspose.com/slides/net/).

### Puis-je appliquer le facteur d’échelle à d’autres types de formes, tels que des cercles ?

Oui, vous pouvez appliquer le facteur d'échelle à différents types de formes, notamment des cercles, des rectangles, etc.

### Aspose.Slides est-il compatible avec différentes versions de PowerPoint ?

Oui, Aspose.Slides génère des présentations compatibles avec différentes versions de Microsoft PowerPoint.

### Puis-je créer des vignettes avec différents facteurs d’échelle pour plusieurs formes ?

Absolument! Vous pouvez répéter le processus pour chaque forme pour laquelle vous souhaitez créer une miniature, en ajustant le facteur de mise à l'échelle si nécessaire.

### Aspose.Slides prend-il en charge d’autres langages de programmation que C# ?

Oui, Aspose.Slides prend en charge plusieurs langages de programmation, notamment Java, Python, etc. Consultez la documentation pour plus de détails.