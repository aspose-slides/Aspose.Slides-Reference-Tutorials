---
title: Extraire l'audio de la chronologie
linktitle: Extraire l'audio de la chronologie
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez comment extraire l'audio des chronologies PowerPoint à l'aide d'Aspose.Slides pour .NET. Un guide étape par étape avec des exemples de code.
type: docs
weight: 13
url: /fr/net/audio-and-video-extraction/extract-audio-from-timeline/
---

## Introduction à Aspose.Slides pour .NET

Aspose.Slides pour .NET est une bibliothèque complète qui permet aux développeurs de créer, modifier, convertir et manipuler des présentations PowerPoint sans nécessiter l'installation de Microsoft Office. Il prend en charge un large éventail de fonctionnalités, notamment l'accès à des éléments de présentation tels que des diapositives, des formes, du texte, des images et même de l'audio. Dans ce guide, nous nous concentrerons sur l'extraction audio de la chronologie d'une présentation.

## Comprendre la chronologie dans les présentations PowerPoint

La chronologie d'une présentation PowerPoint représente la séquence d'événements, d'animations et d'éléments multimédias. Cela inclut les pistes audio synchronisées avec les diapositives. Aspose.Slides vous permet d'accéder et d'extraire ces pistes audio par programme.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Visual Studio ou tout environnement de développement .NET compatible
-  Bibliothèque Aspose.Slides. Vous pouvez le télécharger depuis[ici](https://downloads.aspose.com/slides/net)

## Étape 1 : Installation de la bibliothèque Aspose.Slides

1. Téléchargez la bibliothèque Aspose.Slides à partir du lien fourni.
2. Installez la bibliothèque dans votre projet .NET en ajoutant la référence à l'assembly Aspose.Slides.

## Étape 2 : chargement de la présentation

Pour extraire l'audio d'une présentation, vous devez d'abord charger le fichier PowerPoint. Voici comment procéder :

```csharp
using Aspose.Slides;

// Charger la présentation
using var presentation = new Presentation("presentation.pptx");
```

## Étape 3 : accéder à la chronologie

Après avoir chargé la présentation, vous pouvez accéder à la timeline et à ses pistes audio associées :

```csharp
// Accédez à la première diapositive
var slide = presentation.Slides[0];

//Accéder à la chronologie de la diapositive
var timeline = slide.Timeline;
```

## Étape 4 : Extraire l'audio de la timeline

Maintenant que vous avez accès à la timeline, vous pouvez extraire l'audio :

```csharp
foreach (var timeLineShape in timeline.Shapes)
{
    if (timeLineShape.MediaType == MediaType.Audio)
    {
        var audio = (IAudioFrame)timeLineShape;
        // Extrayez le code de traitement audio ici
    }
}
```

## Étape 5 : Sauvegarde de l'audio extrait

Une fois que vous avez extrait l'audio, vous pouvez l'enregistrer dans le format souhaité :

```csharp
audio.AudioData.WriteToFile("extracted_audio.mp3");
```

## Conclusion

Dans ce didacticiel, nous avons expliqué comment extraire l'audio de la chronologie d'une présentation PowerPoint à l'aide d'Aspose.Slides pour .NET. Nous avons couvert les étapes depuis le chargement de la présentation jusqu'à l'accès à la chronologie et enfin à l'extraction de l'audio. Aspose.Slides simplifie ce processus, facilitant l'utilisation par programme de divers éléments multimédias dans des présentations PowerPoint.

## FAQ

### Comment puis-je installer la bibliothèque Aspose.Slides ?

 Vous pouvez télécharger la bibliothèque Aspose.Slides à partir de[ici](https://downloads.aspose.com/slides/net). Après le téléchargement, ajoutez une référence à l'assembly Aspose.Slides dans votre projet .NET.

### Puis-je extraire l’audio de n’importe quelle diapositive de la présentation ?


Oui, vous pouvez extraire l'audio de la chronologie de n'importe quelle diapositive de la présentation à l'aide d'Aspose.Slides pour .NET.

### Dans quels formats puis-je enregistrer l'audio extrait ?

Aspose.Slides vous permet d'enregistrer l'audio extrait dans différents formats, tels que MP3, WAV, etc.

### Dois-je installer Microsoft Office pour utiliser Aspose.Slides ?

Non, vous n'avez pas besoin d'installer Microsoft Office. Aspose.Slides pour .NET fournit toutes les fonctionnalités nécessaires pour travailler avec des présentations PowerPoint par programme.

### Aspose.Slides est-il adapté aux projets commerciaux ?

Oui, Aspose.Slides convient aux projets personnels et commerciaux. Il offre un large éventail de fonctionnalités pour gérer les présentations PowerPoint par programmation.