---
title: Comment utiliser Aspose.Slides .NET pour récupérer un classeur à partir d'un graphique
linktitle: Récupérer un classeur à partir d'un graphique
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez comment récupérer un classeur à partir d'un graphique dans des présentations PowerPoint à l'aide d'Aspose.Slides pour .NET. Suivez notre guide étape par étape pour extraire efficacement les données.
type: docs
weight: 12
url: /fr/net/additional-chart-features/chart-recover-workbook/
---

Si vous souhaitez travailler avec des présentations PowerPoint dans .NET, Aspose.Slides for .NET est une bibliothèque puissante qui peut vous aider à atteindre vos objectifs. Dans ce didacticiel, nous vous guiderons tout au long du processus de récupération d'un classeur à partir d'un graphique dans une présentation PowerPoint à l'aide d'Aspose.Slides pour .NET. Cette fonctionnalité puissante peut être utile lorsque vous devez extraire des données de graphiques dans vos présentations. Nous décomposerons le processus en étapes faciles à suivre, garantissant que vous comprenez clairement comment accomplir cette tâche.

## Conditions préalables

Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :

### 1. Aspose.Slides pour .NET

Aspose.Slides pour .NET doit être installé et configuré dans votre environnement de développement .NET. Si vous ne l'avez pas déjà fait, vous pouvez le télécharger et l'installer à partir du site Web.

[Téléchargez Aspose.Slides pour .NET](https://releases.aspose.com/slides/net/)

### 2. Présentation PowerPoint

Vous aurez besoin d'une présentation PowerPoint avec un graphique à partir duquel vous souhaitez récupérer le classeur. Assurez-vous que le fichier de présentation est prêt.

## Importation des espaces de noms nécessaires

Dans cette étape, vous devrez importer les espaces de noms requis pour travailler efficacement avec Aspose.Slides pour .NET.

### Étape 1 : Importer les espaces de noms

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

Maintenant, décomposons le processus de récupération d'un classeur à partir d'un graphique dans une présentation PowerPoint en plusieurs étapes.

## Étape 1 : Définir le répertoire des documents

```csharp
// Le chemin d'accès au répertoire des documents.
string dataDir = "Your Document Directory";
```

Dans cette étape, vous devez spécifier le répertoire où se trouve votre présentation PowerPoint.

## Étape 2 : charger la présentation et activer la récupération du classeur

```csharp
string pptxFile = Path.Combine(dataDir, "YourPresentation.pptx");
string outPptxFile = Path.Combine(RunExamples.OutPath, "RecoveredWorkbook.pptx");

LoadOptions lo = new LoadOptions();
lo.SpreadsheetOptions.RecoverWorkbookFromChartCache = true;

using (Presentation pres = new Presentation(pptxFile, lo))
{
    // Votre code pour la récupération des graphiques va ici
    pres.Save(outPptxFile, SaveFormat.Pptx);
}
```

Au cours de cette étape, vous chargez la présentation PowerPoint à partir du fichier spécifié et activez la récupération du classeur à partir du cache de graphiques. Le`LoadOptions` L'objet est utilisé à cette fin.

## Étape 3 : accéder et utiliser les données du graphique

```csharp
IChart chart = pres.Slides[0].Shapes[0] as IChart;
IChartDataWorkbook wb = chart.ChartData.ChartDataWorkbook;
```

Au cours de cette étape, vous accédez au graphique sur la première diapositive et obtenez le classeur de données du graphique. Vous pouvez désormais travailler avec les données du classeur selon vos besoins.

## Conclusion

Dans ce didacticiel, nous avons montré comment utiliser Aspose.Slides for .NET pour récupérer un classeur à partir d'un graphique dans une présentation PowerPoint. En suivant les étapes décrites dans ce guide, vous pouvez extraire efficacement les données de vos présentations et les utiliser pour vos besoins spécifiques.

 Si vous avez des questions ou rencontrez des problèmes, n'hésitez pas à demander de l'aide à la communauté Aspose.Slides dans le[Forum Aspose.Slides](https://forum.aspose.com/). Ils sont là pour vous accompagner dans votre parcours avec Aspose.Slides pour .NET.

## Questions fréquemment posées

### 1. Qu'est-ce qu'Aspose.Slides pour .NET ?

Aspose.Slides for .NET est une puissante bibliothèque .NET permettant de travailler avec des fichiers Microsoft PowerPoint, vous permettant de créer, manipuler et convertir des présentations par programme.

### 2. Puis-je essayer Aspose.Slides pour .NET avant d'acheter ?

 Oui, vous pouvez obtenir un essai gratuit d'Aspose.Slides pour .NET pour évaluer ses fonctionnalités et capacités.[Obtenez l'essai gratuit ici](https://releases.aspose.com/).

### 3. Où puis-je trouver la documentation d'Aspose.Slides pour .NET ?

 Vous pouvez accéder à la documentation d'Aspose.Slides pour .NET[ici](https://reference.aspose.com/slides/net/). Il contient des informations détaillées, des exemples et des références API.

### 4. Comment puis-je acheter une licence pour Aspose.Slides pour .NET ?

 Pour acheter une licence pour Aspose.Slides pour .NET, visitez le site Web Aspose et utilisez le lien suivant :[Achetez Aspose.Slides pour .NET](https://purchase.aspose.com/buy).

### 5. Quelle est la longueur maximale du titre pour l’optimisation SEO ?

Pour l'optimisation du référencement, il est recommandé de conserver votre titre sous 60 caractères pour garantir qu'il s'affiche correctement dans les résultats des moteurs de recherche.