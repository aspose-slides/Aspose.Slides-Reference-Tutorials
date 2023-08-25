---
title: Lier toutes les polices dans le contrôleur HTML
linktitle: Lier toutes les polices dans le contrôleur HTML
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez comment lier toutes les polices dans un contrôleur HTML à l'aide d'Aspose.Slides pour .NET. Ce guide étape par étape avec le code source vous aidera à garantir un rendu cohérent des polices dans vos présentations.
type: docs
weight: 20
url: /fr/net/presentation-manipulation/link-all-fonts-in-html-controller/
---

## Introduction
Lors de la création de présentations avec du contenu dynamique, il est crucial de maintenir la cohérence des polices sur les différentes plates-formes et appareils. Aspose.Slides pour .NET fournit une solution puissante pour lier toutes les polices dans un contrôleur HTML, garantissant ainsi que vos présentations restituent les polices avec précision. Dans ce guide complet, nous vous guiderons tout au long du processus de liaison des polices dans un contrôleur HTML à l'aide d'Aspose.Slides pour .NET, avec des exemples de code source détaillés. Que vous soyez développeur ou concepteur de présentations, ce guide vous aidera à obtenir un rendu cohérent des polices dans vos présentations.

## Lier toutes les polices dans le contrôleur HTML à l'aide d'Aspose.Slides pour .NET

### Conditions préalables
Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :
- Visual Studio ou tout autre IDE .NET installé
- Bibliothèque Aspose.Slides pour .NET (téléchargement depuis[ici](https://releases.aspose.com/slides/net/))

### Étape 1 : Créer un nouveau projet .NET
Commencez par créer un nouveau projet .NET dans votre IDE préféré et configurez le projet avec les configurations nécessaires.

### Étape 2 : Ajouter une référence à Aspose.Slides
Dans votre projet, ajoutez une référence à la bibliothèque Aspose.Slides que vous avez téléchargée précédemment. Cela vous permettra d'utiliser ses fonctionnalités pour lier des polices dans un contrôleur HTML.

### Étape 3 : Charger la présentation
Chargez le fichier de présentation avec lequel vous souhaitez travailler. Voici comment procéder :

```csharp
Presentation presentation = new Presentation("your-presentation.pptx");
```

### Étape 4 : préparer le contrôleur HTML
Créez un contrôleur HTML pour gérer le processus de liaison des polices. Ce contrôleur contiendra des références aux polices que vous souhaitez utiliser dans votre présentation.

### Étape 5 : Lier les polices dans le contrôleur HTML
Parcourez les polices de votre contrôleur HTML et liez-les à votre présentation. Utilisez l'extrait de code suivant comme référence :

```csharp
foreach (var fontReference in htmlController.FontReferences)
{
    string fontPath = fontReference.Path;
    presentation.FontsManager.AddEmbeddedFont(FontData.Load(fontPath));
}
```

### Étape 6 : Appliquer les polices liées
Appliquez les polices liées aux éléments de texte souhaités dans votre présentation. Cela garantit que les polices spécifiées sont utilisées lors du rendu de la présentation.

```csharp
foreach (var slide in presentation.Slides)
{
    foreach (var shape in slide.Shapes)
    {
        if (shape is ITextFrame)
        {
            ITextFrame textFrame = (ITextFrame)shape;
            textFrame.Paragraphs[0].Portions[0].PortionFormat.FontHeight = 18; // Appliquer la taille de la police
            textFrame.Paragraphs[0].Portions[0].PortionFormat.LatinFont = "YourLinkedFont"; // Appliquer la police liée
        }
    }
}
```

### Étape 7 : Enregistrez la présentation
Après avoir lié et appliqué les polices, enregistrez la présentation modifiée dans un nouveau fichier pour conserver le modèle d'origine.

```csharp
presentation.Save("modified-presentation.pptx", SaveFormat.Pptx);
```

## FAQ

### Où puis-je télécharger la bibliothèque Aspose.Slides pour .NET ?
Vous pouvez télécharger la bibliothèque Aspose.Slides pour .NET à partir de la page des versions[ici](https://releases.aspose.com/slides/net/).

### Puis-je lier tous les types de polices à l’aide d’Aspose.Slides pour .NET ?
Oui, vous pouvez lier des polices TrueType, des polices OpenType et d'autres types de polices pris en charge à l'aide d'Aspose.Slides pour .NET.

### La liaison de polices dans un contrôleur HTML est-elle une pratique courante ?
La liaison des polices dans un contrôleur HTML est une pratique recommandée pour garantir un rendu cohérent des polices sur différentes plates-formes et appareils.

### Comment les polices liées affectent-elles la taille du fichier de présentation ?
Les polices liées peuvent augmenter la taille du fichier de présentation en raison de l'inclusion de données de police. Cependant, ils garantissent un rendu précis des polices.

### Puis-je lier des polices provenant de sources externes, telles que Google Fonts ?
Aspose.Slides pour .NET vous permet de lier des polices à partir de sources locales. Pour les sources externes telles que Google Fonts, vous devrez peut-être télécharger les polices et les héberger localement.

### Aspose.Slides est-il adapté à d’autres modifications de présentation ?
Absolument. Aspose.Slides offre une large gamme de fonctionnalités pour modifier les présentations, notamment le formatage du texte, les transitions de diapositives, etc.

## Conclusion
La liaison de polices dans un contrôleur HTML à l'aide d'Aspose.Slides pour .NET vous permet d'obtenir un rendu de police cohérent dans vos présentations. En suivant ce guide étape par étape et en utilisant les exemples de code source fournis, vous pouvez vous assurer que vos présentations conservent leur apparence souhaitée sur différents appareils et plates-formes.