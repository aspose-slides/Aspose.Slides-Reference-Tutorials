---
title: Création d'une forme rectangulaire simple dans des diapositives de présentation à l'aide d'Aspose.Slides
linktitle: Création d'une forme rectangulaire simple dans des diapositives de présentation à l'aide d'Aspose.Slides
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez comment créer une forme de rectangle simple dans des diapositives PowerPoint à l'aide d'Aspose.Slides pour .NET. Ce guide étape par étape fournit le code source et les instructions pour ajouter, personnaliser et améliorer vos présentations par programmation.
type: docs
weight: 12
url: /fr/net/shape-alignment-and-formatting-in-slides/creating-simple-rectangle-shape/
---

## Introduction à Aspose.Slides pour .NET

Aspose.Slides for .NET est une bibliothèque puissante qui permet aux développeurs de travailler avec des présentations PowerPoint par programme. Il offre un large éventail de fonctionnalités pour créer, manipuler et gérer des éléments de présentation, notamment des diapositives, des formes, du texte, des images, etc. Dans ce guide, nous nous concentrerons sur la création d'une forme de rectangle simple dans une diapositive de présentation en utilisant les capacités d'Aspose.Slides pour .NET.

## Configuration de l'environnement de développement

Avant de plonger dans le code, configurons notre environnement de développement. Suivez ces étapes:

1.  Téléchargez Aspose.Slides pour .NET : visitez le[page de téléchargement](https://releases.aspose.com/slides/net/) et sélectionnez la version compatible avec votre projet.

2. Installez Aspose.Slides : après le téléchargement, installez Aspose.Slides en ajoutant la référence DLL à votre projet.

3. Créer un nouveau projet : créez un nouveau projet .NET à l'aide de votre environnement de développement préféré (Visual Studio, par exemple).

## Créer une nouvelle présentation

Commençons par créer une nouvelle présentation PowerPoint à l'aide d'Aspose.Slides pour .NET.

```csharp
using Aspose.Slides;

class Program
{
    static void Main(string[] args)
    {
        // Créer une nouvelle présentation
        Presentation presentation = new Presentation();

        // Ajouter une diapositive vierge à la présentation
        Slide slide = presentation.Slides.AddEmptySlide();

        // Votre code pour ajouter la forme du rectangle ira ici

        // Enregistrez la présentation
        presentation.Save("RectangleShapePresentation.pptx", SaveFormat.Pptx);
    }
}
```

## Ajout d'une forme rectangulaire à la diapositive

Maintenant que notre diapositive de présentation est prête, ajoutons-y une forme de rectangle.

```csharp
// Ajouter une forme de rectangle à la diapositive
double x = 100; // Coordonnée X de la forme
double y = 100; // Coordonnée Y de la forme
double width = 200; // Largeur de la forme
double height = 100; // Hauteur de la forme

slide.Shapes.AddRectangle(x, y, width, height);
```

## Personnalisation de la forme du rectangle

Vous pouvez personnaliser divers aspects de la forme du rectangle, tels que sa couleur de remplissage, son style de bordure, etc.

```csharp
// Obtenez la forme ajoutée (rectangle)
IShape rectangle = slide.Shapes[0];

// Personnaliser la couleur de remplissage
rectangle.FillFormat.SolidFillColor.Color = Color.Blue;

// Personnaliser la bordure
rectangle.LineFormat.Width = 2; // Largeur de la bordure
rectangle.LineFormat.DashStyle = LineDashStyle.DashDot; // Style de bordure
rectangle.LineFormat.FillFormat.SolidFillColor.Color = Color.Red; // Couleur de la bordure
```

## Sauvegarde de la présentation

Une fois que vous avez ajouté et personnalisé la forme du rectangle, il est temps d'enregistrer la présentation.

```csharp
// Enregistrez la présentation
presentation.Save("RectangleShapePresentation.pptx", SaveFormat.Pptx);
```

## Conclusion

Dans ce guide, nous avons exploré comment créer une forme de rectangle simple dans une diapositive de présentation à l'aide d'Aspose.Slides pour .NET. Nous avons couvert les étapes de base de la configuration de l'environnement de développement, de la création d'une nouvelle présentation, de l'ajout d'une forme de rectangle, de la personnalisation de son apparence et de l'enregistrement de la présentation finale. Avec Aspose.Slides pour .NET, vous pouvez facilement automatiser et améliorer vos présentations PowerPoint, en ajoutant une couche de dynamisme et d'interactivité.

## FAQ

### Comment installer Aspose.Slides pour .NET ?

Pour installer Aspose.Slides pour .NET, procédez comme suit :

1.  Visiter le[page de téléchargement](https://releases.aspose.com/slides/net/).
2. Choisissez la version compatible avec votre projet.
3. Ajoutez la référence DLL Aspose.Slides à votre projet .NET.

### Puis-je personnaliser la couleur de remplissage de la forme du rectangle ?

 Oui, vous pouvez personnaliser la couleur de remplissage de la forme du rectangle à l'aide de l'option`FillFormat` propriété. Accédez simplement à la forme`FillFormat` et définissez le paramètre souhaité`SolidFillColor`.

### Comment enregistrer la présentation après avoir ajouté la forme rectangulaire ?

Vous pouvez enregistrer la présentation en utilisant le`Save` méthode du`Presentation` classe. Fournissez le nom de fichier souhaité et le format de sauvegarde souhaité (tel que`SaveFormat.Pptx`).

### Aspose.Slides pour .NET convient-il uniquement aux formes rectangulaires ?

Non, Aspose.Slides pour .NET prend en charge un large éventail de formes et d'éléments de présentation. Vous pouvez créer et manipuler des formes telles que des rectangles, des cercles, des flèches, etc.

### Où puis-je trouver plus de documentation sur Aspose.Slides pour .NET ?

 Vous pouvez trouver une documentation détaillée et des références API pour Aspose.Slides for .NET sur le[page de documentation](https://reference.aspose.com/slides/net/).