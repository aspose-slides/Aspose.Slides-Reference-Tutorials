---
"description": "Améliorez vos diapositives de présentation avec Aspose.Slides pour .NET ! Apprenez à appliquer des effets de biseau captivants grâce à ce guide étape par étape."
"linktitle": "Application d'effets de biseau aux formes dans les diapositives de présentation avec Aspose.Slides"
"second_title": "API de traitement PowerPoint Aspose.Slides .NET"
"title": "Maîtriser les effets de biseau dans Aspose.Slides – Tutoriel étape par étape"
"url": "/fr/net/shape-effects-and-manipulation-in-slides/applying-bevel-effects-shapes/"
"weight": 24
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Maîtriser les effets de biseau dans Aspose.Slides – Tutoriel étape par étape

## Introduction
Dans l'univers dynamique des présentations, ajouter un attrait visuel à vos diapositives peut considérablement renforcer l'impact de votre message. Aspose.Slides pour .NET offre une boîte à outils puissante pour manipuler et embellir vos diapositives de présentation par programmation. L'une de ces fonctionnalités intéressantes est la possibilité d'appliquer des effets de biseau aux formes, ajoutant ainsi profondeur et dimension à vos visuels.
## Prérequis
Avant de plonger dans le didacticiel, assurez-vous de disposer des prérequis suivants :
- Aspose.Slides pour .NET : Assurez-vous d'avoir installé la bibliothèque Aspose.Slides. Vous pouvez la télécharger depuis le [site web](https://releases.aspose.com/slides/net/).
- Environnement de développement : configurez votre environnement de développement .NET et ayez une compréhension de base de C#.
- Répertoire de documents : Créez un répertoire pour vos documents où les fichiers de présentation générés seront enregistrés.
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
Assurez-vous que le répertoire du document existe, en le créant s'il n'est pas déjà présent.
## Étape 2 : Créer une instance de présentation
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
## Étape 4 : définir les propriétés de ThreeDFormat
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
## Étape 5 : Enregistrer la présentation
```csharp
pres.Save(dataDir + "Bevel_out.pptx", SaveFormat.Pptx);
```
Enregistrez la présentation avec les effets de biseau appliqués dans un fichier PPTX.
## Conclusion
Félicitations ! Vous avez appliqué avec succès des effets de biseau à une forme de votre présentation avec Aspose.Slides pour .NET. Testez différents paramètres pour exploiter pleinement le potentiel d'amélioration visuelle de vos diapositives.
## Questions fréquemment posées
### 1. Puis-je appliquer des effets de biseau à d’autres formes ?
Oui, vous pouvez appliquer des effets de biseau à différentes formes en ajustant le type de forme et les propriétés en conséquence.
### 2. Comment puis-je changer la couleur du biseau ?
Modifier le `SolidFillColor.Color` propriété dans le `BevelTop` propriété permettant de changer la couleur du biseau.
### 3. Aspose.Slides est-il compatible avec le dernier framework .NET ?
Oui, Aspose.Slides est régulièrement mis à jour pour assurer la compatibilité avec les derniers frameworks .NET.
### 4. Puis-je appliquer plusieurs effets de biseau à une seule forme ?
Bien que cela ne soit pas courant, vous pouvez expérimenter l'empilement de plusieurs formes ou la manipulation des propriétés de biseau pour obtenir un effet similaire.
### 5. Existe-t-il d’autres effets 3D disponibles dans Aspose.Slides ?
Absolument ! Aspose.Slides propose une variété d'effets 3D pour ajouter de la profondeur et du réalisme à vos présentations.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}