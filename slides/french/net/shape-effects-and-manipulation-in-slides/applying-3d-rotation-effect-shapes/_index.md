---
title: Maîtriser la rotation 3D dans les présentations avec Aspose.Slides pour .NET
linktitle: Application d'un effet de rotation 3D sur des formes dans des diapositives de présentation
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Améliorez vos présentations avec Aspose.Slides pour .NET ! Apprenez à appliquer des effets de rotation 3D aux formes dans ce didacticiel. Créez une présentation dynamique et visuellement époustouflante.
weight: 23
url: /fr/net/shape-effects-and-manipulation-in-slides/applying-3d-rotation-effect-shapes/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introduction
La création de diapositives de présentation attrayantes et dynamiques est un aspect clé d’une communication efficace. Aspose.Slides pour .NET fournit un ensemble d'outils puissants pour améliorer vos présentations, notamment la possibilité d'appliquer des effets de rotation 3D aux formes. Dans ce didacticiel, nous allons parcourir le processus d'application d'un effet de rotation 3D aux formes dans les diapositives de présentation à l'aide d'Aspose.Slides pour .NET.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
- Aspose.Slides pour .NET : assurez-vous que la bibliothèque Aspose.Slides pour .NET est installée. Vous pouvez le télécharger depuis le[site web](https://releases.aspose.com/slides/net/).
- Environnement de développement : configurez un environnement de développement .NET, tel que Visual Studio, pour écrire et exécuter votre code.
## Importer des espaces de noms
Dans votre projet .NET, importez les espaces de noms nécessaires pour exploiter les fonctionnalités d'Aspose.Slides. Incluez les espaces de noms suivants au début de votre code :
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Étape 1 : Configurez votre projet
Créez un nouveau projet dans votre environnement de développement .NET préféré. Assurez-vous d'avoir ajouté la référence Aspose.Slides à votre projet.
## Étape 2 : initialiser la présentation
Instanciez une classe Présentation pour commencer à travailler avec des diapositives :
```csharp
Presentation pres = new Presentation();
```
## Étape 3 : ajouter une forme automatique
Ajoutez une forme automatique à la diapositive, en spécifiant son type, sa position et ses dimensions :
```csharp
IShape autoShape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 30, 30, 200, 200);
```
## Étape 4 : Définir l'effet de rotation 3D
Configurez l'effet de rotation 3D pour la forme automatique :
```csharp
autoShape.ThreeDFormat.Depth = 6;
autoShape.ThreeDFormat.Camera.SetRotation(40, 35, 20);
autoShape.ThreeDFormat.Camera.CameraType = CameraPresetType.IsometricLeftUp;
autoShape.ThreeDFormat.LightRig.LightType = LightRigPresetType.Balanced;
```
## Étape 5 : Enregistrez la présentation
Enregistrez la présentation modifiée avec l'effet de rotation 3D appliqué :
```csharp
pres.Save("Your Document Directory" + "Rotation_out.pptx", SaveFormat.Pptx);
```
## Étape 6 : Répétez l'opération pour d'autres formes
Si vous avez des formes supplémentaires, répétez les étapes 3 à 5 pour chaque forme.
## Conclusion
L'ajout d'effets de rotation 3D aux formes de vos diapositives de présentation peut améliorer considérablement leur attrait visuel. Avec Aspose.Slides pour .NET, ce processus devient simple, vous permettant de créer des présentations captivantes.
## FAQ
### Puis-je appliquer une rotation 3D aux zones de texte dans Aspose.Slides pour .NET ?
Oui, vous pouvez appliquer des effets de rotation 3D à diverses formes, y compris des zones de texte, à l'aide d'Aspose.Slides.
### Existe-t-il une version d’essai d’Aspose.Slides pour .NET disponible ?
 Oui, vous pouvez accéder à la version d'essai[ici](https://releases.aspose.com/).
### Comment puis-je obtenir de l’assistance pour Aspose.Slides pour .NET ?
 Visiter le[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) pour le soutien et les discussions de la communauté.
### Puis-je acheter une licence temporaire pour Aspose.Slides pour .NET ?
 Oui, vous pouvez obtenir une licence temporaire[ici](https://purchase.aspose.com/temporary-license/).
### Où puis-je trouver une documentation détaillée pour Aspose.Slides pour .NET ?
 La documentation est disponible[ici](https://reference.aspose.com/slides/net/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
