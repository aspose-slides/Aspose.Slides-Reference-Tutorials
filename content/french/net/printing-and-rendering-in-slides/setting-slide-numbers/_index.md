---
title: Définition des numéros de diapositives pour les présentations à l'aide d'Aspose.Slides
linktitle: Définition des numéros de diapositives pour les présentations à l'aide d'Aspose.Slides
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez comment ajouter et personnaliser des numéros de diapositives dans des présentations PowerPoint à l'aide d'Aspose.Slides for .NET. Ce guide étape par étape fournit des exemples de code source pour configurer le projet, charger une présentation, ajouter des numéros de diapositives, personnaliser leur format et ajuster leur emplacement.
type: docs
weight: 16
url: /fr/net/printing-and-rendering-in-slides/setting-slide-numbers/
---

## Introduction à Aspose.Slides pour .NET

Aspose.Slides for .NET est une bibliothèque polyvalente qui permet aux développeurs .NET de créer, modifier et manipuler des présentations PowerPoint par programme. Il offre un large éventail de fonctionnalités pour interagir avec divers éléments des présentations, notamment des diapositives, des formes, du texte, des images, etc. Dans ce guide, nous nous concentrerons sur l'ajout et la personnalisation des numéros de diapositives à l'aide d'Aspose.Slides for .NET.

## Conditions préalables

Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :

- Visual Studio (ou tout autre environnement de développement .NET)
-  Aspose.Slides pour la bibliothèque .NET (Télécharger depuis[ici](https://releases.aspose.com/slides/net/)

## Mise en place du projet

1. Créez un nouveau projet Visual Studio (application console, par exemple).
2. Ajoutez une référence à la bibliothèque Aspose.Slides pour .NET.

## Chargement d'une présentation

Pour commencer, chargeons une présentation PowerPoint existante :

```csharp
using Aspose.Slides;

// Charger la présentation
using Presentation presentation = new Presentation("your-presentation.pptx");
```

## Ajout de numéros de diapositive

Ensuite, ajoutons des numéros de diapositive à chaque diapositive de la présentation :

```csharp
// Activer les numéros de diapositive
foreach (ISlide slide in presentation.Slides)
{
    // Ajouter une forme de numéro de diapositive
    IAutoShape slideNumberShape = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 10, 10, 50, 20);
    slideNumberShape.TextFrame.Text = (slide.SlideNumber).ToString();
}
```

## Personnalisation du format du numéro de diapositive

Vous pouvez personnaliser l'apparence des numéros de diapositive en ajustant la police, la couleur, la taille, etc. :

```csharp
foreach (IAutoShape shape in presentation.Slides[0].Shapes.OfType<IAutoShape>())
{
    // Personnaliser la police et la couleur
    ITextFrame textFrame = shape.TextFrame;
    IParagraph paragraph = textFrame.Paragraphs[0];
    IPortion portion = paragraph.Portions[0];
    
    portion.PortionFormat.FontHeight = 12;
    portion.PortionFormat.FillFormat.SolidFillColor.Color = Color.Black;
}
```

## Mise à jour de l'emplacement du numéro de diapositive

Vous pouvez également ajuster la position des numéros de diapositive sur chaque diapositive :

```csharp
foreach (ISlide slide in presentation.Slides)
{
    foreach (IAutoShape shape in slide.Shapes.OfType<IAutoShape>())
    {
        shape.Left = slide.SlideSize.Size.Width - shape.Width - 10;
        shape.Top = slide.SlideSize.Size.Height - shape.Height - 10;
    }
}
```

## Enregistrement de la présentation modifiée

Une fois que vous avez ajouté et personnalisé les numéros de diapositives, enregistrez la présentation modifiée :

```csharp
presentation.Save("output-presentation.pptx", SaveFormat.Pptx);
```

## Conclusion

Dans ce guide, nous avons exploré comment améliorer vos présentations en ajoutant et en personnalisant des numéros de diapositives à l'aide d'Aspose.Slides pour .NET. En suivant les étapes et les exemples de code fournis, vous pouvez automatiser le processus d'ajout de numéros de diapositives et créer des présentations d'aspect professionnel.

## FAQ

### Comment installer Aspose.Slides pour .NET ?

 Vous pouvez télécharger la bibliothèque Aspose.Slides pour .NET à partir de[ici](https://releases.aspose.com/slides/net/). Après le téléchargement, ajoutez une référence à la bibliothèque dans votre projet .NET.

### Puis-je personnaliser l’apparence des numéros de diapositives ?

Oui, vous pouvez personnaliser la police, la couleur, la taille et d'autres attributs des numéros de diapositive à l'aide des exemples de code fournis.

### Comment puis-je ajuster la position des numéros de diapositive sur chaque diapositive ?

Vous pouvez ajuster la position des numéros de diapositive en modifiant les coordonnées des formes des numéros de diapositive, comme indiqué dans les exemples de code.

### Aspose.Slides pour .NET sert-il uniquement à ajouter des numéros de diapositives ?

Non, Aspose.Slides pour .NET offre un large éventail de fonctionnalités au-delà de l'ajout de numéros de diapositives. Il vous permet de créer, modifier et manipuler divers éléments de présentations PowerPoint par programme.

### Les modifications sont-elles réversibles si je souhaite supprimer les numéros de diapositive ultérieurement ?

Oui, vous pouvez facilement supprimer les numéros de diapositives en supprimant les formes correspondantes des diapositives à l'aide de la bibliothèque Aspose.Slides.