---
title: Ajout de lignes personnalisées dans les diapositives Java
linktitle: Ajout de lignes personnalisées dans les diapositives Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Améliorez vos diapositives Java avec des lignes personnalisées. Guide étape par étape utilisant Aspose.Slides pour Java. Apprenez à ajouter et à personnaliser des lignes dans des présentations pour obtenir des visuels percutants.
weight: 10
url: /fr/java/customization-and-formatting/adding-custom-lines-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introduction à l'ajout de lignes personnalisées dans les diapositives Java

Dans ce didacticiel, vous apprendrez à ajouter des lignes personnalisées à vos diapositives Java à l'aide d'Aspose.Slides for Java. Des lignes personnalisées peuvent être utilisées pour améliorer la représentation visuelle de vos diapositives et mettre en évidence un contenu spécifique. Nous vous fournirons des instructions étape par étape ainsi que le code source pour y parvenir. Commençons!

## Conditions préalables

 Avant de commencer, assurez-vous que la bibliothèque Aspose.Slides pour Java est configurée dans votre projet Java. Vous pouvez télécharger la bibliothèque sur le site :[Aspose.Slides pour Java](https://releases.aspose.com/slides/java/)

## Étape 1 : initialiser la présentation

Tout d’abord, vous devez créer une nouvelle présentation. Dans cet exemple, nous allons créer une présentation vierge.

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Étape 2 : ajouter un graphique

Ensuite, nous ajouterons un graphique à la diapositive. Dans cet exemple, nous ajoutons un histogramme groupé. Vous pouvez choisir le type de graphique qui correspond à vos besoins.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
```

## Étape 3 : ajouter une ligne personnalisée

 Maintenant, ajoutons une ligne personnalisée au graphique. Nous allons créer un`IAutoShape` de type`ShapeType.Line` et positionnez-le dans le graphique.

```java
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Line, 0, chart.getHeight() / 2, chart.getWidth(), 0);
```

## Étape 4 : Personnaliser la ligne

Vous pouvez personnaliser l'apparence de la ligne en définissant ses propriétés. Dans cet exemple, nous définissons la couleur de la ligne sur rouge.

```java
shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

## Étape 5 : Enregistrez la présentation

Enfin, enregistrez la présentation à l'emplacement souhaité.

```java
pres.save(dataDir + "AddCustomLines.pptx", SaveFormat.Pptx);
```

## Code source complet pour ajouter des lignes personnalisées dans les diapositives Java

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
	IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Line, 0, chart.getHeight() / 2, chart.getWidth(), 0);
	shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
	shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.RED);
	pres.save(dataDir + "AddCustomLines.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusion

Toutes nos félicitations! Vous avez ajouté avec succès une ligne personnalisée à votre diapositive Java à l'aide d'Aspose.Slides for Java. Vous pouvez personnaliser davantage les propriétés de la ligne pour obtenir les effets visuels souhaités.

## FAQ

### Comment changer la couleur de la ligne ?

Pour changer la couleur de la ligne, utilisez le code suivant :
```java
shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YOUR_COLOR);
```

 Remplacer`YOUR_COLOR` avec la couleur désirée.

### Puis-je ajouter des lignes personnalisées à d’autres formes ?

 Oui, vous pouvez ajouter des lignes personnalisées à diverses formes, pas seulement à des graphiques. Créez simplement un`IAutoShape` et personnalisez-le selon vos besoins.

### Comment puis-je modifier l’épaisseur du trait ?

 Vous pouvez modifier l'épaisseur du trait en réglant le`Width` propriété du format de ligne. Par exemple:
```java
shape.getLineFormat().setWidth(2); // Définir l'épaisseur du trait sur 2 points
```

### Est-il possible d'ajouter plusieurs lignes à une diapositive ?

Oui, vous pouvez ajouter plusieurs lignes à une diapositive en répétant les étapes mentionnées dans ce didacticiel. Chaque ligne peut être personnalisée indépendamment.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
