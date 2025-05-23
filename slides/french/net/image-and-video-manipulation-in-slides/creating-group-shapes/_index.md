---
"description": "Apprenez à créer des formes de groupe dans PowerPoint avec Aspose.Slides pour .NET. Suivez notre guide étape par étape pour des présentations visuellement attrayantes."
"linktitle": "Créer des formes de groupe dans les diapositives de présentation avec Aspose.Slides"
"second_title": "API de traitement PowerPoint Aspose.Slides .NET"
"title": "Aspose.Slides – Création de formes de groupe dans .NET"
"url": "/fr/net/image-and-video-manipulation-in-slides/creating-group-shapes/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides – Création de formes de groupe dans .NET

## Introduction
Si vous souhaitez améliorer l'attrait visuel de vos diapositives de présentation et organiser votre contenu plus efficacement, l'intégration de formes de groupe est une solution performante. Aspose.Slides pour .NET permet de créer et de manipuler facilement des formes de groupe dans vos présentations PowerPoint. Dans ce tutoriel, nous vous expliquerons comment créer des formes de groupe avec Aspose.Slides, en procédant par étapes simples.
## Prérequis
Avant de plonger dans le didacticiel, assurez-vous de disposer des éléments suivants :
- Aspose.Slides pour .NET : Assurez-vous d'avoir installé la bibliothèque Aspose.Slides. Vous pouvez la télécharger depuis le [site web](https://releases.aspose.com/slides/net/).
- Environnement de développement : configurez un environnement de travail avec un IDE compatible .NET, tel que Visual Studio.
- Connaissances de base de C# : Familiarisez-vous avec les bases du langage de programmation C#.
## Importer des espaces de noms
Dans votre projet C#, commencez par importer les espaces de noms nécessaires :
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Étape 1 : instancier la classe de présentation

Créer une instance de `Presentation` classe et spécifiez le répertoire où sont stockés vos documents :

```csharp
string dataDir = "Your Documents Directory";
using (Presentation pres = new Presentation())
{
    // Continuez avec les étapes suivantes dans ce bloc d'utilisation
}
```

## Étape 2 : Accéder à la première diapositive

Récupérer la première diapositive de la présentation :

```csharp
ISlide sld = pres.Slides[0];
```

## Étape 3 : Accéder à la collection de formes

Accéder à la collection de formes sur la diapositive :

```csharp
IShapeCollection slideShapes = sld.Shapes;
```

## Étape 4 : Ajout d'une forme de groupe

Ajouter une forme de groupe à la diapositive :

```csharp
IGroupShape groupShape = slideShapes.AddGroupShape();
```

## Étape 5 : Ajout de formes à l'intérieur de la forme de groupe

Remplissez la forme de groupe avec des formes individuelles :

```csharp
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 300, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 300, 100, 100);
```

## Étape 6 : Ajout d'un cadre de forme de groupe

Définir le cadre pour la forme du groupe entier :

```csharp
groupShape.Frame = new ShapeFrame(100, 300, 500, 40, NullableBool.False, NullableBool.False, 0);
```

## Étape 7 : Enregistrer la présentation

Enregistrez la présentation modifiée dans le répertoire spécifié :

```csharp
pres.Save(dataDir + "GroupShape_out.pptx", SaveFormat.Pptx);
```

Répétez ces étapes dans votre application C# pour créer avec succès des formes de groupe dans vos diapositives de présentation à l’aide d’Aspose.Slides.

## Conclusion
Dans ce tutoriel, nous avons exploré le processus de création de formes de groupe avec Aspose.Slides pour .NET. En suivant ces étapes, vous pouvez améliorer l'esthétique et l'organisation de vos présentations PowerPoint.
## Questions fréquemment posées
### Aspose.Slides est-il compatible avec la dernière version de .NET ?
Oui, Aspose.Slides est régulièrement mis à jour pour prendre en charge les dernières versions de .NET. Consultez le [documentation](https://reference.aspose.com/slides/net/) pour plus de détails sur la compatibilité.
### Puis-je essayer Aspose.Slides avant d'acheter ?
Absolument ! Vous pouvez télécharger une version d'essai gratuite. [ici](https://releases.aspose.com/).
### Où puis-je trouver de l'aide pour les requêtes liées à Aspose.Slides ?
Visitez Aspose.Slides [forum](https://forum.aspose.com/c/slides/11) pour le soutien et les discussions de la communauté.
### Comment obtenir une licence temporaire pour Aspose.Slides ?
Vous pouvez obtenir un permis temporaire [ici](https://purchase.aspose.com/temporary-license/).
### Où puis-je acheter une licence complète pour Aspose.Slides ?
Vous pouvez acheter une licence auprès du [page d'achat](https://purchase.aspose.com/buy).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}