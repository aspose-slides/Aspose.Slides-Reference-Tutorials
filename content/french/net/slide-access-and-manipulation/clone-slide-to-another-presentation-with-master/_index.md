---
title: Copier la diapositive dans une nouvelle présentation avec la diapositive principale
linktitle: Copier la diapositive dans une nouvelle présentation avec la diapositive principale
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez comment copier une diapositive dans une nouvelle présentation PowerPoint tout en conservant la diapositive principale à l'aide d'Aspose.Slides pour .NET. Ce guide complet étape par étape comprend des exemples de code source et couvre le chargement de présentations, la copie de diapositives, la préservation des animations, etc.
type: docs
weight: 20
url: /fr/net/slide-access-and-manipulation/clone-slide-to-another-presentation-with-master/
---

## Introduction à Copier la diapositive dans une nouvelle présentation avec la diapositive principale

Lorsqu'il s'agit de créer et de manipuler des présentations PowerPoint par programme, Aspose.Slides for .NET fournit une solution puissante et polyvalente. Dans ce guide étape par étape, nous vous guiderons tout au long du processus de copie d'une diapositive d'une présentation à une autre tout en préservant la diapositive principale. Nous couvrirons tous les extraits de code et explications nécessaires pour vous aider à accomplir cette tâche de manière transparente.

## Conditions préalables

Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :

- Visual Studio ou tout autre environnement de développement intégré (IDE) préféré
- .NET Framework installé
-  Bibliothèque Aspose.Slides pour .NET (téléchargement depuis[ici](https://releases.aspose.com/slides/net/)

## Étape 1 : Créer une nouvelle présentation

Ouvrez votre Visual Studio et créez un nouveau projet. Ajoutez une référence à la bibliothèque Aspose.Slides.

## Étape 2 : Charger les présentations source et destination

 Chargez les présentations source et destination à l'aide du`Presentation` classe:

```csharp
using Aspose.Slides;

// Présentation de la source de chargement
var sourcePresentation = new Presentation("source.pptx");

// Charger la présentation de la destination
var destPresentation = new Presentation("destination.pptx");
```

## Étape 3 : Copier la diapositive avec la diapositive principale

Pour copier une diapositive de la présentation source vers la présentation de destination tout en conservant le modèle de diapositive, utilisez le code suivant :

```csharp
//Copiez la diapositive de la source vers la destination
var sourceSlide = sourcePresentation.Slides[0];
var copiedSlide = destPresentation.Slides.AddClone(sourceSlide);
```

## Étape 4 : Enregistrez la présentation de destination

Après avoir copié la diapositive, enregistrez la présentation de destination :

```csharp
// Enregistrer la présentation de la destination
destPresentation.Save("output.pptx", SaveFormat.Pptx);
```

## Étape 5 : Compléter le code source

Voici le code source complet pour copier une diapositive dans une nouvelle présentation avec le modèle de diapositive :

```csharp
using Aspose.Slides;

namespace SlideCopyApp
{
    class Program
    {
        static void Main(string[] args)
        {
            // Présentation de la source de chargement
            var sourcePresentation = new Presentation("source.pptx");

            // Charger la présentation de la destination
            var destPresentation = new Presentation("destination.pptx");

            //Copiez la diapositive de la source vers la destination
            var sourceSlide = sourcePresentation.Slides[0];
            var copiedSlide = destPresentation.Slides.AddClone(sourceSlide);

            // Enregistrer la présentation de la destination
            destPresentation.Save("output.pptx", SaveFormat.Pptx);
        }
    }
}
```

## Conclusion

Dans ce guide, nous avons couvert le processus étape par étape de copie d'une diapositive d'une présentation à une autre tout en conservant la diapositive principale à l'aide d'Aspose.Slides pour .NET. Avec les extraits de code source et les explications fournis, vous êtes bien équipé pour intégrer cette fonctionnalité dans vos propres applications. Aspose.Slides simplifie l'automatisation et la personnalisation de PowerPoint, ce qui en fait un outil précieux pour divers scénarios.

## FAQ

### Comment puis-je installer la bibliothèque Aspose.Slides pour .NET ?

Vous pouvez télécharger la bibliothèque Aspose.Slides pour .NET à partir du[Site Web Aspose.Slides pour .NET](https://releases.aspose.com/slides/net/). Suivez leurs instructions d'installation pour l'intégrer à votre projet.

### Puis-je copier plusieurs diapositives à la fois en utilisant cette méthode ?

Oui, vous pouvez copier plusieurs diapositives en parcourant les diapositives de la présentation source et en ajoutant des clones à la présentation de destination.

### Cette méthode préserve-t-elle les animations et les transitions ?

Oui, copier une diapositive à l’aide de cette méthode préserve les animations, les transitions et autres éléments de la diapositive.

### Puis-je modifier la diapositive copiée dans la présentation de destination ?

Absolument, la diapositive copiée dans la présentation de destination est une instance distincte. Vous pouvez modifier son contenu, sa mise en page et ses propriétés selon vos besoins.

### Aspose.Slides est-il adapté à d’autres tâches de manipulation PowerPoint ?

Décidément, Aspose.Slides pour .NET fournit un large éventail de fonctionnalités pour la manipulation de PowerPoint, notamment la création, la modification, la conversion de diapositives, etc.