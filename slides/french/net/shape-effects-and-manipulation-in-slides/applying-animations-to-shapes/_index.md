---
title: Animations de formes simplifiées avec Aspose.Slides
linktitle: Application d'animations à des formes dans des diapositives de présentation avec Aspose.Slides
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Créez de superbes présentations avec Aspose.Slides pour .NET. Découvrez comment appliquer des animations aux formes dans ce guide étape par étape. Élevez vos diapositives maintenant !
weight: 21
url: /fr/net/shape-effects-and-manipulation-in-slides/applying-animations-to-shapes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Animations de formes simplifiées avec Aspose.Slides

## Introduction
Dans le monde des présentations dynamiques, l'ajout d'animations aux formes peut améliorer considérablement l'attrait visuel et l'engagement de vos diapositives. Aspose.Slides pour .NET fournit une boîte à outils puissante pour y parvenir de manière transparente. Dans ce didacticiel, nous vous guiderons tout au long du processus d'application d'animations aux formes à l'aide d'Aspose.Slides, vous permettant de créer des présentations captivantes qui laissent une impression durable.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous d'avoir les éléments suivants en place :
1.  Aspose.Slides pour .NET : assurez-vous que la bibliothèque est installée et prête à être utilisée. Vous pouvez le télécharger[ici](https://releases.aspose.com/slides/net/).
2. Environnement de développement : configurez votre environnement de développement préféré avec les configurations nécessaires.
3. Répertoire de documents : créez un répertoire pour stocker vos fichiers de présentation.
## Importer des espaces de noms
Dans votre application .NET, commencez par importer les espaces de noms requis :
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
using Aspose.Slides.Animation;
using System.Drawing;
```
## Étape 1 : Créer une présentation
 Commencez par créer une nouvelle présentation en utilisant le`Presentation` classe:
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // Votre code pour créer une présentation va ici.
}
```
## Étape 2 : Ajouter une forme animée
Ajoutons maintenant une forme animée à la première diapositive de votre présentation :
```csharp
ISlide sld = pres.Slides[0];
IAutoShape ashp = sld.Shapes.AddAutoShape(ShapeType.Rectangle, 150, 150, 250, 25);
ashp.AddTextFrame("Animated TextBox");
```
## Étape 3 : appliquer un effet d'animation
Ajoutez l'effet d'animation « PathFootball » à la forme créée :
```csharp
pres.Slides[0].Timeline.MainSequence.AddEffect(ashp, EffectType.PathFootball, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```
## Étape 4 : Créer un bouton de déclenchement
Créez un bouton qui déclenchera l'animation :
```csharp
IShape shapeTrigger = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Bevel, 10, 10, 20, 20);
```
## Étape 5 : Définir un chemin utilisateur personnalisé
Définissez un chemin utilisateur personnalisé pour l'animation :
```csharp
ISequence seqInter = pres.Slides[0].Timeline.InteractiveSequences.Add(shapeTrigger);
IEffect fxUserPath = seqInter.AddEffect(ashp, EffectType.PathUser, EffectSubtype.None, EffectTriggerType.OnClick);
IMotionEffect motionBhv = ((IMotionEffect)fxUserPath.Behaviors[0]);
PointF[] pts = new PointF[1];
pts[0] = new PointF(0.076f, 0.59f);
motionBhv.Path.Add(MotionCommandPathType.LineTo, pts, MotionPathPointsType.Auto, true);
pts[0] = new PointF(-0.076f, -0.59f);
motionBhv.Path.Add(MotionCommandPathType.LineTo, pts, MotionPathPointsType.Auto, false);
motionBhv.Path.Add(MotionCommandPathType.End, null, MotionPathPointsType.Auto, false);
// Enregistrez la présentation au format PPTX sur le disque
pres.Save(dataDir + "AnimExample_out.pptx", SaveFormat.Pptx);
```
Ceci termine le guide étape par étape pour appliquer des animations aux formes à l’aide d’Aspose.Slides pour .NET.
## Conclusion
L'intégration d'animations dans vos présentations ajoute un élément dynamique qui capte l'attention de votre public. Avec Aspose.Slides, vous disposez d'un outil robuste pour intégrer de manière transparente ces effets et élever vos présentations au niveau supérieur.
## Questions fréquemment posées
### Puis-je appliquer plusieurs animations à une seule forme ?
Oui, Aspose.Slides vous permet d'ajouter plusieurs effets d'animation à une seule forme, offrant ainsi une flexibilité dans la création d'animations complexes.
### Aspose.Slides est-il compatible avec différentes versions de PowerPoint ?
Aspose.Slides garantit la compatibilité avec différentes versions de PowerPoint, garantissant ainsi que vos présentations fonctionnent de manière transparente sur différentes plates-formes.
### Où puis-je trouver des ressources supplémentaires et une assistance pour Aspose.Slides ?
 Explore le[Documentation](https://reference.aspose.com/slides/net/) et demander de l'aide dans le[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### Ai-je besoin d’une licence pour qu’Aspose.Slides puisse utiliser la bibliothèque ?
 Oui, vous pouvez acquérir une licence[ici](https://purchase.aspose.com/buy) pour libérer tout le potentiel d’Aspose.Slides.
### Puis-je essayer Aspose.Slides avant d’acheter ?
 Certainement! Utiliser le[essai gratuit](https://releases.aspose.com/) pour découvrir les capacités d’Aspose.Slides avant de vous engager.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
