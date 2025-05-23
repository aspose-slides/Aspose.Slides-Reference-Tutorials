---
"description": "Apprenez à animer des éléments de graphique dans PowerPoint avec Aspose.Slides pour .NET. Guide étape par étape pour des présentations époustouflantes."
"linktitle": "Animation des éléments de catégories dans un graphique"
"second_title": "API de traitement PowerPoint Aspose.Slides .NET"
"title": "Animations graphiques puissantes avec Aspose.Slides pour .NET"
"url": "/fr/net/chart-formatting-and-animation/animating-categories-elements/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Animations graphiques puissantes avec Aspose.Slides pour .NET


Dans le monde des présentations, les animations peuvent donner vie à votre contenu, notamment pour les graphiques. Aspose.Slides pour .NET offre un éventail de fonctionnalités puissantes pour créer des animations époustouflantes pour vos graphiques. Dans ce guide étape par étape, nous vous expliquerons comment animer des éléments de catégorie dans un graphique avec Aspose.Slides pour .NET.

## Prérequis

Avant de plonger dans le didacticiel, vous devez disposer des prérequis suivants :

- Aspose.Slides pour .NET : Assurez-vous qu'Aspose.Slides pour .NET est installé dans votre environnement de développement. Si ce n'est pas déjà fait, vous pouvez le télécharger ici. [ici](https://releases.aspose.com/slides/net/).

- Présentation existante : Vous devez disposer d'une présentation PowerPoint avec un graphique à animer. Si vous n'en avez pas, créez un exemple de présentation avec un graphique à des fins de test.

Maintenant que tout est en place, commençons à animer ces éléments de graphique !

## Importer des espaces de noms

La première étape consiste à importer les espaces de noms nécessaires pour accéder aux fonctionnalités d'Aspose.Slides. Ajoutez les espaces de noms suivants à votre projet :

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
```

## Étape 1 : Charger la présentation

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "Your Document Directory";

using (Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx"))
{
    // Obtenir la référence de l'objet graphique
    var slide = presentation.Slides[0] as Slide;
    var shapes = slide.Shapes as ShapeCollection;
    var chart = shapes[0] as IChart;
```

Dans cette étape, nous chargeons la présentation PowerPoint existante contenant le graphique à animer. Nous accédons ensuite à l'objet graphique dans la première diapositive.

## Étape 2 : Animer les éléments des catégories

```csharp
// Animer les éléments des catégories
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

Cette étape ajoute un effet d'animation « Fondu » à l'ensemble du graphique, le faisant apparaître après l'animation précédente.

Ensuite, nous ajouterons une animation aux éléments individuels de chaque catégorie du graphique. C'est là que la magie opère.

## Étape 3 : Animer des éléments individuels

Nous allons décomposer l'animation des éléments individuels de chaque catégorie selon les étapes suivantes :

### Étape 3.1 : Animation des éléments de la catégorie 0

```csharp
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

Ici, nous animons des éléments individuels de la catégorie 0 du graphique, les faisant apparaître les uns après les autres. L'effet « Apparition » est utilisé pour cette animation.

### Étape 3.2 : Animation des éléments de la catégorie 1

```csharp
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

Le processus est répété pour la catégorie 1, en animant ses éléments individuels à l'aide de l'effet « Apparaître ».

### Étape 3.3 : Animation des éléments de la catégorie 2

```csharp
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

Le même processus se poursuit pour la catégorie 2, en animant ses éléments individuellement.

## Étape 4 : Enregistrer la présentation

```csharp
// Écrire le fichier de présentation sur le disque
presentation.Save(dataDir + "AnimatingCategoriesElements_out.pptx", SaveFormat.Pptx);
}
```

Enfin, nous enregistrons la présentation avec les nouvelles animations. Vos éléments graphiques s'animeront parfaitement lors de l'exécution de la présentation.

## Conclusion

Animer des éléments de catégorie dans un graphique peut améliorer l'attrait visuel de vos présentations. Avec Aspose.Slides pour .NET, ce processus devient simple et efficace. Vous avez appris à importer des espaces de noms, à charger une présentation et à ajouter des animations au graphique entier et à ses éléments individuels. Laissez libre cours à votre créativité et rendez vos présentations plus attrayantes avec Aspose.Slides pour .NET.

## FAQ

### 1. Comment puis-je télécharger Aspose.Slides pour .NET ?
Vous pouvez télécharger Aspose.Slides pour .NET à partir de [ce lien](https://releases.aspose.com/slides/net/).

### 2. Ai-je besoin d’expérience en codage pour utiliser Aspose.Slides pour .NET ?
Bien que l'expérience en codage soit utile, Aspose.Slides pour .NET fournit une documentation complète et des exemples pour aider les utilisateurs à tous les niveaux de compétence.

### 3. Puis-je utiliser Aspose.Slides pour .NET avec n’importe quelle version de PowerPoint ?
Aspose.Slides pour .NET est conçu pour fonctionner avec différentes versions de PowerPoint, garantissant ainsi la compatibilité.

### 4. Comment puis-je obtenir une licence temporaire pour Aspose.Slides pour .NET ?
Vous pouvez obtenir une licence temporaire pour Aspose.Slides pour .NET [ici](https://purchase.aspose.com/temporary-license/).

### 5. Existe-t-il un forum communautaire pour le support d'Aspose.Slides pour .NET ?
Oui, vous pouvez trouver un forum communautaire de soutien pour Aspose.Slides pour .NET [ici](https://forum.aspose.com/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}