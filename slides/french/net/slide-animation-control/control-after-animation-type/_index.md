---
title: Maîtriser les effets d'après-animation dans PowerPoint avec Aspose.Slides
linktitle: Contrôle après le type d'animation dans la diapositive
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez comment contrôler les effets d'après-animation dans les diapositives PowerPoint à l'aide d'Aspose.Slides pour .NET. Améliorez vos présentations avec des éléments visuels dynamiques.
weight: 11
url: /fr/net/slide-animation-control/control-after-animation-type/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maîtriser les effets d'après-animation dans PowerPoint avec Aspose.Slides

## Introduction
Améliorer vos présentations avec des animations dynamiques est un aspect crucial pour engager votre public. Aspose.Slides pour .NET fournit une solution puissante pour contrôler les effets d'après-animation dans les diapositives. Dans ce didacticiel, nous vous guiderons tout au long du processus d'utilisation d'Aspose.Slides pour .NET pour manipuler le type d'après-animation sur les diapositives. En suivant ce guide étape par étape, vous serez en mesure de créer des présentations plus interactives et visuellement attrayantes.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous d'avoir les éléments suivants en place :
- Connaissance de base de la programmation C# et .NET.
-  Aspose.Slides pour la bibliothèque .NET installée. Vous pouvez le télécharger[ici](https://releases.aspose.com/slides/net/).
- Un environnement de développement intégré (IDE) tel que Visual Studio.
## Importer des espaces de noms
Commencez par importer les espaces de noms nécessaires pour accéder aux fonctionnalités Aspose.Slides. Ajoutez les lignes suivantes à votre code :
```csharp
using System.Drawing;
using System.IO;
using Aspose.Slides.Animation;
using Aspose.Slides.SlideShow;
using Aspose.Slides.Export;
```
Maintenant, décomposons le code fourni en plusieurs étapes pour une meilleure compréhension :
## Étape 1 : configurer le répertoire de documents
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
Assurez-vous que le répertoire spécifié existe ou créez-le s'il n'existe pas.
## Étape 2 : Définir le chemin du fichier de sortie
```csharp
string outPath = Path.Combine(dataDir, "AnimationAfterEffect-out.pptx");
```
Spécifiez le chemin du fichier de sortie pour la présentation modifiée.
## Étape 3 : Charger la présentation
```csharp
using (Presentation pres = new Presentation(dataDir + "AnimationAfterEffect.pptx"))
```
Instanciez la classe Présentation et chargez la présentation existante.
## Étape 4 : Modifier les effets d'animation après la diapositive 1
```csharp
ISlide slide1 = pres.Slides.AddClone(pres.Slides[0]);
ISequence seq = slide1.Timeline.MainSequence;
foreach (IEffect effect in seq)
    effect.AfterAnimationType = AfterAnimationType.HideOnNextMouseClick;
```
Clonez la première diapositive, accédez à sa séquence chronologique et définissez l'effet d'après-animation sur "Masquer au prochain clic de souris".
## Étape 5 : Modifier les effets d'animation après la diapositive 2
```csharp
ISlide slide2 = pres.Slides.AddClone(pres.Slides[0]);
seq = slide2.Timeline.MainSequence;
foreach (IEffect effect in seq)
{
    effect.AfterAnimationType = AfterAnimationType.Color;
    effect.AfterAnimationColor.Color = Color.Green;
}
```
Clonez à nouveau la première diapositive, en changeant cette fois l'effet après-animation en "Couleur" avec une couleur verte.
## Étape 6 : Modifier les effets d'animation après la diapositive 3
```csharp
ISlide slide3 = pres.Slides.AddClone(pres.Slides[0]);
seq = slide3.Timeline.MainSequence;
foreach (IEffect effect in seq)
    effect.AfterAnimationType = AfterAnimationType.HideAfterAnimation;
```
Clonez à nouveau la première diapositive en définissant l'effet après-animation sur "Masquer après l'animation".
## Étape 7 : Enregistrez la présentation modifiée
```csharp
pres.Save(outPath, SaveFormat.Pptx);
```
Enregistrez la présentation modifiée avec le chemin du fichier de sortie spécifié.
## Conclusion
Toutes nos félicitations! Vous avez appris avec succès à contrôler les effets d'après-animation sur les diapositives à l'aide d'Aspose.Slides pour .NET. Expérimentez avec différents types d'après-animation pour créer des présentations plus dynamiques et plus attrayantes.
## FAQ
### Puis-je appliquer différents effets d’après-animation à des éléments individuels d’une diapositive ?
Oui, vous pouvez. Parcourez les éléments et ajustez leurs effets après animation en conséquence.
### Aspose.Slides est-il compatible avec les dernières versions de .NET ?
Oui, Aspose.Slides est régulièrement mis à jour pour garantir la compatibilité avec les dernières versions du framework .NET.
### Comment puis-je ajouter des animations personnalisées aux diapositives à l'aide d'Aspose.Slides ?
 Se référer à la documentation[ici](https://reference.aspose.com/slides/net/) pour des informations détaillées sur l’ajout d’animations personnalisées.
### Quels formats de fichiers Aspose.Slides prend-il en charge pour enregistrer des présentations ?
Aspose.Slides prend en charge divers formats, notamment PPTX, PPT, PDF, etc. Consultez la documentation pour la liste complète.
### Où puis-je obtenir de l'aide ou poser des questions concernant Aspose.Slides ?
 Visiter le[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) pour le soutien et l’interaction communautaire.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
