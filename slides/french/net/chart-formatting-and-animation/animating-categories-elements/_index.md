---
title: Animations de graphiques puissantes avec Aspose.Slides pour .NET
linktitle: Animation d'éléments de catégories dans un graphique
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Apprenez à animer des éléments de graphique dans PowerPoint avec Aspose.Slides pour .NET. Guide étape par étape pour des présentations époustouflantes.
type: docs
weight: 11
url: /fr/net/chart-formatting-and-animation/animating-categories-elements/
---

Dans le monde des présentations, les animations peuvent donner vie à votre contenu, notamment lorsqu'il s'agit de graphiques. Aspose.Slides pour .NET offre une gamme de fonctionnalités puissantes qui vous permettent de créer de superbes animations pour vos graphiques. Dans ce guide étape par étape, nous vous guiderons tout au long du processus d'animation des éléments de catégorie dans un graphique à l'aide d'Aspose.Slides pour .NET.

## Conditions préalables

Avant de plonger dans le didacticiel, vous devez disposer des conditions préalables suivantes :

-  Aspose.Slides pour .NET : assurez-vous que Aspose.Slides pour .NET est installé dans votre environnement de développement. Si ce n'est pas déjà fait, vous pouvez le télécharger depuis[ici](https://releases.aspose.com/slides/net/).

- Présentation existante : vous devez disposer d'une présentation PowerPoint avec un graphique que vous souhaitez animer. Si vous n'en avez pas, créez un exemple de présentation avec un graphique à des fins de test.

Maintenant que tout est en place, commençons à animer ces éléments du graphique !

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

Dans cette étape, nous chargeons la présentation PowerPoint existante contenant le graphique que vous souhaitez animer. Nous accédons ensuite à l'objet graphique dans la première diapositive.

## Étape 2 : Animer les éléments des catégories

```csharp
// Animer les éléments des catégories
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

Cette étape ajoute un effet d'animation "Fade" à l'ensemble du graphique, le faisant apparaître après l'animation précédente.

Ensuite, nous ajouterons une animation aux éléments individuels de chaque catégorie du graphique. C’est là que la vraie magie opère.

## Étape 3 : Animer des éléments individuels

Nous décomposerons l'animation des éléments individuels au sein de chaque catégorie en les étapes suivantes :

### Étape 3.1 : Animation d'éléments dans la catégorie 0

```csharp
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

Ici, nous animons des éléments individuels dans la catégorie 0 du graphique, les faisant apparaître les uns après les autres. L'effet "Apparaître" est utilisé pour cette animation.

### Étape 3.2 : Animation des éléments de la catégorie 1

```csharp
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

Le processus est répété pour la catégorie 1, en animant ses éléments individuels à l'aide de l'effet « Apparaître ».

### Étape 3.3 : Animation des éléments de la catégorie 2

```csharp
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

Le même processus se poursuit pour la catégorie 2, en animant ses éléments individuellement.

## Étape 4 : Enregistrez la présentation

```csharp
// Écrire le fichier de présentation sur le disque
presentation.Save(dataDir + "AnimatingCategoriesElements_out.pptx", SaveFormat.Pptx);
}
```

Dans la dernière étape, nous enregistrons la présentation avec les animations nouvellement ajoutées. Désormais, les éléments de votre graphique s’animeront magnifiquement lorsque vous exécuterez la présentation.

## Conclusion

L'animation d'éléments de catégorie dans un graphique peut améliorer l'attrait visuel de vos présentations. Avec Aspose.Slides pour .NET, ce processus devient simple et efficace. Vous avez appris à importer des espaces de noms, à charger une présentation et à ajouter des animations à l'ensemble du graphique et à ses éléments individuels. Faites preuve de créativité et rendez vos présentations plus attrayantes avec Aspose.Slides pour .NET.

## FAQ

### 1. Comment puis-je télécharger Aspose.Slides pour .NET ?
 Vous pouvez télécharger Aspose.Slides pour .NET à partir de[ce lien](https://releases.aspose.com/slides/net/).

### 2. Ai-je besoin d’une expérience en codage pour utiliser Aspose.Slides pour .NET ?
Bien qu'une expérience en codage soit utile, Aspose.Slides pour .NET fournit une documentation complète et des exemples pour aider les utilisateurs de tous niveaux de compétence.

### 3. Puis-je utiliser Aspose.Slides pour .NET avec n’importe quelle version de PowerPoint ?
Aspose.Slides for .NET est conçu pour fonctionner avec différentes versions de PowerPoint, garantissant ainsi la compatibilité.

### 4. Comment puis-je obtenir une licence temporaire pour Aspose.Slides pour .NET ?
 Vous pouvez obtenir une licence temporaire pour Aspose.Slides pour .NET[ici](https://purchase.aspose.com/temporary-license/).

### 5. Existe-t-il un forum communautaire pour la prise en charge d'Aspose.Slides pour .NET ?
 Oui, vous pouvez trouver un forum communautaire de soutien pour Aspose.Slides pour .NET[ici](https://forum.aspose.com/).
