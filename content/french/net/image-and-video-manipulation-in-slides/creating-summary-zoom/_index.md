---
title: Création d'un zoom récapitulatif dans les diapositives de présentation avec Aspose.Slides
linktitle: Création d'un zoom récapitulatif dans les diapositives de présentation avec Aspose.Slides
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Apprenez à créer des diapositives de présentation captivantes avec un zoom récapitulatif à l'aide d'Aspose.Slides pour .NET. Notre guide étape par étape fournit le code source et des conseils de personnalisation pour améliorer l'interactivité.
type: docs
weight: 16
url: /fr/net/image-and-video-manipulation-in-slides/creating-summary-zoom/
---

## Introduction à Aspose.Slides pour .NET

Aspose.Slides for .NET est une bibliothèque complète qui permet aux développeurs de travailler avec des présentations PowerPoint dans leurs applications .NET. Il offre un large éventail de fonctionnalités, notamment la création, la modification et la manipulation de diapositives, de formes, de texte, d'images, etc. Dans ce guide, nous nous concentrerons sur l'utilisation d'Aspose.Slides pour .NET pour créer des diapositives de zoom récapitulatives dans les présentations.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Visual Studio installé.
- .NET Framework ou .NET Core installé.
-  Aspose.Slides pour la bibliothèque .NET. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/slides/net/).

## Configuration de l'environnement de développement

1. Créez un nouveau projet .NET dans Visual Studio.
2. Ajoutez une référence à la bibliothèque Aspose.Slides dans votre projet.

## Chargement d'une présentation

Pour commencer, chargeons une présentation PowerPoint existante :

```csharp
using Aspose.Slides;

// Charger la présentation
using var presentation = new Presentation("path_to_your_presentation.pptx");
```

## Ajout de diapositives au zoom récapitulatif

Les diapositives de zoom récapitulatif vous permettent de fournir un aperçu de plusieurs diapositives dans une seule diapositive. Ajoutons les diapositives que nous souhaitons résumer :

```csharp
// Ajouter des diapositives à résumer
var slideIndexes = new[] { 2, 3, 4 };
var summaryZoomSlide = presentation.Slides.AddSummaryZoomSlide(slideIndexes);
```

## Création de diapositives de zoom récapitulatives

Maintenant, créons la véritable diapositive de zoom récapitulatif qui affichera l'aperçu des diapositives que nous avons ajoutées précédemment :

```csharp
//Créer une diapositive de zoom récapitulatif
var summaryZoom = presentation.Slides.AddSummaryZoomSlide(new[] { summaryZoomSlide });
```

## Personnalisation du comportement du zoom récapitulatif

Vous pouvez personnaliser le comportement du zoom récapitulatif, comme la mise en page et l'apparence :

```csharp
// Personnaliser les paramètres de zoom récapitulatif
var zoomFrame = summaryZoom.Shapes.OfType<ISmartArt>().FirstOrDefault();
if (zoomFrame != null)
{
    zoomFrame.Nodes[0].TextFrame.Text = "Summary Zoom";
    zoomFrame.Nodes[0].IsHidden = true; // Cacher le titre
    zoomFrame.Nodes[1].IsHidden = true; // Masquer le contenu
}
```

## Ajout de code source pour référence

Pour votre commodité, voici le code source complet pour créer des diapositives de zoom récapitulatives :

```csharp
using Aspose.Slides;

class Program
{
    static void Main(string[] args)
    {
        using var presentation = new Presentation("path_to_your_presentation.pptx");

        var slideIndexes = new[] { 2, 3, 4 };
        var summaryZoomSlide = presentation.Slides.AddSummaryZoomSlide(slideIndexes);

        var summaryZoom = presentation.Slides.AddSummaryZoomSlide(new[] { summaryZoomSlide });

        var zoomFrame = summaryZoom.Shapes.OfType<ISmartArt>().FirstOrDefault();
        if (zoomFrame != null)
        {
            zoomFrame.Nodes[0].TextFrame.Text = "Summary Zoom";
            zoomFrame.Nodes[0].IsHidden = true;
            zoomFrame.Nodes[1].IsHidden = true;
        }

        presentation.Save("output.pptx", SaveFormat.Pptx);
    }
}
```

## Conclusion

Dans ce guide, nous avons expliqué comment utiliser Aspose.Slides pour .NET pour créer des diapositives de zoom récapitulatives dans les présentations. Cette fonctionnalité puissante peut améliorer l'interactivité et l'engagement de vos présentations, en apportant une touche professionnelle à votre contenu.

## FAQ

### Comment puis-je télécharger Aspose.Slides pour .NET ?

 Vous pouvez télécharger Aspose.Slides pour .NET à partir du[Site Web Aspose.Slides](https://releases.aspose.com/slides/net/).

### Puis-je personnaliser l’apparence des diapositives du zoom récapitulatif ?

Oui, vous pouvez personnaliser l'apparence des diapositives de zoom récapitulatif à l'aide de diverses propriétés fournies par la bibliothèque Aspose.Slides.

### Aspose.Slides est-il compatible avec .NET Framework et .NET Core ?

Oui, Aspose.Slides prend en charge à la fois .NET Framework et .NET Core, vous offrant ainsi la flexibilité de choisir votre plateforme de développement.

### Puis-je créer des diapositives de zoom récapitulatives pour des plages de diapositives spécifiques ?

Absolument! Vous pouvez sélectionner les diapositives que vous souhaitez inclure dans le zoom récapitulatif à l'aide de leurs index de diapositives.

### Comment puis-je masquer le titre et le contenu de la diapositive de zoom récapitulatif ?

 Vous pouvez utiliser le`IsHidden` propriété des nœuds SmartArt pour masquer le titre et le contenu sur la diapositive de zoom récapitulatif.