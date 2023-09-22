---
title: Ajout d'images vidéo aux diapositives de présentation à l'aide d'Aspose.Slides
linktitle: Ajout d'images vidéo aux diapositives de présentation à l'aide d'Aspose.Slides
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez comment améliorer vos présentations en ajoutant des images vidéo à l'aide d'Aspose.Slides pour .NET. Créez du contenu engageant et interactif en toute transparence.
type: docs
weight: 19
url: /fr/net/shape-effects-and-manipulation-in-slides/adding-video-frames/
---

## Introduction à Aspose.Slides et à l'intégration vidéo

Aspose.Slides est une bibliothèque complète qui permet aux développeurs de créer, manipuler et convertir des présentations PowerPoint par programme. En intégrant des images vidéo dans vos diapositives, vous pouvez rehausser vos présentations et les rendre plus dynamiques et attrayantes.

## Conditions préalables à l'intégration de vidéos

Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Visual Studio ou tout autre environnement de développement .NET préféré
- Aspose.Slides pour la bibliothèque .NET installée
- Une présentation PowerPoint (PPTX) dans laquelle vous souhaitez ajouter des images vidéo

## Configuration de votre environnement de développement

1. Ouvrez Visual Studio et créez un nouveau projet .NET.
2.  Installez le package NuGet Aspose.Slides :`Install-Package Aspose.Slides`.

## Chargement d'une présentation et accès aux diapositives

Pour commencer, chargez votre présentation PowerPoint à l'aide d'Aspose.Slides :

```csharp
using Aspose.Slides;

// Charger la présentation
using Presentation presentation = new Presentation("your-presentation.pptx");

// Accéder aux diapositives
ISlideCollection slides = presentation.Slides;
```

## Ajout de fichiers vidéo à la présentation

1. Placez vos fichiers vidéo dans un dossier de votre projet.
2. Ajoutez des références à ces fichiers dans votre code :

```csharp
// Ajouter des fichiers vidéo
string videoPath = "path-to-your-videos-folder";
string[] videoFiles = Directory.GetFiles(videoPath, "*.mp4");
```

## Placer des images vidéo sur des diapositives

Parcourez les diapositives et ajoutez des images vidéo :

```csharp
foreach (ISlide slide in slides)
{
    foreach (string videoFile in videoFiles)
    {
        IVideoFrame videoFrame = slide.Shapes.AddVideoFrame(100, 100, 320, 240, videoFile);
    }
}
```

## Personnalisation des propriétés de l'image vidéo

Vous pouvez personnaliser les propriétés de l'image vidéo telles que la position, la taille et le style :

```csharp
foreach (IVideoFrame videoFrame in slide.Shapes.OfType<IVideoFrame>())
{
    videoFrame.X = 200;
    videoFrame.Y = 150;
    videoFrame.Width = 480;
    videoFrame.Height = 360;
}
```

## Gestion des options de lecture

 Contrôlez la lecture vidéo à l’aide du`VideoPlayModePreset` énumération:

```csharp
foreach (IVideoFrame videoFrame in slide.Shapes.OfType<IVideoFrame>())
{
    videoFrame.PlayMode = VideoPlayModePreset.Auto;
}
```

## Enregistrement et exportation de la présentation modifiée

Enregistrez votre présentation après avoir ajouté des images vidéo :

```csharp
presentation.Save("modified-presentation.pptx", SaveFormat.Pptx);
```

## Conclusion

L'intégration d'images vidéo dans vos diapositives de présentation à l'aide d'Aspose.Slides améliore l'impact visuel de votre contenu. Vous avez appris à intégrer de manière transparente des vidéos, à personnaliser les propriétés des images vidéo et à contrôler les options de lecture. Commencez à créer des présentations dynamiques et engageantes qui captivent votre public.

## FAQ

### Comment ajouter plusieurs vidéos à une seule diapositive ?

Parcourez vos fichiers vidéo et ajoutez des images vidéo à la diapositive souhaitée à l'aide du code fourni.

### Puis-je contrôler les paramètres de lecture vidéo ?

 Oui, vous pouvez utiliser le`VideoPlayModePreset` énumération pour définir les options de lecture telles que la lecture automatique.

### Quels formats vidéo sont pris en charge ?

Aspose.Slides prend en charge divers formats vidéo, notamment MP4, AVI, WMV, etc.

### Est-il possible d'ajouter des vidéos par programme en C# ?

Absolument, Aspose.Slides pour .NET fournit une API conviviale pour ajouter des vidéos aux diapositives par programmation à l'aide de C#.

### Puis-je modifier l'apparence de l'image vidéo ?

Oui, vous pouvez personnaliser la position, la taille et d'autres propriétés visuelles de l'image vidéo en fonction de vos besoins.