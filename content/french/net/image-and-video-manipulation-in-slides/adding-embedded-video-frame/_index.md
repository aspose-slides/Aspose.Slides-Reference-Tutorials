---
title: Ajout d'une image vidéo intégrée dans les diapositives de présentation à l'aide d'Aspose.Slides
linktitle: Ajout d'une image vidéo intégrée dans les diapositives de présentation à l'aide d'Aspose.Slides
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez comment améliorer vos diapositives de présentation en ajoutant des images vidéo intégrées à l'aide d'Aspose.Slides pour .NET. Suivez ce guide étape par étape avec le code source complet pour intégrer de manière transparente des vidéos, personnaliser la lecture et créer des présentations captivantes.
type: docs
weight: 19
url: /fr/net/image-and-video-manipulation-in-slides/adding-embedded-video-frame/
---

## Introduction à Aspose.Slides pour .NET

Aspose.Slides for .NET est une bibliothèque polyvalente et riche en fonctionnalités qui permet aux développeurs de travailler avec des présentations PowerPoint par programme. Il offre un large éventail de fonctionnalités, notamment la création, l'édition, la conversion et la manipulation de présentations. Dans ce guide, nous nous concentrerons sur le processus d'intégration d'images vidéo dans les diapositives de présentation.

## Conditions préalables

Avant de nous lancer dans la mise en œuvre, assurez-vous que les conditions préalables suivantes sont en place :

- Visual Studio (ou tout autre environnement de développement .NET)
- Connaissance de base du langage de programmation C#
- Aspose.Slides pour la bibliothèque .NET

## Installation d'Aspose.Slides pour .NET

Pour commencer, vous devez installer la bibliothèque Aspose.Slides pour .NET. Vous pouvez télécharger la bibliothèque depuis le site Web ou utiliser un gestionnaire de packages comme NuGet. Voici comment l'installer à l'aide de NuGet :

```csharp
Install-Package Aspose.Slides
```

## Créer une nouvelle présentation

Commençons par créer une nouvelle présentation PowerPoint à l'aide d'Aspose.Slides. Voici un extrait de code de base pour créer une présentation :

```csharp
using Aspose.Slides;

// Créer une nouvelle présentation
Presentation presentation = new Presentation();
```

## Ajout d'une diapositive

Ensuite, nous ajouterons une nouvelle diapositive à la présentation. Les diapositives sont indexées à partir de zéro. Voici comment ajouter une diapositive :

```csharp
//Ajouter une nouvelle diapositive à la présentation
ISlide slide = presentation.Slides.AddEmptySlide(SlideLayout.Blank);
```

## Intégrer une vidéo

Vient maintenant la partie passionnante : intégrer une vidéo dans la diapositive. Vous devez disposer du chemin ou de l'URL du fichier vidéo pour continuer. Voici comment intégrer une vidéo dans la diapositive :

```csharp
// Chemin d'accès au fichier vidéo
string videoPath = "path_to_your_video.mp4";

// Ajouter la vidéo à la diapositive
IVideoFrame videoFrame = slide.Shapes.AddVideoFrame(100, 100, 480, 270, videoPath);
```

## Personnalisation du cadre vidéo

Vous pouvez personnaliser divers aspects de l'image vidéo, tels que sa taille, sa position et ses options de lecture. Voici un exemple de la façon de configurer le mode de lecture pour qu'il démarre automatiquement :

```csharp
// Définir le mode de lecture vidéo pour démarrer automatiquement
videoFrame.PlayMode = VideoPlayMode.Auto;
```

## Enregistrement et exportation de la présentation

Une fois que vous avez ajouté l'image vidéo et l'avez personnalisée à votre guise, il est temps d'enregistrer la présentation. Vous pouvez l'enregistrer dans différents formats, tels que PPTX ou PDF. Voici comment l'enregistrer en tant que fichier PPTX :

```csharp
// Enregistrez la présentation
presentation.Save("output.pptx", SaveFormat.Pptx);
```

## Conclusion

Dans ce guide, nous avons exploré comment améliorer vos diapositives de présentation en ajoutant des images vidéo intégrées à l'aide d'Aspose.Slides pour .NET. Cette puissante bibliothèque vous permet de créer des présentations dynamiques et engageantes qui laissent une impression durable sur votre public. En suivant les étapes décrites dans ce guide, vous pouvez intégrer en toute transparence du contenu multimédia dans vos diapositives et créer des présentations captivantes.

## FAQ

### Comment installer Aspose.Slides pour .NET ?

 Vous pouvez installer Aspose.Slides pour .NET à l'aide du gestionnaire de packages NuGet. Exécutez simplement la commande suivante dans votre console NuGet Package Manager :`Install-Package Aspose.Slides`

### Puis-je personnaliser l’apparence de l’image vidéo ?

Oui, vous pouvez personnaliser la taille, la position et les options de lecture de l'image vidéo à l'aide des propriétés fournies par la bibliothèque Aspose.Slides.

### Quels formats vidéo sont pris en charge pour l'intégration ?

Aspose.Slides prend en charge l'intégration de vidéos dans divers formats, notamment MP4, AVI et WMV.

### Puis-je contrôler le moment où la lecture de la vidéo commence ?

Absolument! Vous pouvez définir le mode de lecture de l'image vidéo pour qu'il démarre automatiquement ou manuellement, selon vos préférences.

### Aspose.Slides sert-il uniquement à ajouter des vidéos ?

Non, Aspose.Slides offre un large éventail de fonctionnalités au-delà de l'ajout de vidéos. Il vous permet de créer, modifier, convertir et manipuler des présentations PowerPoint par programme.