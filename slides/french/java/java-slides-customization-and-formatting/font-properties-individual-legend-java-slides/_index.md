---
"description": "Améliorez les présentations PowerPoint avec des styles de police, des tailles et des couleurs personnalisés pour les légendes individuelles dans Java Slides à l'aide d'Aspose.Slides pour Java."
"linktitle": "Propriétés de police pour une légende individuelle dans les diapositives Java"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Propriétés de police pour une légende individuelle dans les diapositives Java"
"url": "/fr/java/customization-and-formatting/font-properties-individual-legend-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Propriétés de police pour une légende individuelle dans les diapositives Java


## Introduction aux propriétés de police pour les légendes individuelles dans les diapositives Java

Dans ce tutoriel, nous allons découvrir comment définir les propriétés de police d'une légende dans Java Slides avec Aspose.Slides pour Java. En personnalisant les propriétés de police, vous pouvez rendre vos légendes plus attrayantes et informatives dans vos présentations PowerPoint.

## Prérequis

Avant de commencer, assurez-vous d'avoir intégré la bibliothèque Aspose.Slides pour Java à votre projet. Vous pouvez la télécharger depuis le [Documentation Aspose.Slides pour Java](https://reference.aspose.com/slides/java/).

## Étape 1 : Initialiser la présentation et ajouter un graphique

Commençons par initialiser une présentation PowerPoint et y ajouter un graphique. Dans cet exemple, nous utiliserons un histogramme groupé.

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

Remplacer `"Your Document Directory"` avec le répertoire réel où se trouve votre document PowerPoint.

## Étape 2 : Personnaliser les propriétés de police pour la légende

Personnalisons maintenant les propriétés de police d'une entrée de légende spécifique du graphique. Dans cet exemple, nous ciblons la deuxième entrée de légende (index 1), mais vous pouvez ajuster l'index selon vos besoins.

```java
IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
tf.getPortionFormat().setFontBold(NullableBool.True);
tf.getPortionFormat().setFontHeight(20);
tf.getPortionFormat().setFontItalic(NullableBool.True);
tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```

Voici ce que fait chaque ligne de code :

- `get_Item(1)` récupère la deuxième entrée de légende (index 1). Vous pouvez modifier l'index pour cibler une autre entrée de légende.
- `setFontBold(NullableBool.True)` définit la police en gras.
- `setFontHeight(20)` définit la taille de la police à 20 points.
- `setFontItalic(NullableBool.True)` définit la police en italique.
- `setFillType(FillType.Solid)` spécifie que le texte d'entrée de la légende doit avoir un remplissage solide.
- `getSolidFillColor().setColor(Color.BLUE)` définit la couleur de remplissage sur bleu. Vous pouvez remplacer `Color.BLUE` avec la couleur souhaitée.

## Étape 3 : Enregistrer la présentation modifiée

Enfin, enregistrez la présentation modifiée dans un nouveau fichier pour conserver vos modifications.

```java
pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
```

Remplacer `"output.pptx"` avec votre nom de fichier de sortie préféré.

Et voilà ! Vous avez réussi à personnaliser les propriétés de police d'une entrée de légende dans une présentation Java Slides avec Aspose.Slides pour Java.

## Code source complet des propriétés de police pour chaque légende dans les diapositives Java

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

Dans ce tutoriel, nous avons appris à personnaliser les propriétés de police d'une légende dans Java Slides avec Aspose.Slides pour Java. En ajustant les styles, tailles et couleurs de police, vous pouvez améliorer l'esthétique et la clarté de vos présentations PowerPoint.

## FAQ

### Comment puis-je changer la couleur de la police ?

Pour changer la couleur de la police, utilisez `tf.getPortionFormat().getFontColor().setColor(yourColor)` au lieu de changer la couleur de remplissage. Remplacer `yourColor` avec la couleur de police souhaitée.

### Comment modifier d’autres propriétés de légende ?

Vous pouvez modifier diverses autres propriétés de la légende, telles que la position, la taille et le format. Consultez la documentation d'Aspose.Slides pour Java pour plus d'informations sur l'utilisation des légendes.

### Puis-je appliquer ces modifications à plusieurs entrées de légende ?

Oui, vous pouvez parcourir les entrées de légende et appliquer ces modifications à plusieurs entrées en ajustant l'index dans `get_Item(index)` et en répétant le code de personnalisation.

N'oubliez pas de supprimer l'objet de présentation lorsque vous avez terminé pour libérer les ressources :

```java
if (pres != null) pres.dispose();
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}