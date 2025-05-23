---
"description": "Apprenez à contrôler les effets post-animation dans vos diapositives PowerPoint avec Aspose.Slides pour .NET. Améliorez vos présentations avec des éléments visuels dynamiques."
"linktitle": "Contrôle après le type d'animation dans la diapositive"
"second_title": "API de traitement PowerPoint Aspose.Slides .NET"
"title": "Maîtriser les effets d'après-animation dans PowerPoint avec Aspose.Slides"
"url": "/fr/net/slide-animation-control/control-after-animation-type/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Maîtriser les effets d'après-animation dans PowerPoint avec Aspose.Slides

## Introduction
Enrichir vos présentations avec des animations dynamiques est essentiel pour captiver votre public. Aspose.Slides pour .NET offre une solution performante pour contrôler les effets post-animation des diapositives. Dans ce tutoriel, nous vous guiderons dans l'utilisation d'Aspose.Slides pour .NET pour manipuler le type d'animation post-animation sur les diapositives. En suivant ce guide étape par étape, vous pourrez créer des présentations plus interactives et visuellement plus attrayantes.
## Prérequis
Avant de plonger dans le didacticiel, assurez-vous que les éléments suivants sont en place :
- Connaissances de base de la programmation C# et .NET.
- Bibliothèque Aspose.Slides pour .NET installée. Vous pouvez la télécharger. [ici](https://releases.aspose.com/slides/net/).
- Un environnement de développement intégré (IDE) tel que Visual Studio.
## Importer des espaces de noms
Commencez par importer les espaces de noms nécessaires pour accéder aux fonctionnalités d'Aspose.Slides. Ajoutez les lignes suivantes à votre code :
```csharp
using System.Drawing;
using System.IO;
using Aspose.Slides.Animation;
using Aspose.Slides.SlideShow;
using Aspose.Slides.Export;
```
Maintenant, décomposons le code fourni en plusieurs étapes pour une meilleure compréhension :
## Étape 1 : Configurer le répertoire de documents
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
Instanciez la classe Presentation et chargez la présentation existante.
## Étape 4 : Modifier les effets d'animation sur la diapositive 1
```csharp
ISlide slide1 = pres.Slides.AddClone(pres.Slides[0]);
ISequence seq = slide1.Timeline.MainSequence;
foreach (IEffect effect in seq)
    effect.AfterAnimationType = AfterAnimationType.HideOnNextMouseClick;
```
Clonez la première diapositive, accédez à sa séquence chronologique et définissez l'effet post-animation sur « Masquer au prochain clic de souris ».
## Étape 5 : Modifier les effets d'animation sur la diapositive 2
```csharp
ISlide slide2 = pres.Slides.AddClone(pres.Slides[0]);
seq = slide2.Timeline.MainSequence;
foreach (IEffect effect in seq)
{
    effect.AfterAnimationType = AfterAnimationType.Color;
    effect.AfterAnimationColor.Color = Color.Green;
}
```
Clonez à nouveau la première diapositive, cette fois en changeant l'effet d'après-animation en « Couleur » avec une couleur verte.
## Étape 6 : Modifier les effets d'animation sur la diapositive 3
```csharp
ISlide slide3 = pres.Slides.AddClone(pres.Slides[0]);
seq = slide3.Timeline.MainSequence;
foreach (IEffect effect in seq)
    effect.AfterAnimationType = AfterAnimationType.HideAfterAnimation;
```
Clonez à nouveau la première diapositive en définissant l'effet après animation sur « Masquer après l'animation ».
## Étape 7 : Enregistrer la présentation modifiée
```csharp
pres.Save(outPath, SaveFormat.Pptx);
```
Enregistrez la présentation modifiée avec le chemin du fichier de sortie spécifié.
## Conclusion
Félicitations ! Vous avez appris à contrôler les effets d'après-animation sur les diapositives avec Aspose.Slides pour .NET. Testez différents types d'après-animation pour créer des présentations plus dynamiques et attrayantes.
## FAQ
### Puis-je appliquer différents effets post-animation à des éléments individuels dans une diapositive ?
Oui, vous pouvez. Parcourez les éléments et ajustez leurs effets post-animation en conséquence.
### Aspose.Slides est-il compatible avec les dernières versions de .NET ?
Oui, Aspose.Slides est régulièrement mis à jour pour assurer la compatibilité avec les dernières versions du framework .NET.
### Comment puis-je ajouter des animations personnalisées aux diapositives à l’aide d’Aspose.Slides ?
Se référer à la documentation [ici](https://reference.aspose.com/slides/net/) pour des informations détaillées sur l'ajout d'animations personnalisées.
### Quels formats de fichiers Aspose.Slides prend-il en charge pour l'enregistrement des présentations ?
Aspose.Slides prend en charge divers formats, notamment PPTX, PPT, PDF, etc. Consultez la documentation pour la liste complète.
### Où puis-je obtenir de l'aide ou poser des questions concernant Aspose.Slides ?
Visitez le [Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) pour le soutien et l'interaction communautaire.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}