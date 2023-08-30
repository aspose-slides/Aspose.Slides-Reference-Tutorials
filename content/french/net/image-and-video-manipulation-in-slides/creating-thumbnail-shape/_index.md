---
title: Création d'une vignette pour la forme dans Aspose.Slides
linktitle: Création d'une vignette pour la forme dans Aspose.Slides
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez comment créer des miniatures pour les formes dans des présentations PowerPoint à l'aide d'Aspose.Slides pour .NET. Ce guide étape par étape fournit des exemples de code pratiques, du chargement de présentations à la génération et à l'enregistrement de vignettes.
type: docs
weight: 14
url: /fr/net/image-and-video-manipulation-in-slides/creating-thumbnail-shape/
---

## Introduction

Aspose.Slides for .NET est une bibliothèque riche en fonctionnalités qui permet aux développeurs de travailler de manière transparente avec des présentations PowerPoint. Une exigence courante consiste à générer des vignettes pour des formes spécifiques dans les diapositives. Cela peut être particulièrement utile lorsque vous souhaitez fournir un aperçu rapide ou une représentation d'une forme dans votre application.

## Conditions préalables

Avant de plonger dans le code, assurez-vous que les conditions préalables suivantes sont en place :

- Visual Studio ou tout autre environnement de développement .NET approprié.
-  Aspose.Slides pour la bibliothèque .NET. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/slides/net/).

## Installation

1. Téléchargez la bibliothèque Aspose.Slides pour .NET à partir du lien fourni.
2. Installez la bibliothèque dans votre projet .NET en ajoutant une référence à la DLL téléchargée.

## Chargement d'une présentation

Commençons par charger une présentation PowerPoint à l'aide d'Aspose.Slides. Le code suivant montre comment charger une présentation à partir d'un fichier :

```csharp
using Aspose.Slides;

// Charger la présentation
using var presentation = new Presentation("sample.pptx");
```

 Remplacer`"sample.pptx"` avec le chemin réel de votre présentation PowerPoint.

## Accéder aux formes

Une fois la présentation chargée, vous pouvez accéder aux formes de chaque diapositive. Dans cet exemple, nous nous concentrerons sur la génération d'une vignette pour une forme spécifique sur une diapositive particulière. Voici comment accéder à une forme :

```csharp
// Accéder à une diapositive par index (basé sur 0)
var slide = presentation.Slides[0];

// Accéder à une forme par index (basé sur 0)
var shape = slide.Shapes[0];
```

Modifiez les index des diapositives et des formes en fonction de la structure de votre présentation.

## Création de vignettes

 Vient maintenant la partie passionnante : créer une vignette pour la forme sélectionnée. Aspose.Slides vous permet d'y parvenir en tirant parti de`GetThumbnail` méthode. Voici comment créer une miniature pour une forme :

```csharp
// Définir les dimensions des vignettes
int thumbnailWidth = 200;
int thumbnailHeight = 150;

// Générer une vignette pour la forme
var thumbnail = shape.GetThumbnail(thumbnailWidth, thumbnailHeight);
```

 Ajuste le`thumbnailWidth` et`thumbnailHeight` variables pour définir les dimensions souhaitées pour votre vignette.

## Enregistrer les vignettes

Après avoir généré la vignette, vous souhaiterez peut-être l'enregistrer en tant que fichier image. Voici comment enregistrer la vignette sous forme d'image PNG :

```csharp
// Enregistrer la vignette en tant qu'image
thumbnail.Save("shape_thumbnail.png", ImageFormat.Png);
```

Personnalisez le nom et le format du fichier selon vos besoins.

## Conclusion

Dans ce guide, nous avons expliqué comment créer des vignettes pour les formes dans les présentations PowerPoint à l'aide d'Aspose.Slides pour .NET. Vous avez appris à charger une présentation, à accéder à des formes, à générer des vignettes et à les enregistrer sous forme de fichiers image. Cette fonctionnalité peut considérablement améliorer l'expérience utilisateur dans les applications impliquant des présentations PowerPoint.

## FAQ

### Comment puis-je spécifier différentes dimensions de miniature ?

 Vous pouvez ajuster le`thumbnailWidth` et`thumbnailHeight` variables dans le code pour spécifier les dimensions dont vous avez besoin pour la vignette générée.

### Puis-je créer des miniatures pour plusieurs formes à la fois ?

Oui, vous pouvez parcourir toutes les formes d'une diapositive et générer des vignettes pour chaque forme à l'aide d'une boucle.

### Aspose.Slides est-il compatible avec différents formats PowerPoint ?

Oui, Aspose.Slides prend en charge divers formats PowerPoint, notamment PPTX, PPT, etc.

### Puis-je personnaliser l'apparence de la vignette générée ?

 Tandis que le`GetThumbnail` fournit un moyen rapide de générer des vignettes, vous pouvez manipuler davantage l'image miniature à l'aide des bibliothèques de traitement d'image standard dans .NET.

### Aspose.Slides est-il adapté à d’autres tâches liées à PowerPoint ?

Absolument, Aspose.Slides offre un large éventail de fonctionnalités pour travailler avec des présentations PowerPoint, notamment la création, l'édition, la conversion et le rendu de diapositives.