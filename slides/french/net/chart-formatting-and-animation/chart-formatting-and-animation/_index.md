---
title: Formatage et animation des graphiques dans Aspose.Slides
linktitle: Formatage et animation des graphiques dans Aspose.Slides
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Apprenez à formater et à animer des graphiques dans Aspose.Slides pour .NET, améliorant ainsi vos présentations avec des visuels captivants.
type: docs
weight: 10
url: /fr/net/chart-formatting-and-animation/chart-formatting-and-animation/
---

Créer des présentations convaincantes avec des graphiques et des animations dynamiques peut grandement améliorer l'impact de votre message. Aspose.Slides pour .NET vous permet d’y parvenir. Dans ce didacticiel, nous vous guiderons tout au long du processus d'animation et de formatage de graphiques à l'aide d'Aspose.Slides pour .NET. Nous diviserons les étapes en sections gérables pour nous assurer que vous comprenez parfaitement le concept.

## Conditions préalables

Avant de vous plonger dans le formatage et l'animation de graphiques avec Aspose.Slides, vous aurez besoin des éléments suivants :

1.  Aspose.Slides pour .NET : assurez-vous d'avoir installé Aspose.Slides pour .NET. Si ce n'est pas déjà fait, vous pouvez[Télécharger les ici](https://releases.aspose.com/slides/net/).

2. Présentation existante : disposez d'une présentation existante contenant un graphique que vous souhaitez formater et animer.

3. Connaissances de base en C# : une connaissance de C# sera utile pour la mise en œuvre des étapes.

Maintenant, commençons.

## Importer des espaces de noms

Pour commencer, vous devrez importer les espaces de noms nécessaires pour accéder aux fonctionnalités Aspose.Slides. Dans votre projet C#, ajoutez ce qui suit :

```csharp
﻿using Aspose.Slides.Charts;
using Aspose.Slides.Export;
using Aspose.Slides.Animation;
using Aspose.Slides;
```

## Animation d'éléments de catégories dans un graphique

### Étape 1 : charger la présentation et accéder au graphique

Tout d’abord, chargez votre présentation existante et accédez au graphique que vous souhaitez animer. Cet exemple suppose que le graphique se trouve sur la première diapositive de votre présentation.

```csharp
using (Presentation presentation = new Presentation("Your Document Directory\\ExistingChart.pptx"))
{
    var slide = presentation.Slides[0] as Slide;
    var shapes = slide.Shapes as ShapeCollection;
    var chart = shapes[0] as IChart;
}
```

### Étape 2 : ajouter une animation aux éléments des catégories

Maintenant, ajoutons une animation aux éléments des catégories. Dans cet exemple, nous utilisons un effet de fondu entrant.

```csharp
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

for (int i = 0; i < chart.ChartData.Categories.Count; i++)
{
    ((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, i, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
}
```

### Étape 3 : Enregistrez la présentation

Enfin, enregistrez la présentation modifiée sur le disque.

```csharp
presentation.Save("Your Document Directory\\AnimatingCategoriesElements_out.pptx", SaveFormat.Pptx);
```

## Animation de séries dans un graphique

### Étape 1 : charger la présentation et accéder au graphique

Semblable à l’exemple précédent, vous allez charger la présentation et accéder au graphique.

```csharp
using (Presentation presentation = new Presentation("Your Document Directory\\ExistingChart.pptx"))
{
    var slide = presentation.Slides[0] as Slide;
    var shapes = slide.Shapes as ShapeCollection;
    var chart = shapes[0] as IChart;
}
```

### Étape 2 : ajouter une animation à la série

Maintenant, ajoutons une animation à la série de graphiques. Nous utilisons également ici un effet de fondu.

```csharp
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

for (int i = 0; i < chart.ChartData.Series.Count; i++)
{
    ((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, i, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
}
```

### Étape 3 : Enregistrez la présentation

Enregistrez la présentation modifiée avec la série animée.

```csharp
presentation.Save("Your Document Directory\\AnimatingSeries_out.pptx", SaveFormat.Pptx);
```

## Animation d'éléments de série dans un graphique

### Étape 1 : charger la présentation et accéder au graphique

Comme auparavant, chargez la présentation et accédez au graphique.

```csharp
using (Presentation presentation = new Presentation("Your Document Directory\\ExistingChart.pptx"))
{
    var slide = presentation.Slides[0] as Slide;
    var shapes = slide.Shapes as ShapeCollection;
    var chart = shapes[0] as IChart;
}
```

### Étape 2 : ajouter une animation aux éléments de la série

Au cours de cette étape, vous ajouterez une animation aux éléments de la série, créant ainsi un effet visuel impressionnant.

```csharp
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

for (int seriesIndex = 0; seriesIndex < chart.ChartData.Series.Count; seriesIndex++)
{
    for (int elementIndex = 0; elementIndex < chart.ChartData.Categories.Count; elementIndex++)
    {
        ((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInSeries, seriesIndex, elementIndex, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
    }
}
```

### Étape 3 : Enregistrez la présentation

N'oubliez pas de sauvegarder la présentation avec les éléments de la série animée.

```csharp
presentation.Save("Your Document Directory\\AnimatingSeriesElements_out.pptx", SaveFormat.Pptx);
```

Toutes nos félicitations! Vous avez maintenant appris à formater et animer des graphiques dans Aspose.Slides pour .NET. Ces techniques peuvent rendre vos présentations plus attrayantes et informatives.

## Conclusion

Aspose.Slides pour .NET fournit des outils puissants pour le formatage et l'animation de graphiques, vous permettant de créer des présentations visuellement attrayantes qui captivent votre public. En suivant ce guide étape par étape, vous pourrez maîtriser l'art de l'animation graphique et améliorer vos présentations.

## FAQ

### 1. Où puis-je trouver la documentation d'Aspose.Slides pour .NET ?

 Vous pouvez accéder à la documentation sur[https://reference.aspose.com/slides/net/](https://reference.aspose.com/slides/net/).

### 2. Comment télécharger Aspose.Slides pour .NET ?

 Vous pouvez télécharger Aspose.Slides pour .NET à partir de[https://releases.aspose.com/slides/net/](https://releases.aspose.com/slides/net/).

### 3. Existe-t-il un essai gratuit disponible ?

 Oui, vous pouvez obtenir un essai gratuit d'Aspose.Slides pour .NET sur[https://releases.aspose.com/](https://releases.aspose.com/).

### 4. Puis-je acheter une licence temporaire pour Aspose.Slides pour .NET ?

 Oui, vous pouvez acheter une licence temporaire à[https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/).

### 5. Où puis-je obtenir de l'aide ou poser des questions sur Aspose.Slides pour .NET ?

 Pour obtenir de l'aide et des questions, visitez le forum Aspose.Slides à l'adresse[https://forum.aspose.com/](https://forum.aspose.com/).

