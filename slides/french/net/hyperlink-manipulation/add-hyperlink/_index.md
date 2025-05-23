---
"description": "Apprenez à ajouter des hyperliens à vos diapositives PowerPoint avec Aspose.Slides pour .NET. Améliorez vos présentations avec des éléments interactifs."
"linktitle": "Ajouter un lien hypertexte à la diapositive"
"second_title": "API de traitement PowerPoint Aspose.Slides .NET"
"title": "Ajout d'hyperliens aux diapositives dans .NET à l'aide d'Aspose.Slides"
"url": "/fr/net/hyperlink-manipulation/add-hyperlink/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ajout d'hyperliens aux diapositives dans .NET à l'aide d'Aspose.Slides


Dans le monde des présentations numériques, l'interactivité est essentielle. Ajouter des hyperliens à vos diapositives peut rendre votre présentation plus attrayante et informative. Aspose.Slides pour .NET est une bibliothèque puissante qui vous permet de créer, modifier et manipuler des présentations PowerPoint par programmation. Dans ce tutoriel, nous vous montrerons comment ajouter des hyperliens à vos diapositives avec Aspose.Slides pour .NET. 

## Prérequis

Avant de nous lancer dans l’ajout d’hyperliens aux diapositives, assurez-vous de disposer des conditions préalables suivantes :

1. Visual Studio : vous devez avoir Visual Studio installé sur votre ordinateur pour écrire et exécuter le code .NET.

2. Aspose.Slides pour .NET : la bibliothèque Aspose.Slides pour .NET doit être installée. Vous pouvez la télécharger depuis [ici](https://releases.aspose.com/slides/net/).

3. Connaissances de base en C# : une connaissance de la programmation C# sera bénéfique.

## Importer des espaces de noms

Pour commencer, vous devez importer les espaces de noms nécessaires dans votre projet C#. Dans ce cas, vous aurez besoin des espaces de noms suivants, issus de la bibliothèque Aspose.Slides :

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

Décomposons maintenant le processus d’ajout d’hyperliens aux diapositives en plusieurs étapes.

## Étape 1 : Initialiser la présentation

Commencez par créer une présentation avec Aspose.Slides. Voici comment procéder :

```csharp
using (Presentation presentation = new Presentation())
{
    // Votre code va ici
}
```

Ce code initialise une nouvelle présentation PowerPoint.

## Étape 2 : Ajouter un cadre de texte

Ajoutons maintenant un cadre de texte à votre diapositive. Ce cadre servira d'élément cliquable. 

```csharp
IAutoShape shape1 = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 600, 50, false);
shape1.AddTextFrame("Aspose: File Format APIs");
```

Le code ci-dessus crée une forme automatique rectangulaire et ajoute un cadre de texte avec le texte « Aspose : API de format de fichier ».

## Étape 3 : Ajouter un lien hypertexte

Ensuite, ajoutons un lien hypertexte au bloc de texte que vous avez créé. Cela rendra le texte cliquable.

```csharp
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick = new Hyperlink("https://www.aspose.com/");
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick.Tooltip = "More than 70% Fortune 100 companies trust Aspose APIs";
shape1.TextFrame.Paragraphs[0].Portions[0].PortionFormat.FontHeight = 32;
```

Dans cette étape, nous définissons l'URL du lien hypertexte sur « https://www.aspose.com/ » et affichons une info-bulle pour plus d'informations. Vous pouvez également formater l'apparence du lien hypertexte, comme illustré ci-dessus.

## Étape 4 : Enregistrer la présentation

Enfin, enregistrez votre présentation avec l’hyperlien ajouté.

```csharp
presentation.Save("presentation-out.pptx", SaveFormat.Pptx);
```

Ce code enregistre la présentation sous le nom « presentation-out.pptx ».

Vous avez maintenant ajouté avec succès un lien hypertexte à une diapositive à l’aide d’Aspose.Slides pour .NET.

## Conclusion

Dans ce tutoriel, nous avons découvert comment ajouter des hyperliens aux diapositives de vos présentations PowerPoint avec Aspose.Slides pour .NET. En suivant ces étapes, vous pouvez rendre vos présentations plus interactives et attrayantes, en fournissant des liens utiles vers des ressources ou des informations supplémentaires.

Pour des informations et une documentation plus détaillées, visitez le [Aspose.Slides pour la documentation .NET](https://reference.aspose.com/slides/net/).

## FAQ

### 1. Puis-je ajouter des hyperliens vers d’autres formes en plus des cadres de texte ?

Oui, vous pouvez ajouter des hyperliens à diverses formes telles que des rectangles, des images et plus encore à l'aide d'Aspose.Slides pour .NET.

### 2. Comment puis-je supprimer un lien hypertexte d’une forme dans une diapositive PowerPoint ?

Vous pouvez supprimer un lien hypertexte d'une forme en définissant le `HyperlinkClick` propriété à `null`.

### 3. Puis-je modifier l’URL du lien hypertexte de manière dynamique dans mon code ?

Absolument ! Vous pouvez mettre à jour l'URL d'un lien hypertexte à tout moment dans votre code en modifiant le `Hyperlink` propriété.

### 4. Quels autres éléments interactifs puis-je ajouter aux diapositives PowerPoint à l’aide d’Aspose.Slides ?

Aspose.Slides propose une large gamme de fonctionnalités interactives, notamment des boutons d'action, des éléments multimédias et des animations.

### 5. Aspose.Slides est-il disponible pour d'autres langages de programmation ?

Oui, Aspose.Slides est disponible pour divers langages de programmation, notamment Java et Python.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}