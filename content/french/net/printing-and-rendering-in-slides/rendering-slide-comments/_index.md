---
title: Rendu des commentaires de diapositive dans Aspose.Slides
linktitle: Rendu des commentaires de diapositive dans Aspose.Slides
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez comment afficher les commentaires de diapositives dans des présentations PowerPoint à l'aide d'Aspose.Slides pour .NET. Ce guide étape par étape fournit des exemples de code source pour accéder, personnaliser et afficher les commentaires par programmation.
type: docs
weight: 12
url: /fr/net/printing-and-rendering-in-slides/rendering-slide-comments/
---

## Introduction

Les commentaires de diapositives offrent des informations, des explications et des discussions précieuses liées à des diapositives spécifiques d'une présentation. Le rendu de ces commentaires par programmation peut rationaliser le processus de révision et de collaboration. Aspose.Slides for .NET simplifie cette tâche en fournissant un ensemble complet d'API pour gérer et afficher les commentaires des diapositives.

## Conditions préalables

Avant de nous lancer dans la mise en œuvre, assurez-vous que les conditions préalables suivantes sont en place :

- Visual Studio installé sur votre ordinateur.
- Compréhension de base du développement C# et .NET.
-  Aspose.Slides pour la bibliothèque .NET. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/slides/net/).

## Mise en place du projet

1. Créez un nouveau projet C# dans Visual Studio.

2. Ajoutez une référence à la bibliothèque Aspose.Slides for .NET dans votre projet.

## Chargement d'une présentation

Pour commencer, chargeons une présentation PowerPoint contenant des commentaires de diapositive :

```csharp
using Aspose.Slides;

// Charger la présentation
using var presentation = new Presentation("presentation.pptx");
```

## Accéder aux commentaires des diapositives

Parcourons ensuite les diapositives de la présentation et accédons aux commentaires associés à chaque diapositive :

```csharp
// Parcourez les diapositives
foreach (var slide in presentation.Slides)
{
    // Accéder aux commentaires des diapositives
    var comments = slide.Comments;
    foreach (var comment in comments)
    {
        // Accéder aux propriétés des commentaires
        var author = comment.Author;
        var text = comment.Text;
        
        // Traitez le commentaire si nécessaire
    }
}
```

## Rendu des commentaires sur les diapositives

Maintenant, affichons les commentaires sur les diapositives. Nous ajouterons les commentaires sous forme de zones de texte sous chaque diapositive :

```csharp
foreach (var slide in presentation.Slides)
{
    // Accéder aux commentaires des diapositives
    var comments = slide.Comments;
    foreach (var comment in comments)
    {
        // Créer une zone de texte pour le commentaire
        var textBox = slide.Shapes.AddTextFrame("");
        var textFrame = textBox.TextFrame;
        
        // Définir les propriétés du commentaire sous forme de texte
        textFrame.Text = $"{comment.Author}: {comment.Text}";
        
        // Positionnez la zone de texte sous la diapositive
        textBox.Left = slide.SlideSize.Size.Width / 2;
        textBox.Top = slide.SlideSize.Size.Height + 20;
        
        // Personnalisez l'apparence de la zone de texte si nécessaire
        
        // Traitez le commentaire si nécessaire
    }
}
```

## Personnalisation du rendu des commentaires

Vous pouvez personnaliser davantage l'apparence des commentaires rendus, comme la taille, la couleur et la position de la police. Cela vous permet d'adapter les commentaires au style de votre présentation :

```csharp
// Personnaliser l'apparence de la zone de texte
var fontHeight = 12;
var fontColor = Color.Black;
var margin = 20;

foreach (var slide in presentation.Slides)
{
    // ...
    foreach (var comment in comments)
    {
        // ...
        
        // Personnaliser l'apparence de la zone de texte
        textFrame.Paragraphs[0].Portions[0].PortionFormat.FontHeight = fontHeight;
        textFrame.Paragraphs[0].Portions[0].PortionFormat.FillFormat.SolidFillColor.Color = fontColor;
        
        // Ajuster la position de la zone de texte
        textBox.Top = slide.SlideSize.Size.Height - margin;
        margin += 30; // Augmenter la marge pour le prochain commentaire
    }
}
```

## Enregistrement de la présentation rendue

Une fois que vous avez rendu les commentaires sur les diapositives, vous pouvez enregistrer la présentation modifiée :

```csharp
// Enregistrez la présentation modifiée
presentation.Save("rendered_presentation.pptx", SaveFormat.Pptx);
```

## Conclusion

Dans ce guide, nous avons exploré comment afficher les commentaires de diapositives dans des présentations PowerPoint à l'aide d'Aspose.Slides pour .NET. En suivant les étapes décrites ci-dessus, vous pouvez accéder et afficher les commentaires par programmation, améliorant ainsi la collaboration et la communication au sein de vos diaporamas.

## FAQ

### Comment puis-je installer Aspose.Slides pour .NET ?

 Vous pouvez télécharger la bibliothèque Aspose.Slides pour .NET à partir de[ce lien](https://releases.aspose.com/slides/net/). Une fois téléchargé, vous pouvez l'ajouter comme référence dans votre projet Visual Studio.

### Puis-je personnaliser l'apparence des commentaires rendus ?

Oui, vous pouvez personnaliser l'apparence des commentaires rendus, notamment la taille, la couleur et la position de la police. Cela vous permet d'adapter les commentaires au style de votre présentation.

### Comment puis-je accéder aux propriétés des commentaires individuels ?

 Vous pouvez accéder aux propriétés des commentaires telles que l'auteur et le texte à l'aide du`Author` et`Text` propriétés de l'objet commentaire.

### Puis-je afficher les commentaires sous forme de légendes au lieu de zones de texte ?

Oui, vous pouvez afficher les commentaires sous forme de légendes en créant des formes personnalisées et en y ajoutant du texte. Vous devrez ajuster la position et l'apparence des légendes en conséquence.

### Aspose.Slides for .NET est-il adapté à d’autres tâches liées à PowerPoint ?

Absolument! Aspose.Slides pour .NET fournit une large gamme d'API pour travailler avec des présentations PowerPoint. Vous pouvez créer, modifier, convertir et manipuler divers aspects des présentations par programmation.