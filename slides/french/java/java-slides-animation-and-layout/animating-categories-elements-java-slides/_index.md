---
title: Animation d'éléments de catégories dans des diapositives Java
linktitle: Animation d'éléments de catégories dans des diapositives Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Optimisez vos présentations Java avec Aspose.Slides pour Java. Découvrez comment animer des éléments de catégorie dans des diapositives PowerPoint, étape par étape.
weight: 10
url: /fr/java/animation-and-layout/animating-categories-elements-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introduction à l'animation d'éléments de catégories dans les diapositives Java

Dans ce didacticiel, nous vous guiderons tout au long du processus d'animation des éléments de catégorie dans les diapositives Java à l'aide d'Aspose.Slides pour Java. Ce guide étape par étape vous fournira le code source et les explications pour vous aider à obtenir cet effet d'animation.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Aspose.Slides pour l'API Java installée.
- Une présentation PowerPoint existante contenant un graphique. Vous animerez les éléments de catégorie de ce graphique.

## Étape 1 : Importer la bibliothèque Aspose.Slides

Pour commencer, importez la bibliothèque Aspose.Slides dans votre projet Java. Vous pouvez télécharger et ajouter la bibliothèque au chemin de classe de votre projet. Assurez-vous d'avoir configuré les dépendances nécessaires.

## Étape 2 : Charger la présentation

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
```

 Dans ce code, nous chargeons une présentation PowerPoint existante contenant le graphique que vous souhaitez animer. Remplacer`"Your Document Directory"` avec le chemin réel vers votre répertoire de documents.

## Étape 3 : obtenir une référence à l'objet graphique

```java
ISlide slide = presentation.getSlides().get_Item(0);
IShapeCollection shapes = slide.getShapes();
IChart chart = (IChart) shapes.get_Item(0);
```

Nous obtenons une référence à l'objet graphique dans la première diapositive de la présentation. Ajustez l’index des diapositives (`get_Item(0)`) et l'indice de forme (`get_Item(0)`) selon vos besoins pour accéder à votre graphique spécifique.

## Étape 4 : Animer les éléments des catégories

```java
slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

for (int i = 0; i < chart.getChartData().getCategories().size(); i++) {
    for (int j = 0; j < chart.getChartData().getSeries().size(); j++) {
        ((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, i, j, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
    }
}
```

Nous animons les éléments des catégories dans le graphique. Ce code ajoute un effet de fondu à l'ensemble du graphique, puis ajoute un effet « Apparaître » à chaque élément de chaque catégorie. Ajustez le type et le sous-type d’effet selon vos besoins.

## Étape 5 : Enregistrez la présentation

```java
presentation.save(dataDir + "AnimatingCategoriesElements_out.pptx", SaveFormat.Pptx);
```

 Enfin, enregistrez la présentation modifiée avec le graphique animé dans un nouveau fichier. Remplacer`"AnimatingCategoriesElements_out.pptx"` avec le nom de fichier de sortie souhaité.


## Code source complet pour animer des éléments de catégories dans des diapositives Java
```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
try
{
	// Obtenir la référence de l'objet graphique
	ISlide slide = presentation.getSlides().get_Item(0);
	IShapeCollection shapes = slide.getShapes();
	IChart chart = (IChart) shapes.get_Item(0);
	// Animer les éléments des catégories
	slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 0, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 1, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 0, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 1, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 2, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart, EffectChartMinorGroupingType.ByElementInCategory, 2, 3, EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	// Écrire le fichier de présentation sur le disque
	presentation.save(dataDir + "AnimatingCategoriesElements_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusion

Vous avez animé avec succès les éléments de catégorie dans une diapositive Java à l'aide d'Aspose.Slides pour Java. Ce guide étape par étape vous a fourni le code source et les explications nécessaires pour obtenir cet effet d'animation dans vos présentations PowerPoint. Expérimentez avec différents effets et paramètres pour personnaliser davantage vos animations.

## FAQ

### Comment puis-je personnaliser les effets d'animation ?

 Vous pouvez personnaliser les effets d'animation en modifiant le`EffectType` et`EffectSubtype` paramètres lors de l’ajout d’effets aux éléments du graphique. Reportez-vous à la documentation Aspose.Slides pour Java pour plus de détails sur les effets d'animation disponibles.

### Puis-je appliquer ces animations à d’autres types de graphiques ?

Oui, vous pouvez appliquer des animations similaires à d'autres types de graphiques en modifiant le code pour cibler les éléments spécifiques du graphique que vous souhaitez animer. Ajustez la structure et les paramètres de la boucle en conséquence.

### Comment puis-je en savoir plus sur Aspose.Slides pour Java ?

 Pour une documentation complète et des ressources supplémentaires, visitez le[Référence de l'API Aspose.Slides pour Java](https://reference.aspose.com/slides/java/) . Vous pouvez également télécharger la bibliothèque depuis[ici](https://releases.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
