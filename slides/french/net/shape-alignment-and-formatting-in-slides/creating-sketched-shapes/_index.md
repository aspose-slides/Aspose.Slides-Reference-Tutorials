---
"description": "Apprenez à ajouter des formes esquissées créatives à vos diapositives de présentation avec Aspose.Slides pour .NET. Améliorez l'attrait visuel sans effort !"
"linktitle": "Créer des formes esquissées dans des diapositives de présentation avec Aspose.Slides"
"second_title": "API de traitement PowerPoint Aspose.Slides .NET"
"title": "Créez de superbes formes esquissées avec Aspose.Slides"
"url": "/fr/net/shape-alignment-and-formatting-in-slides/creating-sketched-shapes/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Créez de superbes formes esquissées avec Aspose.Slides

## Introduction
Bienvenue dans notre guide étape par étape pour créer des formes esquissées dans vos diapositives de présentation avec Aspose.Slides pour .NET. Si vous souhaitez ajouter une touche de créativité à vos présentations, les formes esquissées offrent une esthétique unique et dessinée à la main. Dans ce tutoriel, nous vous expliquerons le processus en le décomposant en étapes simples pour une expérience fluide.
## Prérequis
Avant de plonger dans le didacticiel, assurez-vous que vous disposez des prérequis suivants :
- Aspose.Slides pour .NET : Assurez-vous d'avoir installé la bibliothèque Aspose.Slides pour .NET. Vous pouvez la télécharger. [ici](https://releases.aspose.com/slides/net/).
- Environnement de développement : configurez un environnement de développement .NET avec votre IDE préféré.
## Importer des espaces de noms
Commencez par importer les espaces de noms nécessaires dans votre projet .NET. Cette étape vous permettra d'accéder aux classes et fonctionnalités nécessaires à l'utilisation d'Aspose.Slides.
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
## Étape 1 : Configurer le projet
Commencez par créer un nouveau projet .NET ou ouvrez-en un existant. Assurez-vous d'inclure Aspose.Slides dans vos références de projet.
## Étape 2 : Initialiser Aspose.Slides
Initialisez Aspose.Slides en ajoutant l'extrait de code suivant. Cela configure la présentation et spécifie les chemins de sortie du fichier de présentation et de l'image miniature.
```csharp
string dataDir = "Your Document Directory";
string outPptxFile = Path.Combine(dataDir, "SketchedShapes_out.pptx");
string outPngFile = Path.Combine(dataDir, "SketchedShapes_out.png");
using (Presentation pres = new Presentation())
{
    // Passez aux étapes suivantes...
}
```
## Étape 3 : Ajouter une forme esquissée
Ajoutons maintenant une forme esquissée à la diapositive. Dans cet exemple, nous allons ajouter un rectangle avec un effet d'esquisse à main levée.
```csharp
IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 20, 20, 300, 150);
shape.FillFormat.FillType = FillType.NoFill;
// Transformer une forme en esquisse d'un style à main levée
shape.LineFormat.SketchFormat.SketchType = LineSketchType.Scribble;
```
## Étape 4 : Générer une miniature
Générez une miniature de la diapositive pour visualiser la forme esquissée. Enregistrez la miniature au format PNG.
```csharp
pres.Slides[0].GetThumbnail(4/3f, 4/3f).Save(outPngFile, ImageFormat.Png);
```
## Étape 5 : Enregistrer la présentation
Enregistrez le fichier de présentation avec la forme esquissée.
```csharp
pres.Save(outPptxFile, SaveFormat.Pptx);
```
Et voilà ! Vous avez créé avec succès une présentation avec des formes esquissées avec Aspose.Slides pour .NET.
## Conclusion
Ajouter des formes esquissées à vos diapositives de présentation peut améliorer l'attrait visuel et captiver votre public. Avec Aspose.Slides pour .NET, le processus devient simple et vous permet de libérer votre créativité sans effort.
## FAQ
### 1. Puis-je personnaliser l’effet esquissé ?
Oui, Aspose.Slides pour .NET offre diverses options de personnalisation pour les effets d'esquisse. Consultez le [documentation](https://reference.aspose.com/slides/net/) pour des informations détaillées.
### 2. Existe-t-il un essai gratuit disponible ?
Bien sûr ! Vous pouvez essayer gratuitement Aspose.Slides pour .NET. [ici](https://releases.aspose.com/).
### 3. Où puis-je obtenir de l’aide ?
Pour toute assistance ou question, visitez le [Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### 4. Comment puis-je acheter Aspose.Slides pour .NET ?
Pour acheter Aspose.Slides pour .NET, visitez le [page d'achat](https://purchase.aspose.com/buy).
### 5. Proposez-vous des licences temporaires ?
Oui, des licences temporaires sont disponibles [ici](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}