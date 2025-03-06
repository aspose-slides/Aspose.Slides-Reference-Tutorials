---
title: Créez de superbes formes esquissées avec Aspose.Slides
linktitle: Création de formes esquissées dans des diapositives de présentation avec Aspose.Slides
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez comment ajouter des formes esquissées créatives à vos diapositives de présentation à l'aide d'Aspose.Slides pour .NET. Améliorez l’attrait visuel sans effort !
weight: 13
url: /fr/net/shape-alignment-and-formatting-in-slides/creating-sketched-shapes/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introduction
Bienvenue dans notre guide étape par étape sur la création de formes esquissées dans des diapositives de présentation à l'aide d'Aspose.Slides pour .NET. Si vous souhaitez ajouter une touche de créativité à vos présentations, les formes esquissées offrent une esthétique unique et dessinée à la main. Dans ce didacticiel, nous vous guiderons tout au long du processus, en le décomposant en étapes simples pour garantir une expérience fluide.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous que les conditions préalables suivantes sont remplies :
-  Aspose.Slides pour .NET : assurez-vous que la bibliothèque Aspose.Slides pour .NET est installée. Vous pouvez le télécharger[ici](https://releases.aspose.com/slides/net/).
- Environnement de développement : configurez un environnement de développement .NET avec votre IDE préféré.
## Importer des espaces de noms
Commencez par importer les espaces de noms nécessaires dans votre projet .NET. Cette étape garantit que vous avez accès aux classes et fonctionnalités requises pour travailler avec Aspose.Slides.
```csharp
using System;
using System.Collections.Generic;
using System.Drawing.Imaging;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Slides;
using Aspose.Slides.Examples.CSharp;
using Aspose.Slides.Util;
using Aspose.Slides.Export;
using Aspose.Slides.MathText;
```
## Étape 1 : configurer le projet
Commencez par créer un nouveau projet .NET ou en ouvrez un existant. Assurez-vous d'inclure Aspose.Slides dans les références de votre projet.
## Étape 2 : initialiser Aspose.Slides
Initialisez Aspose.Slides en ajoutant l’extrait de code suivant. Cela configure la présentation et spécifie les chemins de sortie pour le fichier de présentation et l'image miniature.
```csharp
string dataDir = "Your Document Directory";
string outPptxFile = Path.Combine(dataDir, "SketchedShapes_out.pptx");
string outPngFile = Path.Combine(dataDir, "SketchedShapes_out.png");
using (Presentation pres = new Presentation())
{
    // Passez aux étapes suivantes...
}
```
## Étape 3 : ajouter une forme esquissée
Maintenant, ajoutons une forme esquissée à la diapositive. Dans cet exemple, nous ajouterons un rectangle avec un effet d'esquisse à main levée.
```csharp
IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 20, 20, 300, 150);
shape.FillFormat.FillType = FillType.NoFill;
// Transformer la forme en esquisse d'un style à main levée
shape.LineFormat.SketchFormat.SketchType = LineSketchType.Scribble;
```
## Étape 4 : générer une vignette
Générez une vignette de la diapositive pour visualiser la forme esquissée. Enregistrez la vignette sous forme de fichier PNG.
```csharp
pres.Slides[0].GetThumbnail(4/3f, 4/3f).Save(outPngFile, ImageFormat.Png);
```
## Étape 5 : Enregistrer la présentation
Enregistrez le fichier de présentation avec la forme esquissée.
```csharp
pres.Save(outPptxFile, SaveFormat.Pptx);
```
C'est ça! Vous avez créé avec succès une présentation avec des formes esquissées à l'aide d'Aspose.Slides pour .NET.
## Conclusion
L'ajout de formes esquissées à vos diapositives de présentation peut améliorer l'attrait visuel et engager votre public. Avec Aspose.Slides pour .NET, le processus devient simple, vous permettant de libérer votre créativité sans effort.
## FAQ
### 1. Puis-je personnaliser l’effet esquissé ?
 Oui, Aspose.Slides pour .NET propose diverses options de personnalisation pour les effets d'esquisse. Se référer au[Documentation](https://reference.aspose.com/slides/net/) pour des informations détaillées.
### 2. Existe-t-il un essai gratuit disponible ?
 Certainement! Vous pouvez explorer un essai gratuit d'Aspose.Slides pour .NET[ici](https://releases.aspose.com/).
### 3. Où puis-je obtenir de l'aide ?
 Pour toute assistance ou question, visitez le[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### 4. Comment puis-je acheter Aspose.Slides pour .NET ?
 Pour acheter Aspose.Slides pour .NET, visitez le[page d'achat](https://purchase.aspose.com/buy).
### 5. Proposez-vous des licences temporaires ?
 Oui, des licences temporaires sont disponibles[ici](https://purchase.aspose.com/temporary-license/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
