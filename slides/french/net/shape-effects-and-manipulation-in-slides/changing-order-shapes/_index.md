---
title: Remodeler les diapositives de présentation avec Aspose.Slides pour .NET
linktitle: Modification de l'ordre des formes dans les diapositives de présentation à l'aide d'Aspose.Slides
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez comment remodeler les diapositives de présentation à l'aide d'Aspose.Slides pour .NET. Suivez ce guide étape par étape pour réorganiser les formes et améliorer l'attrait visuel.
weight: 26
url: /fr/net/shape-effects-and-manipulation-in-slides/changing-order-shapes/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introduction
Créer des diapositives de présentation visuellement attrayantes est un aspect crucial d’une communication efficace. Aspose.Slides for .NET permet aux développeurs de manipuler les diapositives par programme, offrant un large éventail de fonctionnalités. Dans ce didacticiel, nous aborderons le processus de modification de l'ordre des formes dans les diapositives de présentation à l'aide d'Aspose.Slides pour .NET.
## Conditions préalables
Avant de nous lancer dans ce voyage, assurez-vous d’avoir les conditions préalables suivantes en place :
-  Aspose.Slides pour .NET : assurez-vous que la bibliothèque Aspose.Slides est intégrée à votre projet .NET. Sinon, vous pouvez le télécharger depuis le[page des versions](https://releases.aspose.com/slides/net/).
- Environnement de développement : configurez un environnement de développement fonctionnel avec Visual Studio ou tout autre outil de développement .NET.
- Compréhension de base de C# : Familiarisez-vous avec les bases du langage de programmation C#.
## Importer des espaces de noms
Dans votre projet C#, incluez les espaces de noms nécessaires pour accéder à la fonctionnalité Aspose.Slides :
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Étape 1 : Configurez votre projet
Créez un nouveau projet dans Visual Studio ou dans votre environnement de développement .NET préféré. Assurez-vous qu'Aspose.Slides for .NET est référencé dans votre projet.
## Étape 2 : Charger la présentation
```csharp
string dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
## Étape 3 : accéder à la diapositive et aux formes
```csharp
ISlide slide = presentation.Slides[0];
```
## Étape 4 : ajouter une nouvelle forme
```csharp
IAutoShape shp3 = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 200, 365, 400, 150);
shp3.FillFormat.FillType = FillType.NoFill;
shp3.AddTextFrame(" ");
```
## Étape 5 : modifier le texte dans la forme
```csharp
ITextFrame txtFrame = shp3.TextFrame;
IParagraph para = txtFrame.Paragraphs[0];
IPortion portion = para.Portions[0];
portion.Text = "Watermark Text Watermark Text Watermark Text";
```
## Étape 6 : Ajouter une autre forme
```csharp
shp3 = slide.Shapes.AddAutoShape(ShapeType.Triangle, 200, 365, 400, 150);
```
## Étape 7 : modifier l'ordre des formes
```csharp
slide.Shapes.Reorder(2, shp3);
```
## Étape 8 : Enregistrez la présentation modifiée
```csharp
presentation.Save(dataDir + "Reshape_out.pptx", SaveFormat.Pptx);
```
Ceci termine le guide étape par étape pour modifier l’ordre des formes dans les diapositives de présentation à l’aide d’Aspose.Slides pour .NET.
## Conclusion
Aspose.Slides pour .NET simplifie la tâche de manipulation des diapositives de présentation par programme. En suivant ce didacticiel, vous avez appris à réorganiser les formes, vous permettant ainsi d'améliorer l'attrait visuel de vos présentations.
## FAQ
### Q : Puis-je utiliser Aspose.Slides pour .NET dans les environnements Windows et Linux ?
R : Oui, Aspose.Slides pour .NET est compatible avec les environnements Windows et Linux.
### Q : Existe-t-il des considérations en matière de licence pour l'utilisation d'Aspose.Slides dans un projet commercial ?
 R : Oui, vous pouvez trouver les détails de la licence et les options d'achat sur le[Page d'achat Aspose.Slides](https://purchase.aspose.com/buy).
### Q : Existe-t-il un essai gratuit disponible pour Aspose.Slides pour .NET ?
 R : Oui, vous pouvez explorer les fonctionnalités avec le[essai gratuit](https://releases.aspose.com/) disponible sur le site Aspose.Slides.
### Q : Où puis-je trouver de l'aide ou poser des questions concernant Aspose.Slides pour .NET ?
 R : Visitez le[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) pour obtenir du soutien et interagir avec la communauté.
### Q : Comment puis-je obtenir une licence temporaire pour Aspose.Slides pour .NET ?
 R : Vous pouvez acquérir un[permis temporaire](https://purchase.aspose.com/temporary-license/) à des fins d’évaluation.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
