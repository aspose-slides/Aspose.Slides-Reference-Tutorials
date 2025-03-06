---
title: Ajout d'hyperliens vers des diapositives dans .NET à l'aide d'Aspose.Slides
linktitle: Ajouter un lien hypertexte à la diapositive
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez comment ajouter des hyperliens aux diapositives PowerPoint avec Aspose.Slides pour .NET. Améliorez vos présentations avec des éléments interactifs.
type: docs
weight: 12
url: /fr/net/hyperlink-manipulation/add-hyperlink/
---

Dans le monde des présentations numériques, l’interactivité est essentielle. L'ajout d'hyperliens à vos diapositives peut rendre votre présentation plus attrayante et informative. Aspose.Slides pour .NET est une bibliothèque puissante qui vous permet de créer, modifier et manipuler des présentations PowerPoint par programme. Dans ce didacticiel, nous allons vous montrer comment ajouter des hyperliens à vos diapositives à l'aide d'Aspose.Slides pour .NET. 

## Conditions préalables

Avant de commencer à ajouter des hyperliens aux diapositives, assurez-vous que les conditions préalables suivantes sont remplies :

1. Visual Studio : Visual Studio doit être installé sur votre ordinateur pour écrire et exécuter le code .NET.

2. Aspose.Slides pour .NET : vous devez avoir installé la bibliothèque Aspose.Slides pour .NET. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/slides/net/).

3. Connaissances de base en C# : Une connaissance de la programmation C# sera bénéfique.

## Importer des espaces de noms

Pour commencer, vous devez importer les espaces de noms nécessaires dans votre projet C#. Dans ce cas, vous aurez besoin des espaces de noms suivants de la bibliothèque Aspose.Slides :

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

Maintenant, décomposons le processus d'ajout de liens hypertexte aux diapositives en plusieurs étapes.

## Étape 1 : initialiser la présentation

Tout d’abord, créez une nouvelle présentation à l’aide d’Aspose.Slides. Voici comment procéder :

```csharp
using (Presentation presentation = new Presentation())
{
    // Votre code va ici
}
```

Ce code initialise une nouvelle présentation PowerPoint.

## Étape 2 : Ajouter un cadre de texte

Maintenant, ajoutons un cadre de texte à votre diapositive. Ce cadre de texte servira d’élément cliquable dans votre diapositive. 

```csharp
IAutoShape shape1 = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 600, 50, false);
shape1.AddTextFrame("Aspose: File Format APIs");
```

Le code ci-dessus crée une forme automatique rectangulaire et ajoute un cadre de texte avec le texte « Aspose : API de format de fichier ».

## Étape 3 : ajouter un lien hypertexte

Ensuite, ajoutons un lien hypertexte vers le bloc de texte que vous avez créé. Cela rendra le texte cliquable.

```csharp
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick = new Hyperlink("https://www.aspose.com/");
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick.Tooltip = "More than 70% Fortune 100 companies trust Aspose APIs";
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.FontHeight = 32;
```

Dans cette étape, nous définissons l'URL du lien hypertexte sur « https://www.aspose.com/ » et fournissons une info-bulle pour des informations supplémentaires. Vous pouvez également formater l'apparence du lien hypertexte, comme indiqué ci-dessus.

## Étape 4 : Enregistrer la présentation

Enfin, enregistrez votre présentation avec le lien hypertexte ajouté.

```csharp
presentation.Save("presentation-out.pptx", SaveFormat.Pptx);
```

Ce code enregistre la présentation sous le nom « présentation-out.pptx ».

Vous avez maintenant ajouté avec succès un lien hypertexte à une diapositive à l’aide d’Aspose.Slides pour .NET.

## Conclusion

Dans ce didacticiel, nous avons expliqué comment ajouter des hyperliens vers des diapositives dans des présentations PowerPoint à l'aide d'Aspose.Slides pour .NET. En suivant ces étapes, vous pouvez rendre vos présentations plus interactives et attrayantes, en fournissant des liens précieux vers des ressources ou des informations supplémentaires.

 Pour des informations et une documentation plus détaillées, visitez le[Aspose.Slides pour la documentation .NET](https://reference.aspose.com/slides/net/).

## FAQ

### 1. Puis-je ajouter des hyperliens vers d’autres formes en plus des blocs de texte ?

Oui, vous pouvez ajouter des hyperliens vers diverses formes telles que des rectangles, des images, etc. à l'aide d'Aspose.Slides pour .NET.

### 2. Comment puis-je supprimer un lien hypertexte d’une forme dans une diapositive PowerPoint ?

 Vous pouvez supprimer un lien hypertexte d'une forme en définissant l'option`HyperlinkClick` propriété à`null`.

### 3. Puis-je modifier l'URL du lien hypertexte de manière dynamique dans mon code ?

 Absolument! Vous pouvez mettre à jour l'URL d'un lien hypertexte à tout moment dans votre code en modifiant le`Hyperlink` propriété.

### 4. Quels autres éléments interactifs puis-je ajouter aux diapositives PowerPoint à l'aide d'Aspose.Slides ?

Aspose.Slides offre une large gamme de fonctionnalités interactives, notamment des boutons d'action, des éléments multimédias et des animations.

### 5. Aspose.Slides est-il disponible pour d’autres langages de programmation ?

Oui, Aspose.Slides est disponible pour différents langages de programmation, notamment Java et Python.