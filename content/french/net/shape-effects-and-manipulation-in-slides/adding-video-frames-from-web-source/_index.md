---
title: Ajout d'images vidéo à partir d'une source Web dans des diapositives de présentation avec Aspose.Slides
linktitle: Ajout d'images vidéo à partir d'une source Web dans des diapositives de présentation avec Aspose.Slides
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez comment améliorer vos diapositives de présentation en ajoutant des images vidéo à partir de sources Web à l'aide d'Aspose.Slides pour .NET. Créez des présentations multimédia attrayantes avec des instructions étape par étape et des exemples de code source.
type: docs
weight: 20
url: /fr/net/shape-effects-and-manipulation-in-slides/adding-video-frames-from-web-source/
---

Dans le monde dynamique d'aujourd'hui, les présentations ont évolué au-delà des diapositives statiques. L'intégration d'éléments multimédias tels que des vidéos dans votre présentation peut améliorer considérablement l'engagement et transmettre les informations plus efficacement. Aspose.Slides pour .NET permet aux développeurs d'incorporer de manière transparente des images vidéo provenant de sources Web dans leurs diapositives de présentation. Ce guide vous guide pas à pas tout au long du processus, démontrant la puissance d'Aspose.Slides.

## Conditions préalables

Avant de nous lancer dans la mise en œuvre, assurez-vous que les conditions préalables suivantes sont en place :

- Visual Studio ou tout autre IDE compatible installé
- Aspose.Slides pour la bibliothèque .NET
- Connaissance de base de la programmation C#

## Étape 1 : Configuration de votre projet

Pour commencer, créez un nouveau projet dans votre IDE préféré et incluez la bibliothèque Aspose.Slides pour .NET. Vous pouvez soit télécharger la bibliothèque à partir du site Web, soit l'installer à l'aide de NuGet Package Manager.

## Étape 2 : Ajout d'une image vidéo à une diapositive

1.  Créer une nouvelle instance de`Presentation` en utilisant Aspose.Slides.
2.  Ajoutez une nouvelle diapositive à la présentation à l'aide du`Slides` collection.
3. Définissez la position et les dimensions de l'image vidéo sur la diapositive.
4.  Utilisez le`EmbedWebVideoFrame` méthode pour ajouter l’image vidéo à la diapositive.

```csharp
// Créer une nouvelle présentation
using (Presentation presentation = new Presentation())
{
    // Ajouter une nouvelle diapositive
    ISlide slide = presentation.Slides.AddEmptySlide();

    // Définir la position et les dimensions de l'image vidéo
    int x = 100; // Coordonnée X
    int y = 100; // Coordonnée Y
    int width = 480; // Largeur
    int height = 270; // Hauteur

    // Ajouter une image vidéo à la diapositive
    slide.EmbedWebVideoFrame(x, y, width, height, new Uri("https://exemple.com/video.mp4"));
    
    // Enregistrez la présentation
    presentation.Save("output.pptx", SaveFormat.Pptx);
}
```

## Étape 3 : Personnalisation de la lecture vidéo

Aspose.Slides propose diverses options pour personnaliser l'expérience de lecture vidéo dans votre présentation. Vous pouvez contrôler des aspects tels que les paramètres de lecture automatique, de boucle et de sourdine pour la vidéo intégrée.

```csharp
// Obtenez l'image vidéo sur la diapositive
IVideoFrame videoFrame = (IVideoFrame)slide.Shapes[0];

//Activer la lecture automatique
videoFrame.PlayMode = VideoPlayModePreset.Auto;

// Activer la boucle
videoFrame.PlayLoopMode = VideoPlayLoopMode.Loop;

// Couper la vidéo
videoFrame.Volume = AudioVolumeMode.Mute;
```

## FAQ

### Comment puis-je changer la source de la vidéo intégrée ?

 Pour changer la source de la vidéo intégrée, mettez simplement à jour l'URI fourni dans le`EmbedWebVideoFrame` méthode pour pointer vers la nouvelle source Web.

### Puis-je personnaliser l’apparence de l’image vidéo ?

Oui, vous pouvez personnaliser l'apparence de l'image vidéo à l'aide de propriétés telles que la position, la taille et le formatage de la forme.

### Est-il possible de contrôler le moment où la lecture de la vidéo commence ?

 Absolument! Vous pouvez contrôler l’heure de début de lecture en ajustant le`videoFrame.StartTime` propriété.

### Quels formats vidéo sont pris en charge pour l'intégration ?

Aspose.Slides prend en charge l'intégration d'images vidéo provenant de diverses sources Web, y compris des formats populaires tels que MP4, des liens YouTube, etc.

### Comment puis-je garantir la compatibilité multiplateforme de la vidéo intégrée ?

Les images vidéo intégrées sont prises en charge dans les versions modernes de Microsoft PowerPoint et d'autres logiciels de présentation compatibles.

## Conclusion

L'intégration d'images vidéo provenant de sources Web dans vos diapositives de présentation à l'aide d'Aspose.Slides for .NET peut transformer vos présentations en expériences multimédias attrayantes. Ce guide étape par étape a montré comment intégrer de manière transparente des images vidéo, personnaliser la lecture et répondre aux questions courantes. Améliorez vos présentations avec du contenu vidéo dynamique et captivez votre public comme jamais auparavant !