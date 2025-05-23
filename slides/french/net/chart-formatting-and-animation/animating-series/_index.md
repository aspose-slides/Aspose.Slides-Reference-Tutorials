---
"description": "Apprenez à animer des séries de graphiques avec Aspose.Slides pour .NET. Captivez votre public avec des présentations dynamiques. Commencez dès maintenant !"
"linktitle": "Série animée dans le graphique"
"second_title": "API de traitement PowerPoint Aspose.Slides .NET"
"title": "Animer des séries de graphiques avec Aspose.Slides pour .NET"
"url": "/fr/net/chart-formatting-and-animation/animating-series/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Animer des séries de graphiques avec Aspose.Slides pour .NET


Envie d'ajouter du peps à vos présentations avec des graphiques animés ? Aspose.Slides pour .NET est là pour donner vie à vos graphiques. Dans ce guide étape par étape, nous vous montrerons comment animer des séries dans un graphique avec Aspose.Slides pour .NET. Mais avant de passer à l'action, découvrons les prérequis.

## Prérequis

Pour animer avec succès des séries dans un graphique à l'aide d'Aspose.Slides pour .NET, vous aurez besoin des éléments suivants :

### 1. Bibliothèque Aspose.Slides pour .NET

Assurez-vous d'avoir installé la bibliothèque Aspose.Slides pour .NET. Si ce n'est pas déjà fait, vous pouvez la télécharger depuis le [Aspose.Slides pour site Web .NET](https://releases.aspose.com/slides/net/).

### 2. Présentation existante avec un graphique

Préparez une présentation PowerPoint (PPTX) avec un graphique existant que vous souhaitez animer.

Maintenant que nous avons couvert les prérequis, décomposons le processus en une série d'étapes pour animer la série de graphiques.


## Étape 1 : Importer les espaces de noms nécessaires

Vous devrez importer les espaces de noms requis dans votre code C# pour travailler avec Aspose.Slides pour .NET :

```csharp
﻿using Aspose.Slides.Charts;
using Aspose.Slides.Export;
using Aspose.Slides.Animation;
using Aspose.Slides;
```

## Étape 2 : Charger la présentation existante

À cette étape, chargez votre présentation PowerPoint existante (PPTX) qui contient le graphique que vous souhaitez animer.

```csharp
// Chemin d'accès au répertoire des documents
string dataDir = "Your Document Directory";

// Instancier une classe de présentation qui représente un fichier de présentation 
using (Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx"))
{
    // Votre code va ici
}
```

## Étape 3 : Obtenir la référence de l'objet graphique

Pour travailler avec le graphique dans votre présentation, vous devrez obtenir une référence à l'objet graphique :

```csharp
var slide = presentation.Slides[0] as Slide;
var shapes = slide.Shapes as ShapeCollection;
var chart = shapes[0] as IChart;
```

## Étape 4 : Animer la série

Il est maintenant temps d'ajouter des effets d'animation à votre série de graphiques. Nous allons appliquer un effet de fondu à l'ensemble du graphique et faire apparaître chaque série une par une.

```csharp
// Animer le graphique
slide.Timeline.MainSequence.AddEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

// Ajouter une animation à chaque série
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
((Sequence)slide.Timeline.MainSequence).AddEffect(chart, EffectChartMajorGroupingType.BySeries, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
```

## Étape 5 : Enregistrer la présentation modifiée

Une fois que vous avez ajouté les effets d’animation à votre graphique, enregistrez la présentation modifiée sur le disque.

```csharp
// Enregistrer la présentation modifiée
presentation.Save(dataDir + "AnimatingSeries_out.pptx", SaveFormat.Pptx);
```

Et voilà ! Vous avez réussi à animer des séries dans un graphique avec Aspose.Slides pour .NET.

## Conclusion

Dans ce tutoriel, nous vous avons expliqué comment animer des séries dans un graphique avec Aspose.Slides pour .NET. Grâce à cette puissante bibliothèque, vous pouvez créer des présentations attrayantes et dynamiques qui captiveront votre public.

Si vous avez des questions ou avez besoin d'aide supplémentaire, n'hésitez pas à contacter la communauté Aspose.Slides sur leur [forum d'assistance](https://forum.aspose.com/).

## FAQ

### Puis-je animer d’autres éléments de graphique en plus des séries à l’aide d’Aspose.Slides pour .NET ?
Oui, vous pouvez animer divers éléments de graphique, notamment des points de données, des axes et des légendes, à l’aide d’Aspose.Slides pour .NET.

### Aspose.Slides pour .NET est-il compatible avec les dernières versions de PowerPoint ?
Aspose.Slides pour .NET prend en charge différentes versions de PowerPoint, notamment PowerPoint 2007 et versions ultérieures, garantissant ainsi la compatibilité avec les versions les plus récentes.

### Puis-je personnaliser les effets d’animation pour chaque série de graphiques individuellement ?
Oui, vous pouvez personnaliser les effets d’animation pour chaque série de graphiques afin de créer des présentations uniques et attrayantes.

### Existe-t-il une version d'essai disponible pour Aspose.Slides pour .NET ?
Oui, vous pouvez essayer la bibliothèque avec un essai gratuit à partir du [Aspose.Slides pour site Web .NET](https://releases.aspose.com/).

### Où puis-je acheter une licence pour Aspose.Slides pour .NET ?
Vous pouvez acquérir une licence pour Aspose.Slides pour .NET à partir de la page d'achat [ici](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}