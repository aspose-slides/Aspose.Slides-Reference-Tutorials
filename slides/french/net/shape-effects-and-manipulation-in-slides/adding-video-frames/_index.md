---
title: Didacticiel sur l'ajout de cadres vidéo avec Aspose.Slides pour .NET
linktitle: Ajout d'images vidéo aux diapositives de présentation à l'aide d'Aspose.Slides
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Revitalisez les présentations avec des images vidéo dynamiques à l’aide d’Aspose.Slides pour .NET. Suivez notre guide pour une intégration transparente et créez des contenus attrayants.
weight: 19
url: /fr/net/shape-effects-and-manipulation-in-slides/adding-video-frames/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introduction
Dans le paysage dynamique des présentations, l’intégration d’éléments multimédias peut accroître l’impact et l’engagement globaux. L'ajout d'images vidéo à vos diapositives peut changer la donne, capturant l'attention de votre public d'une manière que le contenu statique ne peut pas. Aspose.Slides for .NET fournit une solution robuste pour intégrer de manière transparente des images vidéo dans vos diapositives de présentation.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
- Compréhension de base de la programmation C# et .NET.
-  Aspose.Slides pour la bibliothèque .NET installée. Sinon, vous pouvez le télécharger[ici](https://releases.aspose.com/slides/net/).
- Un environnement de développement adapté mis en place.
## Importer des espaces de noms
Pour commencer, assurez-vous d'importer les espaces de noms nécessaires dans votre projet :
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Étape 1 : Créer un objet de présentation
 Commencez par créer une instance de`Presentation` classe, représentant le fichier PPTX :
```csharp
string dataDir = "Your Document Directory";
using (Presentation pres = new Presentation())
{
    // Votre code ici
}
```
## Étape 2 : accéder à la diapositive
Récupérez la première diapositive de la présentation :
```csharp
ISlide sld = pres.Slides[0];
```
## Étape 3 : ajouter une image vidéo
Maintenant, ajoutez une image vidéo à la diapositive :
```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 150, dataDir + "video1.avi");
```
Ajustez les paramètres (gauche, haut, largeur, hauteur) en fonction de vos préférences de mise en page.
## Étape 4 : Définir le mode de lecture et le volume
Configurez le mode de lecture et le volume de l'image vidéo insérée :
```csharp
vf.PlayMode = VideoPlayModePreset.Auto;
vf.Volume = AudioVolumeMode.Loud;
```
N'hésitez pas à personnaliser ces paramètres en fonction de vos besoins de présentation.
## Étape 5 : Enregistrez la présentation
Enregistrez la présentation modifiée sur le disque :
```csharp
pres.Save(dataDir + "VideoFrame_out.pptx", SaveFormat.Pptx);
```
Désormais, votre présentation comprend une image vidéo parfaitement intégrée !
## Conclusion
L'incorporation d'images vidéo dans des diapositives de présentation à l'aide d'Aspose.Slides pour .NET est un processus simple qui ajoute une touche dynamique à votre contenu. Améliorez vos présentations en tirant parti des éléments multimédias, en captivant votre public et en offrant une expérience mémorable.
## FAQ
### Q1 : Puis-je ajouter plusieurs images vidéo à une seule diapositive ?
Oui, vous pouvez ajouter plusieurs images vidéo à une seule diapositive en répétant le processus décrit dans le didacticiel pour chaque image vidéo.
### Q2 : Quels formats vidéo sont pris en charge par Aspose.Slides pour .NET ?
Aspose.Slides pour .NET prend en charge divers formats vidéo, notamment AVI, WMV et MP4.
### Q3 : Puis-je contrôler les options de lecture de la vidéo insérée ?
Absolument! Vous avez un contrôle total sur les options de lecture, telles que le mode de lecture et le volume, comme démontré dans le didacticiel.
### Q4 : Existe-t-il une version d’essai disponible pour Aspose.Slides pour .NET ?
 Oui, vous pouvez explorer les capacités d'Aspose.Slides pour .NET en téléchargeant la version d'essai[ici](https://releases.aspose.com/).
### Q5 : Où puis-je trouver de l'assistance pour Aspose.Slides pour .NET ?
 Pour toute question ou assistance, visitez le[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
