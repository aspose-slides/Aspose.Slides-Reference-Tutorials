---
title: Définir la couleur de remplissage automatique des séries dans les diapositives Java
linktitle: Définir la couleur de remplissage automatique des séries dans les diapositives Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment définir la couleur de remplissage automatique des séries dans Java Slides à l'aide d'Aspose.Slides pour Java. Guide étape par étape avec des exemples de code pour des présentations dynamiques.
weight: 14
url: /fr/java/data-manipulation/set-automatic-series-fill-color-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introduction à la définition automatique de la couleur de remplissage des séries dans les diapositives Java

Dans ce didacticiel, nous explorerons comment définir la couleur de remplissage automatique des séries dans Java Slides à l'aide de l'API Aspose.Slides pour Java. Aspose.Slides pour Java est une bibliothèque puissante qui vous permet de créer, manipuler et gérer des présentations PowerPoint par programme. À la fin de ce guide, vous serez en mesure de créer des graphiques et de définir sans effort les couleurs de remplissage automatiques des séries.

## Conditions préalables

Avant de plonger dans le code, assurez-vous que les conditions préalables suivantes sont en place :

- Kit de développement Java (JDK) installé sur votre système.
-  Bibliothèque Aspose.Slides pour Java ajoutée à votre projet. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/slides/java/).

Maintenant que nous avons notre plan en place, commençons par le guide étape par étape.

## Étape 1 : Introduction à Aspose.Slides pour Java

Aspose.Slides for Java est une API Java qui permet aux développeurs de travailler avec des présentations PowerPoint. Il offre un large éventail de fonctionnalités, notamment la création, la modification et la manipulation de diapositives, de graphiques, de formes, etc.

## Étape 2 : configuration de votre projet Java

Avant de commencer le codage, assurez-vous d'avoir configuré un projet Java dans votre environnement de développement intégré (IDE) préféré. Assurez-vous d'ajouter la bibliothèque Aspose.Slides pour Java à votre projet.

## Étape 3 : Création d'une présentation PowerPoint

Pour commencer, créez une nouvelle présentation PowerPoint à l'aide de l'extrait de code suivant :

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

 Remplacer`"Your Document Directory"` avec le chemin où vous souhaitez enregistrer la présentation.

## Étape 4 : Ajout d'un graphique à la présentation

Ajoutons ensuite un histogramme groupé à la présentation. Nous utiliserons le code suivant pour accomplir cela :

```java
// Création d'un histogramme groupé
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
```

Ce code crée un histogramme groupé sur la première diapositive de la présentation.

## Étape 5 : Définition de la couleur de remplissage automatique de la série

Vient maintenant l’élément clé : la définition automatique de la couleur de remplissage des séries. Nous allons parcourir les séries du graphique et définir leur format de remplissage sur automatique :

```java
// Définition du format de remplissage des séries sur automatique
for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
{
    chart.getChartData().getSeries().get_Item(i).getAutomaticSeriesColor();
}
```

Ce code garantit que la couleur de remplissage de la série est définie sur automatique.

## Étape 6 : Sauvegarde de la présentation

Pour enregistrer la présentation, utilisez le code suivant :

```java
// Écrire le fichier de présentation sur le disque
presentation.save(dataDir + "AutoFillSeries_out.pptx", SaveFormat.Pptx);
```

 Remplacer`"AutoFillSeries_out.pptx"` avec le nom de fichier souhaité.

## Code source complet pour définir la couleur de remplissage automatique des séries dans les diapositives Java

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try
{
	// Création d'un histogramme groupé
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
	// Définition du format de remplissage des séries sur automatique
	for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
	{
		chart.getChartData().getSeries().get_Item(i).getAutomaticSeriesColor();
	}
	// Écrire le fichier de présentation sur le disque
	presentation.save(dataDir + "AutoFillSeries_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusion

Toutes nos félicitations! Vous avez défini avec succès la couleur de remplissage automatique des séries dans une diapositive Java à l'aide d'Aspose.Slides pour Java. Vous pouvez désormais utiliser ces connaissances pour créer des présentations PowerPoint dynamiques et visuellement attrayantes dans vos applications Java.

## FAQ

### Comment puis-je changer le type de graphique en un style différent ?

 Vous pouvez modifier le type de graphique en remplaçant`ChartType.ClusteredColumn` avec le type de graphique souhaité, tel que`ChartType.Line` ou`ChartType.Pie`.

### Puis-je personnaliser davantage l’apparence du graphique ?

Oui, vous pouvez personnaliser l'apparence du graphique en modifiant diverses propriétés du graphique, telles que les couleurs, les polices et les étiquettes.

### Aspose.Slides pour Java est-il adapté à un usage commercial ?

Oui, Aspose.Slides pour Java peut être utilisé pour des projets personnels et commerciaux. Vous pouvez vous référer à leurs conditions de licence pour plus de détails.

### Existe-t-il d'autres fonctionnalités fournies par Aspose.Slides pour Java ?

Oui, Aspose.Slides pour Java offre un large éventail de fonctionnalités, notamment la manipulation des diapositives, le formatage du texte et la prise en charge des animations.

### Où puis-je trouver plus de ressources et de documentation ?

 Vous pouvez accéder à une documentation complète pour Aspose.Slides pour Java à l'adresse[ici](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
