---
"description": "Apprenez à créer des présentations par programmation avec Aspose.Slides pour .NET. Guide étape par étape avec code source pour une automatisation efficace."
"linktitle": "Créer de nouvelles présentations par programmation"
"second_title": "API de traitement PowerPoint Aspose.Slides .NET"
"title": "Créer de nouvelles présentations par programmation"
"url": "/fr/net/presentation-manipulation/create-new-presentations-programmatically/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Créer de nouvelles présentations par programmation


Si vous souhaitez créer des présentations par programmation en .NET, Aspose.Slides pour .NET est un outil puissant pour vous aider à réaliser cette tâche efficacement. Ce tutoriel vous guidera pas à pas dans la création de nouvelles présentations à l'aide du code source fourni.

## Introduction à Aspose.Slides pour .NET

Aspose.Slides pour .NET est une bibliothèque robuste qui permet aux développeurs de travailler avec des présentations PowerPoint par programmation. Que vous ayez besoin de générer des rapports, d'automatiser des présentations ou de manipuler des diapositives, Aspose.Slides offre un large éventail de fonctionnalités pour vous simplifier la tâche.

## Étape 1 : Configuration de votre environnement

Avant de nous plonger dans le code, vous devez configurer votre environnement de développement. Assurez-vous de disposer des prérequis suivants :

- Visual Studio ou tout autre environnement de développement .NET.
- Bibliothèque Aspose.Slides pour .NET (vous pouvez la télécharger) [ici](https://releases.aspose.com/slides/net/)).

## Étape 2 : Créer une présentation

Commençons par créer une nouvelle présentation en utilisant le code suivant :

```csharp
// Créer une présentation
Presentation pres = new Presentation();
```

Ce code initialise un nouvel objet de présentation, qui sert de base à votre fichier PowerPoint.

## Étape 3 : Ajout d'une diapositive de titre

Dans la plupart des présentations, la première diapositive est la diapositive de titre. Voici comment en ajouter une :

```csharp
// Ajouter la diapositive de titre
Slide slide = pres.AddTitleSlide();
```

Ce code ajoute une diapositive de titre à votre présentation.

## Étape 4 : Définition du titre et du sous-titre

Maintenant, définissons le titre et le sous-titre de votre diapositive de titre :

```csharp
// Définir le texte du titre
((TextHolder)slide.Placeholders[0]).Text = "Slide Title Heading";

// Définir le texte des sous-titres
((TextHolder)slide.Placeholders[1]).Text = "Slide Title Sub-Heading";
```

Remplacez « Titre de la diapositive » et « Sous-titre du titre de la diapositive » par les titres souhaités.

## Étape 5 : Enregistrer votre présentation

Enfin, enregistrons votre présentation dans un fichier :

```csharp
// Écrire la sortie sur le disque
pres.Write("outAsposeSlides.ppt");
```

Ce code enregistre votre présentation sous le nom « outAsposeSlides.ppt » dans le répertoire de votre projet.

## Conclusion

Félicitations ! Vous venez de créer une présentation PowerPoint par programmation avec Aspose.Slides pour .NET. Cette puissante bibliothèque vous offre la flexibilité nécessaire pour automatiser et personnaliser vos présentations en toute simplicité.

Vous pouvez désormais commencer à intégrer ce code dans vos projets .NET pour générer des présentations dynamiques adaptées à vos besoins spécifiques.

## FAQ

1. ### Aspose.Slides pour .NET est-il gratuit à utiliser ?
   Non, Aspose.Slides pour .NET est une bibliothèque commerciale. Vous trouverez des informations sur les tarifs et les licences ici. [ici](https://purchase.aspose.com/buy).

2. ### Ai-je besoin d’autorisations spéciales pour utiliser Aspose.Slides pour .NET dans mes projets ?
   Vous aurez besoin d'une licence valide pour utiliser Aspose.Slides pour .NET. Vous pouvez obtenir une licence temporaire. [ici](https://purchase.aspose.com/temporary-license/) pour évaluation.

3. ### Où puis-je trouver de l'assistance pour Aspose.Slides pour .NET ?
   Pour une assistance technique et des discussions, vous pouvez visiter le forum Aspose.Slides [ici](https://forum.aspose.com/).

4. ### Puis-je essayer Aspose.Slides pour .NET avant d'acheter ?
   Oui, vous pouvez télécharger une version d'essai gratuite d'Aspose.Slides pour .NET [ici](https://releases.aspose.com/)La version d'essai présente des limitations, assurez-vous donc de vérifier si elle répond à vos besoins.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}