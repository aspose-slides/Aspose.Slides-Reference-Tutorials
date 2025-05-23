---
"description": "Apprenez à définir des hyperliens macro dans vos présentations avec Aspose.Slides pour .NET. Améliorez l'interactivité et captivez votre public."
"linktitle": "Gestion des hyperliens à l'aide de macros"
"second_title": "API de traitement PowerPoint Aspose.Slides .NET"
"title": "Comment définir un clic sur un lien hypertexte macro dans Aspose.Slides pour .NET"
"url": "/fr/net/hyperlink-manipulation/macro-hyperlink/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Comment définir un clic sur un lien hypertexte macro dans Aspose.Slides pour .NET


Dans le monde du développement logiciel moderne, la création de présentations dynamiques et interactives est essentielle. Aspose.Slides pour .NET est une bibliothèque puissante qui vous permet de travailler avec des présentations de manière fluide. Que vous créiez une présentation professionnelle ou un diaporama pédagogique, la possibilité de définir des clics sur des macros hyperliens peut grandement améliorer l'expérience utilisateur. Dans ce guide étape par étape, nous vous expliquerons comment définir un clic sur un macro hyperlien avec Aspose.Slides pour .NET. 

## Prérequis

Avant de plonger dans le didacticiel étape par étape, vous devez avoir quelques prérequis en place :

1. Visual Studio : assurez-vous que Visual Studio est installé sur votre ordinateur, car ce sera notre environnement de développement.

2. Aspose.Slides pour .NET : La bibliothèque Aspose.Slides pour .NET doit être installée. Vous pouvez la télécharger ici. [ici](https://releases.aspose.com/slides/net/).

3. Connaissances de base de C# : la familiarité avec le langage de programmation C# est essentielle pour suivre ce didacticiel.

## Importer des espaces de noms

Dans la première étape, importons les espaces de noms nécessaires pour travailler avec Aspose.Slides :

### Étape 1 : Importer les espaces de noms

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

Nous avons importé le `Aspose.Slides` espace de noms, qui est l'espace de noms principal pour travailler avec des présentations, et le `Aspose.Slides.Export` espace de noms.

## Paramétrage du clic sur un lien hypertexte de macro

Passons maintenant à la partie principale de ce tutoriel : définir un clic sur un lien hypertexte macro dans votre présentation.

### Étape 2 : Initialiser la présentation

Tout d’abord, nous devons initialiser une nouvelle présentation.

```csharp
using (Presentation presentation = new Presentation())
{
    // Votre code ira ici.
}
```

Dans cette instruction using, vous créez un nouvel objet de présentation et effectuez toutes vos opérations à l'intérieur de celui-ci.

### Étape 3 : ajouter une forme automatique

Pour définir un clic sur un lien hypertexte macro, vous aurez besoin d'un objet sur lequel l'utilisateur peut cliquer. Dans cet exemple, nous utiliserons une forme automatique comme élément cliquable.

```csharp
IAutoShape shape = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.BlankButton, 20, 20, 80, 30);
```

Ici, nous créons une forme automatique de type « BlankButton » avec des coordonnées spécifiques (20, 20) et des dimensions de 80 x 30. Vous pouvez personnaliser ces valeurs pour les adapter à la mise en page de votre présentation.

### Étape 4 : Définir le clic sur le lien hypertexte de la macro

Vient maintenant la partie où vous définissez le clic sur le lien hypertexte de la macro. Vous devrez fournir un nom de macro en paramètre.

```csharp
string macroName = "TestMacro";
shape.HyperlinkManager.SetMacroHyperlinkClick(macroName);
```

Dans cet exemple, nous avons défini le clic sur le lien hypertexte de la macro sur « TestMacro ». Lorsque l'utilisateur clique sur la forme automatique, cette macro est déclenchée.

### Étape 5 : Récupérer les informations

Vous pouvez également récupérer des informations sur l'hyperlien que vous avez défini.

```csharp
Console.WriteLine("External URL is {0}", shape.HyperlinkClick.ExternalUrl);
Console.WriteLine("Shape action type is {0}", shape.HyperlinkClick.ActionType);
```

Ces lignes de code vous permettent d'imprimer l'URL externe et le type d'action de l'hyperlien.

Et voilà ! Vous avez réussi à définir un clic sur un lien hypertexte macro dans votre présentation avec Aspose.Slides pour .NET.

## Conclusion

Dans ce tutoriel, nous avons appris à définir un clic sur un lien hypertexte macro dans votre présentation avec Aspose.Slides pour .NET. Cette fonctionnalité peut s'avérer précieuse pour créer des présentations interactives et dynamiques qui captivent votre public. Avec Aspose.Slides pour .NET, vous disposez d'un outil puissant pour propulser le développement de vos présentations.

Il est maintenant temps d'expérimenter et de créer des présentations captivantes avec des liens hypertexte macro personnalisés. N'hésitez pas à explorer [Aspose.Slides pour la documentation .NET](https://reference.aspose.com/slides/net/) pour des informations et des possibilités plus approfondies.

## FAQ (Foire aux questions)

### Puis-je utiliser Aspose.Slides pour .NET avec d’autres langages de programmation ?
Aspose.Slides est principalement conçu pour .NET, mais Aspose propose des bibliothèques similaires pour d'autres langages de programmation, tels que Java.

### Aspose.Slides pour .NET est-elle une bibliothèque gratuite ?
Aspose.Slides pour .NET est une bibliothèque commerciale avec une version d'essai gratuite. Vous pouvez la télécharger ici. [ici](https://releases.aspose.com/).

### Existe-t-il des limitations à l’utilisation de macros dans les présentations créées avec Aspose.Slides pour .NET ?
Aspose.Slides pour .NET vous permet de travailler avec des macros, mais vous devez être conscient des considérations de sécurité et de compatibilité lors de l'utilisation de macros dans des présentations.

### Puis-je personnaliser l’apparence de la forme automatique utilisée pour l’hyperlien ?
Oui, vous pouvez personnaliser l'apparence de la forme automatique en ajustant ses propriétés, telles que la taille, la couleur et la police.

### Où puis-je obtenir de l'aide ou du support pour Aspose.Slides pour .NET ?
Si vous rencontrez des problèmes ou avez des questions, vous pouvez demander de l'aide sur le forum d'assistance Aspose [ici](https://forum.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}