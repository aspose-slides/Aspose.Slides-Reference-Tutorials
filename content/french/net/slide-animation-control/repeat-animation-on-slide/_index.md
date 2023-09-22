---
title: Répéter l'animation sur la diapositive
linktitle: Répéter l'animation sur la diapositive
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez comment répéter des animations sur une diapositive à l'aide d'Aspose.Slides pour .NET. Ce guide étape par étape fournit le code source et des instructions claires pour ajouter par programme des animations captivantes aux présentations PowerPoint.
type: docs
weight: 12
url: /fr/net/slide-animation-control/repeat-animation-on-slide/
---

## Introduction à Aspose.Slides pour .NET

Aspose.Slides for .NET est une bibliothèque robuste qui permet aux développeurs de créer, manipuler et convertir des présentations PowerPoint à l'aide du framework .NET. Il offre un large éventail de fonctionnalités pour travailler avec des diapositives, des formes, du texte, des images, des animations, etc.

## Configuration de votre environnement de développement

Avant de commencer, vous devez configurer votre environnement de développement. Suivez ces étapes:

1.  Téléchargez et installez Visual Studio à partir de[Téléchargements de Visual Studio](https://visualstudio.microsoft.com/downloads/).
2. Créez un nouveau projet .NET (application console, par exemple) dans Visual Studio.

## Chargement d'une présentation PowerPoint

Pour commencer, vous aurez besoin d’une présentation PowerPoint avec laquelle travailler. Assurez-vous d'avoir un fichier PowerPoint prêt.

```csharp
using Aspose.Slides;

// Charger la présentation PowerPoint
using var presentation = new Presentation("presentation.pptx");
```

## Accéder et modifier des animations

Maintenant que notre présentation est chargée, accédons et modifions les animations sur une diapositive spécifique. Pour cet exemple, supposons que nous souhaitions répéter les animations de la diapositive numéro 2.

```csharp
// Accéder à la diapositive par index (basé sur 0)
var slideIndex = 1;
var slide = presentation.Slides[slideIndex];

// Accéder aux animations du slide
var animations = slide.Timeline.MainSequence;
```

## Répéter des animations sur une diapositive

Pour répéter des animations, nous allons cloner et ajouter à nouveau les animations à la diapositive. Cela créera un effet de boucle. Voici comment y parvenir :

```csharp
// Cloner des animations et les ajouter à nouveau
var clonedAnimations = animations.CloneSequence();
animations.AddSequence(clonedAnimations);
```

## Test et exportation de la présentation modifiée

Après avoir modifié les animations, il est temps de tester la présentation et de l'exporter. Vous pouvez l'exporter vers différents formats tels que PPTX, PDF ou images.

```csharp
// Enregistrez la présentation modifiée
presentation.Save("modified_presentation.pptx", SaveFormat.Pptx);
```

## Conclusion

Dans ce guide, nous avons exploré comment répéter des animations sur une diapositive à l'aide d'Aspose.Slides pour .NET. Nous avons commencé par présenter la bibliothèque et configurer l'environnement de développement. Ensuite, nous avons chargé une présentation PowerPoint, accédé et modifié des animations, et enfin, implémenté la fonctionnalité de répétition d'animation. Aspose.Slides pour .NET permet aux développeurs de créer des présentations dynamiques et attrayantes par programmation.

## FAQ

### Comment puis-je télécharger Aspose.Slides pour .NET ?

 Vous pouvez télécharger Aspose.Slides pour .NET à partir de la page des versions :[Téléchargez Aspose.Slides pour .NET](https://releases.aspose.com/slides/net/)

### Puis-je répéter des animations spécifiques au lieu de toutes les animations d’une diapositive ?

 Oui, vous pouvez répéter sélectivement des animations spécifiques en les ciblant à l'aide de leur index dans le`MainSequence`.

### Aspose.Slides pour .NET est-il compatible avec différents formats PowerPoint ?

Oui, Aspose.Slides pour .NET prend en charge divers formats PowerPoint, notamment PPT, PPTX, etc.

### Puis-je créer des animations personnalisées à l’aide d’Aspose.Slides pour .NET ?

Absolument! Aspose.Slides pour .NET fournit des API complètes pour créer et personnaliser des animations en fonction de vos besoins.

### Existe-t-il une version d’essai disponible pour Aspose.Slides pour .NET ?

Oui, vous pouvez essayer Aspose.Slides pour .NET en téléchargeant la version d'essai gratuite sur le site Web.