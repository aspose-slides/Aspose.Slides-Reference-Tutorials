---
title: Définir les options personnalisées de la légende dans les diapositives Java
linktitle: Définir les options personnalisées de la légende dans les diapositives Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment définir des options de légende personnalisées dans Java Slides à l'aide d'Aspose.Slides pour Java. Personnalisez la position et la taille de la légende dans vos graphiques PowerPoint.
weight: 14
url: /fr/java/customization-and-formatting/set-legend-custom-options-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introduction à la définition des options personnalisées de légende dans les diapositives Java

Dans ce didacticiel, nous montrerons comment personnaliser les propriétés de légende d'un graphique dans une présentation PowerPoint à l'aide d'Aspose.Slides pour Java. Vous pouvez modifier la position, la taille et d'autres attributs de la légende en fonction de vos besoins de présentation.

## Conditions préalables

Avant de commencer, assurez-vous d'avoir les éléments suivants :

- Aspose.Slides pour l'API Java installée.
- Environnement de développement Java mis en place.

## Étape 1 : Importez les classes nécessaires :

```java
// Importer Aspose.Slides pour les classes Java
import com.aspose.slides.*;
```

## Étape 2 : Spécifiez le chemin d'accès à votre répertoire de documents :

```java
String dataDir = "Your Document Directory";
```

##  Étape 3 : Créez une instance du`Presentation` class:

```java
Presentation presentation = new Presentation();
```

## Étape 4 : Ajoutez une diapositive à la présentation :

```java
try {
    ISlide slide = presentation.getSlides().get_Item(0);
```

## Étape 5 : Ajoutez un histogramme groupé à la diapositive :

```java
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
```

## Étape 6. Définir les propriétés de la légende :

- Définissez la position X de la légende (par rapport à la largeur du graphique) :

```java
chart.getLegend().setX(50 / chart.getWidth());
```

- Définissez la position Y de la légende (par rapport à la hauteur du graphique) :

```java
chart.getLegend().setY(50 / chart.getHeight());
```

- Définissez la largeur de la légende (par rapport à la largeur du graphique) :

```java
chart.getLegend().setWidth(100 / chart.getWidth());
```

- Définissez la hauteur de la légende (par rapport à la hauteur du graphique) :

```java
chart.getLegend().setHeight(100 / chart.getHeight());
```

## Étape 7 : Enregistrez la présentation sur le disque :

```java
    presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```

C'est ça! Vous avez personnalisé avec succès les propriétés de légende d'un graphique dans une présentation PowerPoint à l'aide d'Aspose.Slides pour Java.

## Code source complet pour définir les options personnalisées de la légende dans les diapositives Java

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
// Créer une instance de la classe Présentation
Presentation presentation = new Presentation();
try
{
	// Obtenir la référence de la diapositive
	ISlide slide = presentation.getSlides().get_Item(0);
	// Ajouter un histogramme groupé sur la diapositive
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
	// Définir les propriétés de la légende
	chart.getLegend().setX(50 / chart.getWidth());
	chart.getLegend().setY(50 / chart.getHeight());
	chart.getLegend().setWidth(100 / chart.getWidth());
	chart.getLegend().setHeight(100 / chart.getHeight());
	// Écrire la présentation sur le disque
	presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```
## Conclusion

Dans ce didacticiel, nous avons appris à personnaliser les propriétés de légende d'un graphique dans une présentation PowerPoint à l'aide d'Aspose.Slides pour Java. Vous pouvez modifier la position, la taille et d'autres attributs de la légende pour créer des présentations visuellement attrayantes et informatives.

## FAQ

## Comment puis-je changer la position de la légende ?

 Pour changer la position de la légende, utilisez le`setX` et`setY` méthodes de l’objet légende. Les valeurs sont spécifiées par rapport à la largeur et à la hauteur du graphique.

## Comment puis-je ajuster la taille de la légende ?

 Vous pouvez ajuster la taille de la légende en utilisant le`setWidth` et`setHeight` méthodes de l’objet légende. Ces valeurs sont également relatives à la largeur et à la hauteur du graphique.

## Puis-je personnaliser d’autres attributs de légende ?

Oui, vous pouvez personnaliser divers attributs de la légende, tels que le style de police, la bordure, la couleur d'arrière-plan, etc. Explorez la documentation Aspose.Slides pour obtenir des informations détaillées sur la personnalisation ultérieure des légendes.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
