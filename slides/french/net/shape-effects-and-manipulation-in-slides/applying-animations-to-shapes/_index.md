---
"description": "Créez des présentations époustouflantes avec Aspose.Slides pour .NET. Apprenez à appliquer des animations aux formes grâce à ce guide étape par étape. Sublimez vos diapositives dès maintenant !"
"linktitle": "Application d'animations aux formes dans les diapositives de présentation avec Aspose.Slides"
"second_title": "API de traitement PowerPoint Aspose.Slides .NET"
"title": "Animations de formes simplifiées avec Aspose.Slides"
"url": "/fr/net/shape-effects-and-manipulation-in-slides/applying-animations-to-shapes/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Animations de formes simplifiées avec Aspose.Slides

## Introduction
Dans l'univers des présentations dynamiques, l'ajout d'animations aux formes peut considérablement améliorer l'attrait visuel et l'engagement de vos diapositives. Aspose.Slides pour .NET offre une boîte à outils puissante pour y parvenir en toute simplicité. Dans ce tutoriel, nous vous guiderons dans l'application d'animations aux formes avec Aspose.Slides, vous permettant ainsi de créer des présentations captivantes et marquantes.
## Prérequis
Avant de plonger dans le didacticiel, assurez-vous que les éléments suivants sont en place :
1. Aspose.Slides pour .NET : Assurez-vous que la bibliothèque est installée et prête à l'emploi. Vous pouvez la télécharger. [ici](https://releases.aspose.com/slides/net/).
2. Environnement de développement : configurez votre environnement de développement préféré avec les configurations nécessaires.
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
Commencez par créer une nouvelle présentation en utilisant le `Presentation` classe:
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
## Étape 2 : ajouter une forme animée
Maintenant, ajoutons une forme animée à la première diapositive de votre présentation :
```csharp
ISlide sld = pres.Slides[0];
IAutoShape ashp = sld.Shapes.AddAutoShape(ShapeType.Rectangle, 150, 150, 250, 25);
ashp.AddTextFrame("Animated TextBox");
```
## Étape 3 : Appliquer l’effet d’animation
Ajoutez l'effet d'animation « PathFootball » à la forme créée :
```csharp
pres.Slides[0].Timeline.MainSequence.AddEffect(ashp, EffectType.PathFootball, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```
## Étape 4 : Créer un bouton déclencheur
Créez un bouton qui déclenchera l'animation :
```csharp
IShape shapeTrigger = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Bevel, 10, 10, 20, 20);
```
## Étape 5 : Définir un chemin d’accès utilisateur personnalisé
Définir un chemin utilisateur personnalisé pour l'animation :
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
// Enregistrer la présentation au format PPTX sur le disque
pres.Save(dataDir + "AnimExample_out.pptx", SaveFormat.Pptx);
```
Ceci complète le guide étape par étape pour appliquer des animations aux formes à l'aide d'Aspose.Slides pour .NET.
## Conclusion
Intégrer des animations à vos présentations ajoute un élément dynamique qui capte l'attention de votre public. Avec Aspose.Slides, vous disposez d'un outil performant pour intégrer ces effets de manière fluide et donner un nouveau souffle à vos présentations.
## Questions fréquemment posées
### Puis-je appliquer plusieurs animations à une seule forme ?
Oui, Aspose.Slides vous permet d'ajouter plusieurs effets d'animation à une seule forme, offrant ainsi une flexibilité dans la création d'animations complexes.
### Aspose.Slides est-il compatible avec différentes versions de PowerPoint ?
Aspose.Slides assure la compatibilité avec différentes versions de PowerPoint, garantissant que vos présentations fonctionnent de manière transparente sur différentes plates-formes.
### Où puis-je trouver des ressources et une assistance supplémentaires pour Aspose.Slides ?
Explorez le [documentation](https://reference.aspose.com/slides/net/) et demander de l'aide dans le [Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### Ai-je besoin d'une licence pour Aspose.Slides pour utiliser la bibliothèque ?
Oui, vous pouvez acquérir une licence [ici](https://purchase.aspose.com/buy) pour libérer tout le potentiel d'Aspose.Slides.
### Puis-je essayer Aspose.Slides avant d'acheter ?
Certainement ! Utilisez le [essai gratuit](https://releases.aspose.com/) pour découvrir les capacités d'Aspose.Slides avant de vous engager.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}