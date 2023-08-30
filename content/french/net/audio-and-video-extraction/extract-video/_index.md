---
title: Extraire la vidéo de la diapositive
linktitle: Extraire la vidéo de la diapositive
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Maîtrisez l'extraction vidéo à partir de diapositives PowerPoint à l'aide d'Aspose.Slides pour .NET. Suivez notre guide avec des exemples de code.
type: docs
weight: 14
url: /fr/net/audio-and-video-extraction/extract-video/
---

## Introduction

Dans le monde numérique d'aujourd'hui, les présentations multimédias sont devenues un élément essentiel de la communication. Les présentations PowerPoint incluent souvent un mélange de texte, d'images et de vidéos pour transmettre des informations efficacement. Cependant, il peut arriver que vous ayez besoin d'extraire une vidéo d'une diapositive à diverses fins, telles que l'archivage, le partage ou une modification ultérieure. C'est là qu'Aspose.Slides pour .NET entre en jeu.

## Conditions préalables

Avant de plonger dans le guide étape par étape, assurez-vous que les conditions préalables suivantes sont en place :

- Connaissance de base de C# et du framework .NET
- Visual Studio installé
-  Bibliothèque Aspose.Slides pour .NET (téléchargement depuis[ici](https://releases.aspose.com/slides/net)

## Guide étape par étape

Passons en revue le processus d'extraction d'une vidéo d'une diapositive à l'aide d'Aspose.Slides pour .NET :

### Étape 1 : Installation

1. Ouvrez Visual Studio et créez un nouveau projet C#.
2. Cliquez avec le bouton droit sur votre projet dans l'Explorateur de solutions et sélectionnez « Gérer les packages NuGet ».
3. Recherchez « Aspose.Slides » et installez la dernière version.

### Étape 2 : Charger la présentation

```csharp
using Aspose.Slides;

// Charger la présentation
using var presentation = new Presentation("your-presentation.pptx");
```

 Remplacer`"your-presentation.pptx"` avec le chemin réel vers votre fichier de présentation PowerPoint.

### Étape 3 : Extraire la vidéo

```csharp
// Obtenez la première diapositive
var slide = presentation.Slides[0];

// Parcourir les formes de diapositives
foreach (var shape in slide.Shapes)
{
    if (shape is IVideoFrame videoFrame)
    {
        // Extraire la vidéo de l'image vidéo
        var video = videoFrame.EmbeddedVideo;
        // Un traitement ultérieur peut être effectué avec l'objet vidéo
    }
}
```

### Étape 4 : Enregistrer la vidéo

```csharp
// Enregistrez la vidéo extraite
video.WriteToFile("extracted-video.mp4");
```

 Remplacer`"extracted-video.mp4"` avec le nom et le chemin souhaités pour le fichier vidéo extrait.

## Conclusion

Aspose.Slides pour .NET simplifie la tâche d'extraction de vidéos à partir de présentations PowerPoint. Avec seulement quelques lignes de code, vous pouvez récupérer des vidéos intégrées dans des diapositives et les enregistrer sous forme de fichiers vidéo distincts. Que vous cherchiez à réutiliser du contenu ou à créer des compilations, cette bibliothèque offre une solution transparente.

## FAQ

### Comment puis-je accéder à la documentation Aspose.Slides ?

 Vous pouvez vous référer à la documentation d'Aspose.Slides pour .NET à l'adresse[ici](https://reference.aspose.com/slides/net/).

### Aspose.Slides est-il disponible pour d’autres langages de programmation ?

Oui, Aspose.Slides est disponible pour plusieurs langages de programmation, dont Java. Vous pouvez trouver les bibliothèques appropriées sur le site Web Aspose.

### Puis-je extraire l’audio en utilisant la même approche ?

Non, l'exemple fourni concerne spécifiquement l'extraction de vidéos. Pour extraire l'audio, vous devrez modifier le code pour fonctionner avec les images audio.

### Y a-t-il des frais de licence pour l'utilisation d'Aspose.Slides ?

Oui, Aspose.Slides est un produit commercial. Vous pouvez trouver des informations détaillées sur les licences et les tarifs sur le site Web Aspose.

### Comment accéder aux propriétés de la vidéo extraite ?

 Le`EmbeddedVideo` objet obtenu à partir du`IVideoFrame` donne accès à diverses propriétés de la vidéo, telles que la durée, la résolution, etc.