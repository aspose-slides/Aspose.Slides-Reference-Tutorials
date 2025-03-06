---
title: Animer une série de graphiques avec Aspose.Slides pour .NET
linktitle: Animation de séries dans un graphique
second_title: API de traitement Aspose.Slides .NET PowerPoint
description: Découvrez comment animer des séries de graphiques avec Aspose.Slides pour .NET. Engagez votre public avec des présentations dynamiques. Commencez maintenant!
weight: 12
url: /fr/net/chart-formatting-and-animation/animating-series/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Animer une série de graphiques avec Aspose.Slides pour .NET


Cherchez-vous à ajouter du piquant à vos présentations avec des graphiques animés ? Aspose.Slides pour .NET est là pour donner vie à vos graphiques. Dans ce guide étape par étape, nous allons vous montrer comment animer des séries dans un graphique à l'aide d'Aspose.Slides pour .NET. Mais avant de plonger dans l’action, abordons les conditions préalables.

## Conditions préalables

Pour réussir à animer des séries dans un graphique à l’aide d’Aspose.Slides pour .NET, vous aurez besoin des éléments suivants :

### 1. Aspose.Slides pour la bibliothèque .NET

 Assurez-vous que la bibliothèque Aspose.Slides pour .NET est installée. Si ce n'est pas déjà fait, vous pouvez le télécharger depuis[Site Web Aspose.Slides pour .NET](https://releases.aspose.com/slides/net/).

### 2. Présentation existante avec un graphique

Préparez une présentation PowerPoint (PPTX) avec un graphique existant que vous souhaitez animer.

Maintenant que nous avons couvert les conditions préalables, décomposons le processus en une série d’étapes pour animer la série de graphiques.


## Étape 1 : Importer les espaces de noms nécessaires

Vous devrez importer les espaces de noms requis dans votre code C# pour travailler avec Aspose.Slides pour .NET :

```csharp
﻿using Aspose.Slides.Charts;
using Aspose.Slides.Export;
using Aspose.Slides.Animation;
using Aspose.Slides;
```

## Étape 2 : Charger la présentation existante

Dans cette étape, chargez votre présentation PowerPoint (PPTX) existante contenant le graphique que vous souhaitez animer.

```csharp
// Chemin d'accès au répertoire des documents
string dataDir = "Your Document Directory";

// Instancier la classe Présentation qui représente un fichier de présentation
using (Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx"))
{
    // Votre code va ici
}
```

## Étape 3 : obtenir la référence de l'objet graphique

Pour utiliser le graphique dans votre présentation, vous devrez obtenir une référence à l'objet graphique :

```csharp
var slide = presentation.Slides[0] as Slide;
var shapes = slide.Shapes as ShapeCollection;
var chart = shapes[0] as IChart;
```

## Étape 4 : Animer la série

Il est maintenant temps d'ajouter des effets d'animation à votre série de graphiques. Nous ajouterons un effet de fondu à l'ensemble du graphique et ferons apparaître chaque série une par une.

```csharp
// Animer le graphique
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

// Ajouter une animation à chaque série
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

## Étape 5 : Enregistrez la présentation modifiée

Une fois que vous avez ajouté les effets d'animation à votre graphique, enregistrez la présentation modifiée sur le disque.

```csharp
//Enregistrez la présentation modifiée
presentation.Save(dataDir + "AnimatingSeries_out.pptx", SaveFormat.Pptx);
```

C'est ça! Vous avez réussi à animer une série dans un graphique à l’aide d’Aspose.Slides pour .NET.

## Conclusion

Dans ce didacticiel, nous vous avons expliqué le processus d'animation de séries dans un graphique à l'aide d'Aspose.Slides pour .NET. Avec cette puissante bibliothèque, vous pouvez créer des présentations attrayantes et dynamiques qui captivent votre public.

 Si vous avez des questions ou avez besoin d'aide supplémentaire, n'hésitez pas à contacter la communauté Aspose.Slides sur leur[forum d'entraide](https://forum.aspose.com/).

## FAQ

### Puis-je animer d’autres éléments de graphique en plus des séries à l’aide d’Aspose.Slides pour .NET ?
Oui, vous pouvez animer divers éléments de graphique, notamment des points de données, des axes et des légendes, à l'aide d'Aspose.Slides pour .NET.

### Aspose.Slides pour .NET est-il compatible avec les dernières versions de PowerPoint ?
Aspose.Slides for .NET prend en charge différentes versions de PowerPoint, notamment PowerPoint 2007 et versions ultérieures, garantissant ainsi la compatibilité avec les versions les plus récentes.

### Puis-je personnaliser les effets d’animation pour chaque série de graphiques individuellement ?
Oui, vous pouvez personnaliser les effets d'animation pour chaque série de graphiques afin de créer des présentations uniques et attrayantes.

### Existe-t-il une version d’essai disponible pour Aspose.Slides pour .NET ?
 Oui, vous pouvez essayer la bibliothèque avec un essai gratuit depuis le[Site Web Aspose.Slides pour .NET](https://releases.aspose.com/).

### Où puis-je acheter une licence pour Aspose.Slides pour .NET ?
 Vous pouvez acquérir une licence pour Aspose.Slides pour .NET à partir de la page d'achat[ici](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
