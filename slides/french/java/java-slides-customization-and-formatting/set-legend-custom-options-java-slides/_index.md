---
"description": "Découvrez comment personnaliser les options de légende dans Java Slides avec Aspose.Slides pour Java. Personnalisez la position et la taille des légendes dans vos graphiques PowerPoint."
"linktitle": "Définir les options personnalisées de légende dans les diapositives Java"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Définir les options personnalisées de légende dans les diapositives Java"
"url": "/fr/java/customization-and-formatting/set-legend-custom-options-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Définir les options personnalisées de légende dans les diapositives Java


## Introduction aux options personnalisées de définition de légende dans les diapositives Java

Dans ce tutoriel, nous vous montrerons comment personnaliser les propriétés de la légende d'un graphique dans une présentation PowerPoint avec Aspose.Slides pour Java. Vous pouvez modifier la position, la taille et d'autres attributs de la légende pour l'adapter aux besoins de votre présentation.

## Prérequis

Avant de commencer, assurez-vous d’avoir les éléments suivants :

- Aspose.Slides pour l'API Java installée.
- Configuration de l'environnement de développement Java.

## Étape 1 : Importer les classes nécessaires :

```java
// Importer Aspose.Slides pour les classes Java
import com.aspose.slides.*;
```

## Étape 2 : Spécifiez le chemin d’accès à votre répertoire de documents :

```java
String dataDir = "Your Document Directory";
```

## Étape 3 : Créer une instance du `Presentation` classe:

```java
Presentation presentation = new Presentation();
```

## Étape 4 : Ajouter une diapositive à la présentation :

```java
try {
    ISlide slide = presentation.getSlides().get_Item(0);
```

## Étape 5 : Ajoutez un graphique à colonnes groupées à la diapositive :

```java
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
```

## Étape 6. Définir les propriétés de la légende :

- Définir la position X de la légende (par rapport à la largeur du graphique) :

```java
chart.getLegend().setX(50 / chart.getWidth());
```

- Définir la position Y de la légende (par rapport à la hauteur du graphique) :

```java
chart.getLegend().setY(50 / chart.getHeight());
```

- Définir la largeur de la légende (par rapport à la largeur du graphique) :

```java
chart.getLegend().setWidth(100 / chart.getWidth());
```

- Définir la hauteur de la légende (par rapport à la hauteur du graphique) :

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

Et voilà ! Vous avez réussi à personnaliser les propriétés de légende d'un graphique dans une présentation PowerPoint avec Aspose.Slides pour Java.

## Code source complet pour définir les options personnalisées de légende dans les diapositives Java

```java
// Le chemin vers le répertoire des documents.
String dataDir = "Your Document Directory";
// Créer une instance de la classe Presentation
Presentation presentation = new Presentation();
try
{
	// Obtenir la référence de la diapositive
	ISlide slide = presentation.getSlides().get_Item(0);
	// Ajouter un graphique à colonnes groupées sur la diapositive
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

Dans ce tutoriel, nous avons appris à personnaliser les propriétés de la légende d'un graphique dans une présentation PowerPoint à l'aide d'Aspose.Slides pour Java. Vous pouvez modifier la position, la taille et d'autres attributs de la légende pour créer des présentations visuellement attrayantes et informatives.

## FAQ

## Comment puis-je changer la position de la légende ?

Pour modifier la position de la légende, utilisez le `setX` et `setY` Méthodes de l'objet légende. Les valeurs sont spécifiées par rapport à la largeur et à la hauteur du graphique.

## Comment puis-je ajuster la taille de la légende ?

Vous pouvez ajuster la taille de la légende en utilisant le `setWidth` et `setHeight` Méthodes de l'objet légende. Ces valeurs sont également relatives à la largeur et à la hauteur du graphique.

## Puis-je personnaliser d’autres attributs de légende ?

Oui, vous pouvez personnaliser divers attributs de la légende, tels que le style de police, la bordure, la couleur d'arrière-plan, etc. Consultez la documentation d'Aspose.Slides pour plus d'informations sur la personnalisation des légendes.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}