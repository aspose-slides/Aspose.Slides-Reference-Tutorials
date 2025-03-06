---
title: Animation de séries dans des diapositives Java
linktitle: Animation de séries dans des diapositives Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Optimisez vos présentations avec des animations en série dans Aspose.Slides pour Java. Suivez notre guide étape par étape avec des exemples de code source pour créer des animations PowerPoint attrayantes.
weight: 11
url: /fr/java/animation-and-layout/animating-series-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introduction à l'animation de séries dans Aspose.Slides pour Java

Dans ce guide, nous vous guiderons à travers le processus d'animation de séries dans des diapositives Java à l'aide de l'API Aspose.Slides pour Java. Cette bibliothèque vous permet de travailler avec des présentations PowerPoint par programmation.

## Conditions préalables

Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :

- Aspose.Slides pour la bibliothèque Java.
- Environnement de développement Java mis en place.

## Étape 1 : Charger la présentation

 Tout d’abord, nous devons charger une présentation PowerPoint existante contenant un graphique. Remplacer`"Your Document Directory"` avec le chemin réel vers votre fichier de présentation.

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
// Instancier la classe Présentation qui représente un fichier de présentation
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
```

## Étape 2 : accéder au graphique

Ensuite, nous accéderons au graphique dans la présentation. Dans cet exemple, nous supposons que le graphique se trouve sur la première diapositive et constitue la première forme de cette diapositive.

```java
// Obtenir une référence à l'objet graphique
ISlide slide = presentation.getSlides().get_Item(0);
IShapeCollection shapes = slide.getShapes();
IChart chart = (IChart) shapes.get_Item(0);
```

## Étape 3 : Ajouter des animations

Maintenant, ajoutons des animations à la série dans le graphique. Nous allons utiliser un effet de fondu et faire apparaître chaque série les unes après les autres.

```java
// Animer l'intégralité du graphique
slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None, EffectTriggerType.AfterPrevious);

// Ajoutez des animations à chaque série (en supposant qu'il y ait 4 séries)
for (int i = 0; i < 4; i++) {
    ((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
            EffectChartMajorGroupingType.BySeries, i,
            EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
}
```

Dans le code ci-dessus, nous utilisons un effet de fondu pour l'ensemble du graphique, puis utilisons une boucle pour ajouter un effet "Apparaître" à chaque série l'une après l'autre.

## Étape 4 : Enregistrez la présentation

Enfin, enregistrez la présentation modifiée sur le disque.

```java
presentation.save(dataDir + "AnimatingSeries_out.pptx", SaveFormat.Pptx);
```

## Code source complet pour l'animation de séries dans Aspose.Slides pour Java

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
// Instancier la classe Présentation qui représente un fichier de présentation
Presentation presentation = new Presentation(dataDir + "ExistingChart.pptx");
try
{
	// Obtenir la référence de l'objet graphique
	ISlide slide = presentation.getSlides().get_Item(0);
	IShapeCollection shapes = slide.getShapes();
	IChart chart = (IChart) shapes.get_Item(0);
	// Animer la série
	slide.getTimeline().getMainSequence().addEffect(chart, EffectType.Fade, EffectSubtype.None,
			EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
			EffectChartMajorGroupingType.BySeries, 0,
			EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
			EffectChartMajorGroupingType.BySeries, 1,
			EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
			EffectChartMajorGroupingType.BySeries, 2,
			EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	((Sequence) slide.getTimeline().getMainSequence()).addEffect(chart,
			EffectChartMajorGroupingType.BySeries, 3,
			EffectType.Appear, EffectSubtype.None, EffectTriggerType.AfterPrevious);
	// Écrivez la présentation modifiée sur le disque
	presentation.save(dataDir + "AnimatingSeries_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusion

Vous avez animé avec succès une série dans un graphique PowerPoint à l'aide d'Aspose.Slides pour Java. Cela peut rendre vos présentations plus attrayantes et visuellement attrayantes. Explorez davantage d'options d'animation et affinez vos présentations selon vos besoins.

## FAQ

### Comment contrôler l’ordre des animations des séries ?

 Pour contrôler l'ordre des animations de séries, utilisez le`EffectTriggerType.AfterPrevious` paramètre lors de l’ajout des effets. Cela fera démarrer chaque animation de série après la fin de la précédente.

### Puis-je appliquer des animations différentes à chaque série ?

 Oui, vous pouvez appliquer différentes animations à chaque série en spécifiant différentes`EffectType` et`EffectSubtype` valeurs lors de l’ajout d’effets.

### Que se passe-t-il si ma présentation comporte plus de quatre séries ?

Vous pouvez étendre la boucle à l'étape 3 pour ajouter des animations pour toutes les séries de votre graphique. Ajustez simplement l'état de la boucle en conséquence.

### Comment puis-je personnaliser la durée et le délai de l'animation ?

Vous pouvez personnaliser la durée et le délai de l'animation en définissant les propriétés des effets d'animation. Consultez la documentation Aspose.Slides pour Java pour plus de détails sur les options de personnalisation disponibles.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
