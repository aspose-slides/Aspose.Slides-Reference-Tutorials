---
title: Aspose.Slides - Création de formes de groupe dans .NET
linktitle: Création de formes de groupe dans des diapositives de présentation avec Aspose.Slides
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez comment créer des formes de groupe dans PowerPoint avec Aspose.Slides pour .NET. Suivez notre guide étape par étape pour des présentations visuellement attrayantes.
type: docs
weight: 11
url: /fr/net/image-and-video-manipulation-in-slides/creating-group-shapes/
---
## Introduction
Si vous souhaitez améliorer l'attrait visuel de vos diapositives de présentation et organiser le contenu plus efficacement, l'incorporation de formes de groupe est une solution puissante. Aspose.Slides pour .NET offre un moyen transparent de créer et de manipuler des formes de groupe dans vos présentations PowerPoint. Dans ce didacticiel, nous passerons en revue le processus de création de formes de groupe à l'aide d'Aspose.Slides, en le décomposant en étapes faciles à suivre.
## Conditions préalables
Avant de plonger dans le didacticiel, assurez-vous d'avoir les éléments suivants :
-  Aspose.Slides pour .NET : assurez-vous que la bibliothèque Aspose.Slides est installée. Vous pouvez le télécharger depuis le[site web](https://releases.aspose.com/slides/net/).
- Environnement de développement : configurez un environnement de travail avec un IDE compatible .NET, tel que Visual Studio.
- Connaissance de base de C# : Familiarisez-vous avec les bases du langage de programmation C#.
## Importer des espaces de noms
Dans votre projet C#, commencez par importer les espaces de noms nécessaires :
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Étape 1 : Instancier un cours de présentation

 Créez une instance du`Presentation` class et précisez le répertoire où sont stockés vos documents :

```csharp
string dataDir = "Your Documents Directory";
using (Presentation pres = new Presentation())
{
    // Continuez avec les étapes suivantes dans ce bloc using
}
```

## Étape 2 : accéder à la première diapositive

Récupérez la première diapositive de la présentation :

```csharp
ISlide sld = pres.Slides[0];
```

## Étape 3 : Accéder à la collection de formes

Accédez à la collection de formes sur la diapositive :

```csharp
IShapeCollection slideShapes = sld.Shapes;
```

## Étape 4 : Ajout d'une forme de groupe

Ajoutez une forme de groupe à la diapositive :

```csharp
IGroupShape groupShape = slideShapes.AddGroupShape();
```

## Étape 5 : Ajout de formes à l'intérieur de la forme de groupe

Remplissez la forme de groupe avec des formes individuelles :

```csharp
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 300, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 300, 100, 100);
```

## Étape 6 : Ajout d'un cadre de forme de groupe

Définissez le cadre pour l'ensemble de la forme du groupe :

```csharp
groupShape.Frame = new ShapeFrame(100, 300, 500, 40, NullableBool.False, NullableBool.False, 0);
```

## Étape 7 : Enregistrez la présentation

Enregistrez la présentation modifiée dans votre répertoire spécifié :

```csharp
pres.Save(dataDir + "GroupShape_out.pptx", SaveFormat.Pptx);
```

Répétez ces étapes dans votre application C# pour réussir à créer des formes de groupe dans vos diapositives de présentation à l'aide d'Aspose.Slides.

## Conclusion
Dans ce didacticiel, nous avons exploré le processus de création de formes de groupe avec Aspose.Slides pour .NET. En suivant ces étapes, vous pouvez améliorer l'attrait visuel et l'organisation de vos présentations PowerPoint.
## Questions fréquemment posées
### Aspose.Slides est-il compatible avec la dernière version de .NET ?
 Oui, Aspose.Slides est régulièrement mis à jour pour prendre en charge les dernières versions de .NET. Vérifier la[Documentation](https://reference.aspose.com/slides/net/) pour les détails de compatibilité.
### Puis-je essayer Aspose.Slides avant d’acheter ?
 Absolument! Vous pouvez télécharger une version d'essai gratuite[ici](https://releases.aspose.com/).
### Où puis-je trouver de l'aide pour les requêtes liées à Aspose.Slides ?
 Visitez Aspose.Slides[forum](https://forum.aspose.com/c/slides/11) pour le soutien et les discussions de la communauté.
### Comment puis-je obtenir une licence temporaire pour Aspose.Slides ?
 Vous pouvez obtenir une licence temporaire[ici](https://purchase.aspose.com/temporary-license/).
### Où puis-je acheter une licence complète pour Aspose.Slides ?
 Vous pouvez acheter une licence auprès du[page d'achat](https://purchase.aspose.com/buy).
