---
title: Création de formes de groupe dans des diapositives de présentation avec Aspose.Slides
linktitle: Création de formes de groupe dans des diapositives de présentation avec Aspose.Slides
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Apprenez à créer des diapositives de présentation captivantes avec des formes de groupe à l'aide d'Aspose.Slides pour .NET. Suivez notre guide étape par étape et notre exemple de code source pour ajouter, regrouper et transformer facilement des formes, améliorant ainsi vos présentations.
type: docs
weight: 11
url: /fr/net/image-and-video-manipulation-in-slides/creating-group-shapes/
---

## Introduction à Aspose.Slides pour .NET

Aspose.Slides for .NET est une bibliothèque complète et riche en fonctionnalités qui permet aux développeurs de manipuler des présentations PowerPoint par programme. Que vous souhaitiez créer, modifier ou convertir des fichiers de présentation, Aspose.Slides fournit une large gamme d'outils et de fonctionnalités pour simplifier le processus.

## Conditions préalables

Avant de commencer à travailler avec Aspose.Slides pour .NET, assurez-vous que les conditions préalables suivantes sont remplies :

- Visual Studio : installez Visual Studio sur votre ordinateur.
-  Bibliothèque Aspose.Slides : téléchargez et référencez la bibliothèque Aspose.Slides dans votre projet. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/slides/net/).

## Ajout d'Aspose.Slides à votre projet

1. Téléchargez la bibliothèque Aspose.Slides à partir du lien fourni.
2. Créez un nouveau projet dans Visual Studio ou ouvrez-en un existant.
3. Cliquez avec le bouton droit sur votre projet dans l'Explorateur de solutions et sélectionnez « Gérer les packages NuGet ».
4. Choisissez l'onglet "Parcourir" et recherchez "Aspose.Slides".
5. Installez le package Aspose.Slides dans votre projet.

## Créer une nouvelle présentation

Commençons par créer une nouvelle présentation PowerPoint à l'aide d'Aspose.Slides :

```csharp
using Aspose.Slides;

// Créer une nouvelle présentation
Presentation presentation = new Presentation();
```

## Ajout de formes à la diapositive

Ensuite, ajoutons quelques formes à la diapositive. Dans cet exemple, nous ajouterons deux rectangles :

```csharp
// Accédez à la première diapositive
ISlide slide = presentation.Slides[0];

// Ajouter des rectangles à la diapositive
IShape shape1 = slide.Shapes.AddRectangle(100, 100, 200, 100);
IShape shape2 = slide.Shapes.AddRectangle(300, 100, 150, 150);
```

## Regrouper des formes ensemble

Maintenant, regroupons les formes pour les gérer collectivement :

```csharp
// Formes de groupe
IGroupShape groupShape = slide.Shapes.GroupShapes(new IShape[] { shape1, shape2 });
```

## Application de transformations à des formes groupées

Vous pouvez appliquer diverses transformations aux formes groupées. Par exemple, faisons pivoter les formes groupées de 45 degrés :

```csharp
// Faites pivoter le groupe de 45 degrés
groupShape.Rotation = 45;
```

## Exemple de code source

Voici l'exemple de code source complet de création de formes de groupe à l'aide d'Aspose.Slides :

```csharp
using Aspose.Slides;

namespace GroupShapesExample
{
    class Program
    {
        static void Main(string[] args)
        {
            // Créer une nouvelle présentation
            Presentation presentation = new Presentation();

            // Accédez à la première diapositive
            ISlide slide = presentation.Slides[0];

            // Ajouter des rectangles à la diapositive
            IShape shape1 = slide.Shapes.AddRectangle(100, 100, 200, 100);
            IShape shape2 = slide.Shapes.AddRectangle(300, 100, 150, 150);

            // Formes de groupe
            IGroupShape groupShape = slide.Shapes.GroupShapes(new IShape[] { shape1, shape2 });

            // Faites pivoter le groupe de 45 degrés
            groupShape.Rotation = 45;

            // Enregistrez la présentation
            presentation.Save("GroupShapesExample.pptx", SaveFormat.Pptx);
        }
    }
}
```

## Conclusion

Dans ce didacticiel, vous avez appris à créer des formes de groupe dans des diapositives de présentation à l'aide d'Aspose.Slides pour .NET. La bibliothèque offre un moyen simple d'ajouter des formes, de les regrouper et d'appliquer des transformations pour améliorer dynamiquement vos présentations.

## FAQ

### Comment installer Aspose.Slides pour .NET ?

 Vous pouvez télécharger la bibliothèque Aspose.Slides à partir du lien fourni :[ici](https://releases.aspose.com/slides/net/). Une fois téléchargé, vous pouvez l'ajouter à votre projet à l'aide des packages NuGet.

### Puis-je appliquer différentes transformations à des formes groupées ?

Oui, vous pouvez appliquer diverses transformations telles que la rotation, la mise à l'échelle et le positionnement aux formes groupées, vous permettant ainsi de personnaliser l'apparence visuelle de vos diapositives.

### Aspose.Slides convient-il à la fois à la création et à la modification de présentations ?

Absolument! Aspose.Slides pour .NET est une bibliothèque polyvalente qui prend en charge la création, la modification et la conversion de fichiers de présentation. Il offre un large éventail de fonctionnalités pour répondre à différents besoins.

### Puis-je regrouper des formes de différents types ?

 Oui, vous pouvez regrouper des formes de différents types, telles que des rectangles, des cercles et des zones de texte, à l'aide de l'option`GroupShapes` méthode. Cela vous permet de les gérer et de les manipuler collectivement.

### Aspose.Slides convient-il uniquement aux applications .NET ?

Oui, Aspose.Slides est spécialement conçu pour les applications .NET. Cependant, il existe également des versions disponibles pour d'autres langages de programmation, tels que Java.