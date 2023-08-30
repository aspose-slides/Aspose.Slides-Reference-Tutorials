---
title: Ajouter un lien hypertexte à la diapositive
linktitle: Ajouter un lien hypertexte à la diapositive
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez comment ajouter des liens hypertexte aux diapositives dans PowerPoint à l'aide d'Aspose.Slides pour .NET. Améliorez les présentations avec du contenu interactif.
type: docs
weight: 12
url: /fr/net/hyperlink-manipulation/add-hyperlink/
---

## Introduction à Aspose.Slides pour .NET

Aspose.Slides for .NET est une bibliothèque complète qui permet aux développeurs de créer, modifier et manipuler des présentations PowerPoint sans recourir à Microsoft Office. Il offre un large éventail de fonctionnalités, notamment l'ajout et la gestion d'hyperliens dans les diapositives.

## Conditions préalables

Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :

- Visual Studio installé sur votre système.
-  Aspose.Slides pour la bibliothèque .NET. Vous pouvez le télécharger depuis[ici](https://downloads.aspose.com/slides/net).

## Ajouter un lien hypertexte à un texte dans une diapositive

1. Créez un nouveau projet C# dans Visual Studio.
2. Ajoutez une référence à la DLL Aspose.Slides dans votre projet.
3. Utilisez le code suivant pour ajouter un lien hypertexte vers un texte dans une diapositive :

```csharp
using Aspose.Slides;

// Charger la présentation
Presentation presentation = new Presentation("presentation.pptx");

// Accéder à une diapositive
ISlide slide = presentation.Slides[0];

// Accéder à une zone de texte
ITextFrame textFrame = slide.Shapes[0] as ITextFrame;

// Ajouter une partie de texte avec un lien hypertexte
textFrame.Paragraphs[0].Portions[0].Text = "Visit our website!";
textFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick = new HyperlinkInfo("https://www.exemple.com", HyperlinkAction.MouseClick);
```

## Ajout d'un lien hypertexte à une forme dans une diapositive

1. Suivez les étapes ci-dessus pour créer un nouveau projet C# et ajouter la référence Aspose.Slides.
2. Utilisez le code suivant pour ajouter un lien hypertexte vers une forme dans une diapositive :

```csharp
using Aspose.Slides;

// Charger la présentation
Presentation presentation = new Presentation("presentation.pptx");

// Accéder à une diapositive
ISlide slide = presentation.Slides[0];

// Accéder à une forme
IShape shape = slide.Shapes[1];

// Ajouter un lien hypertexte à la forme
shape.HyperlinkClick = new HyperlinkInfo("https://www.exemple.com", HyperlinkAction.MouseClick);
```

## Ajout d'un lien hypertexte à une diapositive

1. Suivez les étapes initiales pour configurer votre projet C# et référencer la bibliothèque Aspose.Slides.
2. Utilisez le code suivant pour ajouter un lien hypertexte à une diapositive :

```csharp
using Aspose.Slides;

// Charger la présentation
Presentation presentation = new Presentation("presentation.pptx");

// Accéder à une diapositive
ISlide slide = presentation.Slides[2];

// Ajouter un lien hypertexte à la diapositive
slide.HyperlinkClick = new HyperlinkInfo("https://www.exemple.com", HyperlinkAction.MouseClick);
```

## Ajout de liens hypertextes externes

Outre les hyperliens internes, vous pouvez également ajouter des hyperliens externes à vos diapositives. Utilisez la même approche que ci-dessus, mais fournissez l’URL externe comme cible du lien hypertexte.

## Modification et suppression des hyperliens

Pour modifier un lien hypertexte existant ou le supprimer, vous pouvez accéder aux propriétés du lien hypertexte de l'élément de diapositive concerné et apporter les modifications nécessaires.

## Conclusion

L'ajout d'hyperliens aux diapositives à l'aide d'Aspose.Slides pour .NET est un processus simple qui peut considérablement améliorer l'interactivité de vos présentations. Que vous souhaitiez créer des liens vers des ressources externes ou créer une navigation dans vos diapositives, Aspose.Slides fournit les outils dont vous avez besoin pour réaliser ces tâches efficacement.

## FAQ

### Comment supprimer un lien hypertexte d’une partie de texte ?

 Pour supprimer un lien hypertexte d'une partie de texte, vous pouvez simplement définir le`HyperlinkClick` propriété à`null` pour cette partie.

### Puis-je ajouter des hyperliens vers des formes autres que des zones de texte ?

Oui, vous pouvez ajouter des hyperliens vers diverses formes, notamment des images et des formes personnalisées, à l'aide de l'outil`HyperlinkClick` propriété.

### Aspose.Slides est-il compatible avec différents formats PowerPoint ?

Oui, Aspose.Slides prend en charge divers formats PowerPoint, notamment PPTX, PPT, etc.

### Comment puis-je tester les hyperliens dans ma présentation ?

Vous pouvez exécuter la présentation dans une visionneuse ou un éditeur PowerPoint pour tester la fonctionnalité des hyperliens.

### Où puis-je télécharger la bibliothèque Aspose.Slides pour .NET ?

 Vous pouvez télécharger la bibliothèque Aspose.Slides pour .NET depuis le site Web Aspose :[Téléchargez Aspose.Slides pour .NET](https://releases.aspose.com/slides/net).