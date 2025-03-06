---
title: Maîtriser les effets de biseau dans Aspose.Slides – Tutoriel étape par étape
linktitle: Application d'effets de biseau aux formes dans les diapositives de présentation à l'aide d'Aspose.Slides
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Améliorez vos diapositives de présentation avec Aspose.Slides pour .NET ! Apprenez à appliquer des effets de biseau captivants dans ce guide étape par étape.
weight: 24
url: /fr/net/shape-effects-and-manipulation-in-slides/applying-bevel-effects-shapes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introduction
Dans le monde dynamique des présentations, ajouter un attrait visuel à vos diapositives peut améliorer considérablement l'impact de votre message. Aspose.Slides for .NET fournit une boîte à outils puissante pour manipuler et embellir vos diapositives de présentation par programme. L’une de ces fonctionnalités intéressantes est la possibilité d’appliquer des effets de biseau aux formes, ajoutant ainsi de la profondeur et de la dimension à vos visuels.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
-  Aspose.Slides pour .NET : assurez-vous que la bibliothèque Aspose.Slides est installée. Vous pouvez le télécharger depuis le[site web](https://releases.aspose.com/slides/net/).
- Environnement de développement : configurez votre environnement de développement .NET et possédez une compréhension de base de C#.
- Répertoire de documents : créez un répertoire pour vos documents dans lequel les fichiers de présentation générés seront enregistrés.
## Importer des espaces de noms
Dans votre code C#, incluez les espaces de noms nécessaires pour accéder aux fonctionnalités Aspose.Slides.
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Étape 1 : Configurez votre répertoire de documents
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
Assurez-vous que le répertoire de documents existe, en le créant s'il n'est pas déjà présent.
## Étape 2 : créer une instance de présentation
```csharp
Presentation pres = new Presentation();
ISlide slide = pres.Slides[0];
```
Initialisez une instance de présentation et ajoutez une diapositive avec laquelle travailler.
## Étape 3 : ajouter une forme à la diapositive
```csharp
IAutoShape shape = slide.Shapes.AddAutoShape(ShapeType.Ellipse, 30, 30, 100, 100);
shape.FillFormat.FillType = FillType.Solid;
shape.FillFormat.SolidFillColor.Color = Color.Green;
ILineFillFormat format = shape.LineFormat.FillFormat;
format.FillType = FillType.Solid;
format.SolidFillColor.Color = Color.Orange;
shape.LineFormat.Width = 2.0;
```
Créez une forme automatique (ellipse dans cet exemple) et personnalisez ses propriétés de remplissage et de ligne.
## Étape 4 : Définir les propriétés ThreeDFormat
```csharp
shape.ThreeDFormat.Depth = 4;
shape.ThreeDFormat.BevelTop.BevelType = BevelPresetType.Circle;
shape.ThreeDFormat.BevelTop.Height = 6;
shape.ThreeDFormat.BevelTop.Width = 6;
shape.ThreeDFormat.Camera.CameraType = CameraPresetType.OrthographicFront;
shape.ThreeDFormat.LightRig.LightType = LightRigPresetType.ThreePt;
shape.ThreeDFormat.LightRig.Direction = LightingDirection.Top;
```
Spécifiez les propriétés tridimensionnelles, notamment le type de biseau, la hauteur, la largeur, le type de caméra, le type de lumière et la direction.
## Étape 5 : Enregistrez la présentation
```csharp
pres.Save(dataDir + "Bevel_out.pptx", SaveFormat.Pptx);
```
Enregistrez la présentation avec les effets de biseau appliqués dans un fichier PPTX.
## Conclusion
Toutes nos félicitations! Vous avez appliqué avec succès des effets de biseau à une forme de votre présentation à l'aide d'Aspose.Slides pour .NET. Expérimentez avec différents paramètres pour libérer tout le potentiel des améliorations visuelles de vos diapositives.
## Questions fréquemment posées
### 1. Puis-je appliquer des effets de biseau à d’autres formes ?
Oui, vous pouvez appliquer des effets de biseau à diverses formes en ajustant le type et les propriétés de la forme en conséquence.
### 2. Comment puis-je changer la couleur du biseau ?
 Modifier le`SolidFillColor.Color` propriété au sein de`BevelTop` propriété pour changer la couleur du biseau.
### 3. Aspose.Slides est-il compatible avec le dernier framework .NET ?
Oui, Aspose.Slides est régulièrement mis à jour pour garantir la compatibilité avec les derniers frameworks .NET.
### 4. Puis-je appliquer plusieurs effets de biseau à une seule forme ?
Bien que cela ne soit pas courant, vous pouvez expérimenter en empilant plusieurs formes ou en manipulant les propriétés de biseau pour obtenir un effet similaire.
### 5. Existe-t-il d'autres effets 3D disponibles dans Aspose.Slides ?
Absolument! Aspose.Slides offre une variété d'effets 3D pour ajouter de la profondeur et du réalisme à vos éléments de présentation.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
