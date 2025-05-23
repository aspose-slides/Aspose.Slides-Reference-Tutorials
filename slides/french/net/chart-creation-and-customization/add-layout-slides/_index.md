---
"description": "Apprenez à améliorer vos présentations PowerPoint avec Aspose.Slides pour .NET. Ajoutez des diapositives de mise en page pour une touche professionnelle."
"linktitle": "Ajouter des diapositives de mise en page à la présentation"
"second_title": "API de traitement PowerPoint Aspose.Slides .NET"
"title": "Ajouter des diapositives de mise en page à la présentation"
"url": "/fr/net/chart-creation-and-customization/add-layout-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ajouter des diapositives de mise en page à la présentation


À l'ère du numérique, créer une présentation percutante est une compétence essentielle. Une présentation bien structurée et visuellement attrayante peut transmettre efficacement votre message. Aspose.Slides pour .NET est un outil puissant qui vous permet de créer des présentations percutantes en un rien de temps. Dans ce guide étape par étape, nous vous expliquerons comment utiliser Aspose.Slides pour .NET pour ajouter des diapositives de mise en page à votre présentation. Nous décomposerons le processus en étapes faciles à suivre, vous permettant ainsi de bien maîtriser les concepts. C'est parti !

## Prérequis

Avant de plonger dans le didacticiel, vous devez avoir quelques prérequis en place :

1. Bibliothèque Aspose.Slides pour .NET : La bibliothèque Aspose.Slides pour .NET doit être installée. Vous pouvez la télécharger depuis [ici](https://releases.aspose.com/slides/net/).

2. Environnement de développement : assurez-vous d’avoir configuré un environnement de développement, tel que Visual Studio, pour écrire et exécuter le code.

3. Exemple de présentation : Vous aurez besoin d'un exemple de présentation PowerPoint. Vous pouvez utiliser votre présentation existante ou en créer une nouvelle.

Maintenant que vous avez les prérequis en ordre, procédons à l'ajout de diapositives de mise en page à votre présentation.

## Importer des espaces de noms

Tout d'abord, vous devez importer les espaces de noms nécessaires dans votre projet .NET pour utiliser Aspose.Slides. Ajoutez les espaces de noms suivants à votre code :

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

## Étape 1 : instancier la présentation

Dans cette étape, nous allons créer une instance du `Presentation` classe, qui représente le fichier de présentation sur lequel vous souhaitez travailler. Voici comment procéder :

```csharp
string FilePath = @"..\..\..\Sample Files\";
string FileName = FilePath + "Adding Layout Slides.pptx";

using (Presentation p = new Presentation(FileName))
{
    // Votre code ira ici
}
```

Ici, `FileName` est le chemin d'accès à votre fichier de présentation PowerPoint. Assurez-vous d'ajuster le chemin d'accès à votre fichier en conséquence.

## Étape 2 : Choisissez une diapositive de mise en page

L'étape suivante consiste à sélectionner la diapositive de mise en page à ajouter à votre présentation. Aspose.Slides vous permet de choisir parmi différents types de diapositives de mise en page prédéfinis, tels que « Titre et objet » ou « Titre ». Si votre présentation ne propose pas de mise en page spécifique, vous pouvez également créer une mise en page personnalisée. Voici comment choisir une diapositive de mise en page :

```csharp
IMasterLayoutSlideCollection layoutSlides = p.Masters[0].LayoutSlides;
ILayoutSlide layoutSlide =
    layoutSlides.GetByType(SlideLayoutType.TitleAndObject) ??
    layoutSlides.GetByType(SlideLayoutType.Title);
```

Comme indiqué dans le code ci-dessus, nous cherchons une diapositive de type « Titre et Objet ». Si elle n'est pas trouvée, nous utilisons une disposition de type « Titre ». Vous pouvez adapter cette logique à vos besoins.

## Étape 3 : Insérer une diapositive vide

Maintenant que vous avez sélectionné une diapositive de mise en page, vous pouvez ajouter une diapositive vide avec cette mise en page à votre présentation. Pour ce faire, utilisez l'outil `InsertEmptySlide` méthode. Voici le code de cette étape :

```csharp
p.Slides.InsertEmptySlide(0, layoutSlide);
```

Dans cet exemple, nous insérons la diapositive vide à la position 0, mais vous pouvez spécifier une position différente si nécessaire.

## Étape 4 : Enregistrer la présentation

Enfin, il est temps d'enregistrer votre présentation mise à jour. Vous pouvez utiliser l' `Save` Méthode pour enregistrer la présentation au format souhaité. Voici le code :

```csharp
p.Save(FileName, SaveFormat.Pptx);
```

Assurez-vous d'ajuster le `FileName` variable pour enregistrer la présentation avec le nom de fichier et le format souhaités.

Félicitations ! Vous avez ajouté une diapositive de mise en page à votre présentation avec Aspose.Slides pour .NET. Cela améliore la structure et l'esthétique de vos diapositives, rendant votre présentation plus attrayante.

## Conclusion

Dans ce tutoriel, nous avons découvert comment utiliser Aspose.Slides pour .NET pour ajouter des diapositives de mise en page à votre présentation. Avec une mise en page adaptée, votre contenu sera présenté de manière plus organisée et visuellement plus agréable. Aspose.Slides simplifie ce processus et vous permet de créer facilement des présentations professionnelles.

N'hésitez pas à tester différents types de diapositives et à personnaliser vos présentations selon vos besoins. Avec Aspose.Slides pour .NET, vous disposez d'un outil puissant pour améliorer vos compétences en présentation.

## Foire aux questions (FAQ)

### Qu'est-ce qu'Aspose.Slides pour .NET ?
Aspose.Slides pour .NET est une bibliothèque .NET permettant aux développeurs de travailler avec des présentations PowerPoint par programmation. Elle offre un large éventail de fonctionnalités pour créer, modifier et manipuler des fichiers PowerPoint.

### Où puis-je trouver la documentation d'Aspose.Slides pour .NET ?
Vous pouvez trouver la documentation sur [Documentation Aspose.Slides pour .NET](https://reference.aspose.com/slides/net/)Il offre des informations détaillées et des exemples pour vous aider à démarrer.

### Existe-t-il une version d'essai gratuite d'Aspose.Slides pour .NET disponible ?
Oui, vous pouvez accéder à un essai gratuit d'Aspose.Slides pour .NET [ici](https://releases.aspose.com/)Cet essai vous permet d'explorer les capacités de la bibliothèque avant de procéder à un achat.

### Comment puis-je obtenir une licence temporaire pour Aspose.Slides pour .NET ?
Vous pouvez obtenir un permis temporaire en visitant [ce lien](https://purchase.aspose.com/temporary-license/)Une licence temporaire est utile à des fins d’évaluation et de test.

### Où puis-je obtenir de l'aide ou demander de l'aide avec Aspose.Slides pour .NET ?
Si vous avez des questions ou avez besoin d'aide, vous pouvez visiter le forum Aspose.Slides pour .NET à l'adresse [Forum communautaire Aspose](https://forum.aspose.com/)La communauté est active et utile pour répondre aux requêtes des utilisateurs.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}