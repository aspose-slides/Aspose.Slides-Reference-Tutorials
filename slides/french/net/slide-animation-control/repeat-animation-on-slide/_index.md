---
"description": "Améliorez vos présentations PowerPoint avec Aspose.Slides pour .NET. Contrôlez les animations sans effort, captivez votre public et laissez une impression durable."
"linktitle": "Répéter l'animation sur la diapositive"
"second_title": "API de traitement PowerPoint Aspose.Slides .NET"
"title": "Maîtriser les animations PowerPoint avec Aspose.Slides .NET"
"url": "/fr/net/slide-animation-control/repeat-animation-on-slide/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Maîtriser les animations PowerPoint avec Aspose.Slides .NET

## Introduction
Dans l'univers dynamique des présentations, le contrôle des animations joue un rôle essentiel pour captiver et capter l'attention du public. Aspose.Slides pour .NET permet aux développeurs de gérer les types d'animations au sein des diapositives, pour une présentation plus interactive et visuellement plus attrayante. Dans ce tutoriel, nous allons découvrir comment contrôler les types d'animations sur une diapositive avec Aspose.Slides pour .NET, étape par étape.
## Prérequis
Avant de plonger dans le didacticiel, assurez-vous de disposer des prérequis suivants :
1. Bibliothèque Aspose.Slides pour .NET : téléchargez et installez la bibliothèque à partir de [ici](https://releases.aspose.com/slides/net/).
2. Environnement de développement .NET : configurez un environnement de développement .NET sur votre machine.
## Importer des espaces de noms
Dans votre projet .NET, commencez par importer les espaces de noms nécessaires pour exploiter les fonctionnalités fournies par Aspose.Slides :
```csharp
using Aspose.Slides.Animation;
using Aspose.Slides.SlideShow;
using Aspose.Slides.Export;
```
## Étape 1 : Configurer le projet
Créez un nouveau répertoire pour votre projet et instanciez la classe Presentation pour représenter le fichier de présentation.
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
## Étape 2 : Accéder à la séquence d'effets
Récupérez la séquence d’effets pour la première diapositive à l’aide de la propriété MainSequence.
```csharp
ISequence effectsSequence = pres.Slides[0].Timeline.MainSequence;
```
## Étape 3 : Accéder au premier effet
Obtenez le premier effet de la séquence principale pour manipuler ses propriétés.
```csharp
IEffect effect = effectsSequence[0];
```
## Étape 4 : Modifier les paramètres de répétition
Modifiez la propriété Timing/Répéter de l'effet sur « Jusqu'à la fin de la diapositive ».
```csharp
effect.Timing.RepeatUntilEndSlide = true;
```
## Étape 5 : Enregistrer la présentation
Enregistrez la présentation modifiée pour visualiser les modifications.
```csharp
pres.Save(RunExamples.OutPath + "AnimationOnSlide-out.pptx", Aspose.Slides.Export.SaveFormat.Pptx);
```
Répétez ces étapes pour des effets supplémentaires ou personnalisez-les en fonction des exigences de votre présentation.
## Conclusion
Intégrer des animations dynamiques à vos présentations PowerPoint n'a jamais été aussi simple avec Aspose.Slides pour .NET. Ce guide étape par étape vous permet de maîtriser les différents types d'animations et de garantir que vos diapositives marquent durablement votre public.
## Questions fréquemment posées
### Puis-je appliquer ces animations à des objets spécifiques dans une diapositive ?
Oui, vous pouvez cibler des objets spécifiques en accédant à leurs effets individuels dans la séquence.
### Aspose.Slides est-il compatible avec les dernières versions de PowerPoint ?
Aspose.Slides prend en charge une large gamme de versions de PowerPoint, garantissant la compatibilité avec les anciennes et les nouvelles versions.
### Où puis-je trouver des exemples et des ressources supplémentaires ?
Explorez le [documentation](https://reference.aspose.com/slides/net/) pour des exemples complets et des explications détaillées.
### Comment puis-je obtenir une licence temporaire pour Aspose.Slides ?
Visite [ici](https://purchase.aspose.com/temporary-license/) pour obtenir des informations sur l'obtention d'un permis temporaire.
### Besoin d'aide ou avez-vous d'autres questions ?
Engagez-vous avec la communauté Aspose.Slides sur le [forum d'assistance](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}