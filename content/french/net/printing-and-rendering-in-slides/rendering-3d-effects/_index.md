---
title: Rendu d'effets 3D dans des diapositives de présentation avec Aspose.Slides
linktitle: Rendu d'effets 3D dans des diapositives de présentation avec Aspose.Slides
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez comment ajouter des effets 3D captivants à vos diapositives de présentation à l'aide d'Aspose.Slides pour .NET. Notre guide étape par étape couvre tout, de la configuration de votre environnement à l'application d'animations et à l'exportation du résultat final.
type: docs
weight: 13
url: /fr/net/printing-and-rendering-in-slides/rendering-3d-effects/
---

## Introduction aux effets 3D dans les diapositives de présentation

L'ajout d'effets 3D à vos diapositives de présentation peut rendre votre contenu plus attrayant et dynamique. Aspose.Slides pour .NET fournit une plate-forme puissante pour intégrer ces effets de manière transparente. Nous explorerons comment utiliser la bibliothèque pour créer, manipuler et restituer des objets 3D dans vos diapositives.

## Configuration de votre environnement de développement

Avant de plonger dans le processus de codage, configurons notre environnement de développement. Voici ce dont vous avez besoin :

- Visual Studio avec la bibliothèque Aspose.Slides pour .NET installée
- Compréhension de base de la programmation C#

## Créer une nouvelle présentation

Commençons par créer une nouvelle présentation à l'aide d'Aspose.Slides. L'extrait de code suivant montre comment y parvenir :

```csharp
using Aspose.Slides;

// Créer une nouvelle présentation
Presentation presentation = new Presentation();
```

## Ajout de modèles 3D aux diapositives

Maintenant que notre présentation est prête, ajoutons un modèle 3D à une diapositive. Vous pouvez choisir parmi une variété de formats tels que OBJ, STL ou FBX. Voici comment ajouter un modèle 3D à une diapositive :

```csharp
// Charger une diapositive
ISlide slide = presentation.Slides.AddEmptySlide();

// Charger le modèle 3D
string modelPath = "path/to/your/3d/model.obj";
byte[] modelBytes = File.ReadAllBytes(modelPath);
IEmbeddingResult embeddingResult = presentation.EmbedExternalFile(modelBytes);

// Ajouter le modèle 3D à la diapositive
slide.Shapes.AddEmbedded3DModelFrame(embeddingResult);
```

## Ajustement des effets et des propriétés 3D

Une fois que vous avez ajouté le modèle 3D, vous pouvez ajuster ses effets et ses propriétés. Cela inclut la rotation, la mise à l’échelle et le positionnement. Voici un exemple de la façon dont vous pouvez y parvenir :

```csharp
// Obtenez le cadre du modèle 3D
I3DModelFrame modelFrame = (I3DModelFrame)slide.Shapes[0];

// Faire pivoter le modèle
modelFrame.RotationX = 30;
modelFrame.RotationY = 45;
modelFrame.RotationZ = 0;

// Mettre le modèle à l'échelle
modelFrame.ScaleX = 1.5;
modelFrame.ScaleY = 1.5;
modelFrame.ScaleZ = 1.5;

// Positionner le modèle
modelFrame.X = 100;
modelFrame.Y = 100;
```

## Ajout d'animations aux objets 3D

Pour rendre votre présentation encore plus captivante, vous pouvez ajouter des animations aux objets 3D. Aspose.Slides vous permet d'appliquer divers effets d'animation aux modèles 3D. Voici un extrait pour démontrer :

```csharp
// Ajouter une animation au modèle 3D
IAnimation animation = slide.Timeline.MainSequence.AddEffect(modelFrame, EffectType.Fade);
animation.Timing.TriggerType = EffectTriggerType.OnClick;
```

## Application de l'éclairage et des matériaux

Pour améliorer le réalisme de vos modèles 3D, vous pouvez appliquer de l'éclairage et des matériaux. Ceci peut être réalisé en utilisant les propriétés d'éclairage et de matériaux d'Aspose.Slides. Voici comment procéder :

```csharp
// Appliquer un éclairage au modèle 3D
modelFrame.LightRig.Preset = LightRigPresetType.BrightRoom;

// Appliquer les propriétés du matériau
IMaterial material = modelFrame.Materials[0];
material.DiffuseColor = Color.Red;
material.SpecularColor = Color.White;
```

## Exporter la présentation

Une fois que vous avez perfectionné vos effets et animations 3D, il est temps d'exporter votre présentation. Aspose.Slides propose différents formats d'exportation, tels que PPTX, PDF, etc. Voici un extrait pour exporter votre présentation au format PDF :

```csharp
// Enregistrez la présentation au format PDF
string outputPath = "output/path/presentation.pdf";
presentation.Save(outputPath, SaveFormat.Pdf);
```

## Conclusion

Dans ce didacticiel, nous avons plongé dans le monde passionnant des effets 3D dans les diapositives de présentation à l'aide d'Aspose.Slides pour .NET. Vous avez appris à créer une présentation, à ajouter des modèles 3D, à ajuster les effets et les propriétés, à ajouter des animations, à appliquer l'éclairage et les matériaux et à exporter le résultat final. Avec ces compétences en main, vous pouvez désormais créer des présentations visuellement époustouflantes qui laisseront une impression durable à votre public.

## FAQ

### Comment puis-je installer Aspose.Slides pour .NET ?

 Pour installer Aspose.Slides pour .NET, vous pouvez suivre le guide d'installation fourni dans le[Documentation](https://docs.aspose.com/slides/net/installation/).

### Puis-je ajouter plusieurs modèles 3D à une seule diapositive ?

 Oui, vous pouvez ajouter plusieurs modèles 3D à une seule diapositive en utilisant l'outil`Shapes.AddEmbedded3DModelFrame()` méthode pour chaque modèle.

### Est-il possible d'exporter la présentation vers d'autres formats ?

Absolument! Aspose.Slides pour .NET prend en charge l'exportation de présentations vers différents formats, notamment PPTX, PDF, TIFF, etc.

### Comment puis-je créer des animations complexes pour des modèles 3D ?

Vous pouvez créer des animations complexes en utilisant les effets d'animation fournis par Aspose.Slides. Explore le[documentation d'animation](https://reference.aspose.com/slides/net/aspose.slides.animation/) pour des informations détaillées.

### Où puis-je trouver plus d’exemples de code et de ressources ?

 Pour plus d'exemples de code, de didacticiels et de ressources, vous pouvez visiter le[Aspose.Slides pour la documentation .NET](https://reference.aspose.com/slides/net/).