---
"description": "Apprenez à formater et à animer des graphiques dans Aspose.Slides pour .NET, en améliorant vos présentations avec des visuels captivants."
"linktitle": "Formatage et animation de graphiques dans Aspose.Slides"
"second_title": "API de traitement PowerPoint Aspose.Slides .NET"
"title": "Formatage et animation de graphiques dans Aspose.Slides"
"url": "/fr/net/chart-formatting-and-animation/chart-formatting-and-animation/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Formatage et animation de graphiques dans Aspose.Slides


Créer des présentations percutantes avec des graphiques et des animations dynamiques peut considérablement renforcer l'impact de votre message. Aspose.Slides pour .NET vous permet d'y parvenir. Dans ce tutoriel, nous vous guiderons dans l'animation et la mise en forme de graphiques avec Aspose.Slides pour .NET. Nous décomposerons les étapes en sections faciles à comprendre pour vous permettre de bien comprendre le concept.

## Prérequis

Avant de vous lancer dans la mise en forme et l'animation de graphiques avec Aspose.Slides, vous aurez besoin des éléments suivants :

1. Aspose.Slides pour .NET : Assurez-vous d'avoir installé Aspose.Slides pour .NET. Si ce n'est pas déjà fait, vous pouvez [téléchargez-le ici](https://releases.aspose.com/slides/net/).

2. Présentation existante : vous disposez d'une présentation existante contenant un graphique que vous souhaitez formater et animer.

3. Connaissances de base en C# : la familiarité avec C# sera utile pour mettre en œuvre les étapes.

Maintenant, commençons.

## Importer des espaces de noms

Pour commencer, vous devez importer les espaces de noms nécessaires pour accéder aux fonctionnalités d'Aspose.Slides. Dans votre projet C#, ajoutez les éléments suivants :

```csharp
﻿using Aspose.Slides.Charts;
using Aspose.Slides.Export;
using Aspose.Slides.Animation;
using Aspose.Slides;
```

## Animation des éléments de catégories dans un graphique

### Étape 1 : Charger la présentation et accéder au graphique

Tout d'abord, chargez votre présentation existante et accédez au graphique à animer. Cet exemple suppose que le graphique se trouve sur la première diapositive de votre présentation.

```csharp
using (Presentation presentation = new Presentation("Your Document Directory\\ExistingChart.pptx"))
{
    var slide = presentation.Slides[0] as Slide;
    var shapes = slide.Shapes as ShapeCollection;
    var chart = shapes[0] as IChart;
}
```

### Étape 2 : ajouter une animation aux éléments des catégories

Ajoutons maintenant une animation aux éléments des catégories. Dans cet exemple, nous utilisons un effet de fondu.

```csharp
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

for (int i = 0; i < chart.ChartData.Categories.Count; i++)
{
    ((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, i, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
}
```

### Étape 3 : Enregistrer la présentation

Enfin, enregistrez la présentation modifiée sur le disque.

```csharp
presentation.Save("Your Document Directory\\AnimatingCategoriesElements_out.pptx", SaveFormat.Pptx);
```

## Série animée dans le graphique

### Étape 1 : Charger la présentation et accéder au graphique

Semblable à l’exemple précédent, vous chargerez la présentation et accéderez au graphique.

```csharp
using (Presentation presentation = new Presentation("Your Document Directory\\ExistingChart.pptx"))
{
    var slide = presentation.Slides[0] as Slide;
    var shapes = slide.Shapes as ShapeCollection;
    var chart = shapes[0] as IChart;
}
```

### Étape 2 : ajouter une animation à la série

Ajoutons maintenant une animation à la série de graphiques. Nous utilisons ici aussi un effet de fondu.

```csharp
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

for (int i = 0; i < chart.ChartData.Series.Count; i++)
{
    ((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, i, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
}
```

### Étape 3 : Enregistrer la présentation

Enregistrez la présentation modifiée avec la série animée.

```csharp
presentation.Save("Your Document Directory\\AnimatingSeries_out.pptx", SaveFormat.Pptx);
```

## Animation des éléments de la série dans le graphique

### Étape 1 : Charger la présentation et accéder au graphique

Comme précédemment, chargez la présentation et accédez au graphique.

```csharp
using (Presentation presentation = new Presentation("Your Document Directory\\ExistingChart.pptx"))
{
    var slide = presentation.Slides[0] as Slide;
    var shapes = slide.Shapes as ShapeCollection;
    var chart = shapes[0] as IChart;
}
```

### Étape 2 : ajouter une animation aux éléments de la série

Dans cette étape, vous ajouterez une animation aux éléments de la série, créant ainsi un effet visuel impressionnant.

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

### Étape 3 : Enregistrer la présentation

N'oubliez pas de sauvegarder la présentation avec les éléments de la série animée.

```csharp
presentation.Save("Your Document Directory\\AnimatingSeriesElements_out.pptx", SaveFormat.Pptx);
```

Félicitations ! Vous savez maintenant comment formater et animer des graphiques dans Aspose.Slides pour .NET. Ces techniques peuvent rendre vos présentations plus attrayantes et informatives.

## Conclusion

Aspose.Slides pour .NET offre de puissants outils de mise en forme et d'animation de graphiques, vous permettant de créer des présentations visuellement attrayantes qui captiveront votre public. En suivant ce guide étape par étape, vous maîtriserez l'art de l'animation de graphiques et améliorerez vos présentations.

## FAQ

### 1. Où puis-je trouver la documentation d'Aspose.Slides pour .NET ?

Vous pouvez accéder à la documentation à l'adresse [https://reference.aspose.com/slides/net/](https://reference.aspose.com/slides/net/).

### 2. Comment télécharger Aspose.Slides pour .NET ?

Vous pouvez télécharger Aspose.Slides pour .NET à partir de [https://releases.aspose.com/slides/net/](https://releases.aspose.com/slides/net/).

### 3. Existe-t-il un essai gratuit disponible ?

Oui, vous pouvez obtenir un essai gratuit d'Aspose.Slides pour .NET sur [https://releases.aspose.com/](https://releases.aspose.com/).

### 4. Puis-je acheter une licence temporaire pour Aspose.Slides pour .NET ?

Oui, vous pouvez acheter une licence temporaire sur [https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/).

### 5. Où puis-je obtenir de l'aide ou poser des questions sur Aspose.Slides pour .NET ?

Pour obtenir de l'aide et poser des questions, visitez le forum Aspose.Slides à l'adresse [https://forum.aspose.com/](https://forum.aspose.com/).



{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}