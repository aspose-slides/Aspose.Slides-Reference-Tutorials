---
title: Maîtriser les animations PowerPoint avec Aspose.Slides .NET
linktitle: Répéter l'animation sur la diapositive
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Améliorez les présentations PowerPoint à l’aide d’Aspose.Slides pour .NET. Contrôlez les animations sans effort, captivez votre public et laissez une impression durable.
weight: 12
url: /fr/net/slide-animation-control/repeat-animation-on-slide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introduction
Dans le monde dynamique des présentations, la capacité de contrôler les animations joue un rôle central pour engager et capter l'attention du public. Aspose.Slides pour .NET permet aux développeurs de prendre en charge les types d'animation dans les diapositives, permettant une présentation plus interactive et visuellement attrayante. Dans ce didacticiel, nous explorerons comment contrôler les types d'animation sur une diapositive à l'aide d'Aspose.Slides pour .NET, étape par étape.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
1.  Aspose.Slides pour la bibliothèque .NET : téléchargez et installez la bibliothèque à partir de[ici](https://releases.aspose.com/slides/net/).
2. Environnement de développement .NET : configurez un environnement de développement .NET sur votre machine.
## Importer des espaces de noms
Dans votre projet .NET, commencez par importer les espaces de noms nécessaires pour tirer parti des fonctionnalités fournies par Aspose.Slides :
```csharp
using Aspose.Slides.Animation;
using Aspose.Slides.SlideShow;
using Aspose.Slides.Export;
```
## Étape 1 : configurer le projet
Créez un nouveau répertoire pour votre projet et instanciez la classe Présentation pour représenter le fichier de présentation.
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation(dataDir + "AnimationOnSlide.pptx"))
{
    // Votre code va ici
}
```
## Étape 2 : Accéder à la séquence d’effets
Récupérez la séquence d'effets de la première diapositive à l'aide de la propriété MainSequence.
```csharp
ISequence effectsSequence = pres.Slides[0].Timeline.MainSequence;
```
## Étape 3 : accéder au premier effet
Obtenez le premier effet de la séquence principale pour manipuler ses propriétés.
```csharp
IEffect effect = effectsSequence[0];
```
## Étape 4 : Modifier les paramètres de répétition
Modifiez la propriété Timing/Repeat de l’effet sur « Jusqu’à la fin de la diapositive ».
```csharp
effect.Timing.RepeatUntilEndSlide = true;
```
## Étape 5 : Enregistrez la présentation
Enregistrez la présentation modifiée pour visualiser les modifications.
```csharp
pres.Save(RunExamples.OutPath + "AnimationOnSlide-out.pptx", Aspose.Slides.Export.SaveFormat.Pptx);
```
Répétez ces étapes pour obtenir des effets supplémentaires ou personnalisez-les en fonction de vos besoins de présentation.
## Conclusion
L'intégration d'animations dynamiques dans vos présentations PowerPoint n'a jamais été aussi simple avec Aspose.Slides pour .NET. Ce guide étape par étape vous donne les connaissances nécessaires pour contrôler les types d'animation, garantissant ainsi que vos diapositives laissent une impression durable sur votre public.
## Questions fréquemment posées
### Puis-je appliquer ces animations à des objets spécifiques dans une diapositive ?
Oui, vous pouvez cibler des objets spécifiques en accédant à leurs effets individuels dans la séquence.
### Aspose.Slides est-il compatible avec les dernières versions de PowerPoint ?
Aspose.Slides prend en charge une large gamme de versions de PowerPoint, garantissant la compatibilité avec les anciennes et les nouvelles versions.
### Où puis-je trouver des exemples et des ressources supplémentaires ?
 Explore le[Documentation](https://reference.aspose.com/slides/net/) pour des exemples complets et des explications détaillées.
### Comment puis-je obtenir une licence temporaire pour Aspose.Slides ?
 Visite[ici](https://purchase.aspose.com/temporary-license/) pour obtenir des informations sur l’obtention d’un permis temporaire.
### Besoin d'aide ou vous avez d'autres questions ?
 Engagez-vous avec la communauté Aspose.Slides sur le[forum d'entraide](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
