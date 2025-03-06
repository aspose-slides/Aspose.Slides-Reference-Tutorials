---
title: Propriétés de police pour la légende individuelle dans les diapositives Java
linktitle: Propriétés de police pour la légende individuelle dans les diapositives Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Améliorez les présentations PowerPoint avec des styles de police, des tailles et des couleurs personnalisés pour les légendes individuelles dans Java Slides à l'aide d'Aspose.Slides pour Java.
weight: 12
url: /fr/java/customization-and-formatting/font-properties-individual-legend-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Propriétés de police pour la légende individuelle dans les diapositives Java


## Introduction aux propriétés de police pour les légendes individuelles dans les diapositives Java

Dans ce didacticiel, nous explorerons comment définir les propriétés de police pour une légende individuelle dans Java Slides à l'aide d'Aspose.Slides pour Java. En personnalisant les propriétés de la police, vous pouvez rendre vos légendes plus attrayantes et informatives dans vos présentations PowerPoint.

## Conditions préalables

 Avant de commencer, assurez-vous que la bibliothèque Aspose.Slides pour Java est intégrée à votre projet. Vous pouvez le télécharger depuis le[Aspose.Slides pour Java Documentation](https://reference.aspose.com/slides/java/).

## Étape 1 : initialiser la présentation et ajouter un graphique

Tout d’abord, commençons par initialiser une présentation PowerPoint et y ajouter un graphique. Dans cet exemple, nous utiliserons un histogramme groupé comme illustration.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");

try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    // Le reste du code va ici
} finally {
    if (pres != null) pres.dispose();
}
```

 Remplacer`"Your Document Directory"` avec le répertoire réel où se trouve votre document PowerPoint.

## Étape 2 : Personnaliser les propriétés de police pour la légende

Maintenant, personnalisons les propriétés de police pour une entrée de légende individuelle dans le graphique. Dans cet exemple, nous ciblons la deuxième entrée de légende (index 1), mais vous pouvez ajuster l'index en fonction de vos besoins spécifiques.

```java
IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
tf.getPortionFormat().setFontBold(NullableBool.True);
tf.getPortionFormat().setFontHeight(20);
tf.getPortionFormat().setFontItalic(NullableBool.True);
tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```

Voici ce que fait chaque ligne de code :

- `get_Item(1)` récupère la deuxième entrée de légende (index 1). Vous pouvez modifier l'index pour cibler une entrée de légende différente.
- `setFontBold(NullableBool.True)` définit la police en gras.
- `setFontHeight(20)` définit la taille de la police à 20 points.
- `setFontItalic(NullableBool.True)` définit la police en italique.
- `setFillType(FillType.Solid)` spécifie que le texte de l'entrée de légende doit avoir un remplissage uni.
- `getSolidFillColor().setColor(Color.BLUE)` définit la couleur de remplissage sur bleu. Vous pouvez remplacer`Color.BLUE` avec la couleur souhaitée.

## Étape 3 : Enregistrez la présentation modifiée

Enfin, enregistrez la présentation modifiée dans un nouveau fichier pour conserver vos modifications.

```java
pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
```

 Remplacer`"output.pptx"` avec votre nom de fichier de sortie préféré.

C'est ça! Vous avez personnalisé avec succès les propriétés de police pour une entrée de légende individuelle dans une présentation Java Slides à l'aide d'Aspose.Slides pour Java.

## Code source complet pour les propriétés de police pour les légendes individuelles dans les diapositives Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
	tf.getPortionFormat().setFontBold(NullableBool.True);
	tf.getPortionFormat().setFontHeight(20);
	tf.getPortionFormat().setFontItalic(NullableBool.True);
	tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusion

Dans ce didacticiel, nous avons appris à personnaliser les propriétés de police d'une légende individuelle dans Java Slides à l'aide d'Aspose.Slides pour Java. En ajustant les styles, les tailles et les couleurs des polices, vous pouvez améliorer l'attrait visuel et la clarté de vos présentations PowerPoint.

## FAQ

### Comment puis-je changer la couleur de la police ?

 Pour changer la couleur de la police, utilisez`tf.getPortionFormat().getFontColor().setColor(yourColor)` au lieu de changer la couleur de remplissage. Remplacer`yourColor` avec la couleur de police souhaitée.

### Comment modifier d'autres propriétés de légende ?

Vous pouvez modifier diverses autres propriétés de la légende, telles que la position, la taille et le format. Reportez-vous à la documentation Aspose.Slides pour Java pour des informations détaillées sur l'utilisation des légendes.

### Puis-je appliquer ces modifications à plusieurs entrées de légende ?

 Oui, vous pouvez parcourir les entrées de légende et appliquer ces modifications à plusieurs entrées en ajustant l'index dans`get_Item(index)` et répéter le code de personnalisation.

N'oubliez pas de supprimer l'objet de présentation lorsque vous avez terminé de libérer des ressources :

```java
if (pres != null) pres.dispose();
```
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
