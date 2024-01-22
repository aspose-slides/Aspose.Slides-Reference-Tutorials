---
title: Comment définir un clic de lien hypertexte de macro dans Aspose.Slides pour .NET
linktitle: Gestion des hyperliens à l'aide de macros
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez comment définir des hyperliens de macro dans vos présentations avec Aspose.Slides pour .NET. Améliorez l’interactivité et engagez votre public.
type: docs
weight: 13
url: /fr/net/hyperlink-manipulation/macro-hyperlink/
---

Dans le monde du développement de logiciels moderne, la création de présentations dynamiques et interactives est un aspect clé. Aspose.Slides for .NET est une bibliothèque puissante qui vous permet de travailler avec des présentations de manière transparente. Que vous créiez une présentation professionnelle ou un diaporama éducatif, la possibilité de définir des clics sur des liens hypertextes macro peut considérablement améliorer l'expérience utilisateur. Dans ce guide étape par étape, nous vous guiderons tout au long du processus de définition d'un clic de lien hypertexte de macro à l'aide d'Aspose.Slides pour .NET. 

## Conditions préalables

Avant de plonger dans le didacticiel étape par étape, vous devez respecter quelques conditions préalables :

1.Visual Studio : assurez-vous que Visual Studio est installé sur votre ordinateur, car ce sera notre environnement de développement.

 2.Aspose.Slides pour .NET : vous devrez installer la bibliothèque Aspose.Slides pour .NET. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/slides/net/).

3.Connaissance de base de C# : une familiarité avec le langage de programmation C# est essentielle pour suivre ce didacticiel.

## Importer des espaces de noms

Dans un premier temps, importons les espaces de noms nécessaires pour travailler avec Aspose.Slides :

### Étape 1 : Importer les espaces de noms

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

 Nous avons importé le`Aspose.Slides` l'espace de noms, qui est l'espace de noms principal pour travailler avec des présentations, et l'espace de noms`Aspose.Slides.Export` espace de noms.

## Définition du clic sur le lien hypertexte d'une macro

Passons maintenant à la partie principale de ce didacticiel : définir un clic de lien hypertexte de macro dans votre présentation.

### Étape 2 : initialiser la présentation

Tout d’abord, nous devons initialiser une nouvelle présentation.

```csharp
using (Presentation presentation = new Presentation())
{
    // Votre code ira ici.
}
```

Dans cette instruction using, vous créez un nouvel objet de présentation et effectuez toutes vos opérations à l'intérieur.

### Étape 3 : ajouter une forme automatique

Pour définir un clic sur un lien hypertexte de macro, vous aurez besoin d'un objet sur lequel l'utilisateur peut cliquer. Dans cet exemple, nous utiliserons une forme automatique comme élément cliquable.

```csharp
IAutoShape shape = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.BlankButton, 20, 20, 80, 30);
```

Ici, nous créons une forme automatique de type "BlankButton" à des coordonnées spécifiques (20, 20) et avec des dimensions de 80x30. Vous pouvez personnaliser ces valeurs en fonction de la mise en page de votre présentation.

### Étape 4 : Définir le clic sur le lien hypertexte de la macro

Vient maintenant la partie où vous définissez le clic sur le lien hypertexte de la macro. Vous devrez fournir un nom de macro en tant que paramètre.

```csharp
string macroName = "TestMacro";
shape.HyperlinkManager.SetMacroHyperlinkClick(macroName);
```

Dans cet exemple, nous avons défini le clic du lien hypertexte de la macro sur "TestMacro". Lorsque l'utilisateur clique sur la forme automatique, cela déclenchera cette macro.

### Étape 5 : Récupérer des informations

Vous pouvez également récupérer des informations sur le lien hypertexte que vous avez défini.

```csharp
Console.WriteLine("External URL is {0}", shape.HyperlinkClick.ExternalUrl);
Console.WriteLine("Shape action type is {0}", shape.HyperlinkClick.ActionType);
```

Ces lignes de code permettent d'imprimer l'URL externe et le type d'action du lien hypertexte.

Et c'est tout! Vous avez réussi à définir un clic sur un lien hypertexte de macro dans votre présentation à l'aide d'Aspose.Slides pour .NET.

## Conclusion

Dans ce didacticiel, nous avons appris à définir un clic sur un lien hypertexte de macro dans votre présentation à l'aide d'Aspose.Slides pour .NET. Cela peut s'avérer une fonctionnalité précieuse pour créer des présentations interactives et dynamiques qui engagent votre public. Avec Aspose.Slides pour .NET, vous disposez d'un outil puissant pour faire passer le développement de votre présentation au niveau supérieur.

 Il est maintenant temps d'expérimenter et de créer des présentations captivantes avec des hyperliens macro personnalisés. N'hésitez pas à explorer le[Aspose.Slides pour la documentation .NET](https://reference.aspose.com/slides/net/) pour des informations et des possibilités plus détaillées.

## FAQ (Foire aux questions)

### Puis-je utiliser Aspose.Slides pour .NET avec d’autres langages de programmation ?
Aspose.Slides est principalement conçu pour .NET, mais Aspose propose des bibliothèques similaires pour d'autres langages de programmation, tels que Java.

### Aspose.Slides pour .NET est-il une bibliothèque gratuite ?
Aspose.Slides for .NET est une bibliothèque commerciale avec une version d'essai gratuite disponible. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/).

### Existe-t-il des limites à l’utilisation de macros dans les présentations créées avec Aspose.Slides pour .NET ?
Aspose.Slides pour .NET vous permet de travailler avec des macros, mais vous devez être conscient des considérations de sécurité et de compatibilité lorsque vous utilisez des macros dans des présentations.

### Puis-je personnaliser l’apparence de la forme automatique utilisée pour le lien hypertexte ?
Oui, vous pouvez personnaliser l'apparence de la forme automatique en ajustant ses propriétés, telles que la taille, la couleur et la police.

### Où puis-je obtenir de l’aide ou du support pour Aspose.Slides pour .NET ?
 Si vous rencontrez des problèmes ou avez des questions, vous pouvez demander de l'aide sur le forum d'assistance Aspose.[ici](https://forum.aspose.com/).