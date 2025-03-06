---
title: Définir un classeur externe avec mettre à jour les données du graphique dans les diapositives Java
linktitle: Définir un classeur externe avec mettre à jour les données du graphique dans les diapositives Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment définir des classeurs externes et mettre à jour les données du graphique dans Java Slides à l'aide d'Aspose.Slides pour Java. Améliorez vos compétences en automatisation PowerPoint.
weight: 20
url: /fr/java/data-manipulation/set-external-workbook-update-chart-data-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introduction à la définition d'un classeur externe avec mise à jour des données du graphique dans les diapositives Java

Dans ce guide complet, nous vous guiderons tout au long du processus de configuration d'un classeur externe avec des données de graphique mises à jour dans Java Slides à l'aide de l'API Aspose.Slides pour Java. Cette puissante bibliothèque vous permet de manipuler des présentations PowerPoint par programme, ce qui facilite l'automatisation de tâches telles que la mise à jour des données graphiques à partir d'une source externe. À la fin de ce didacticiel, vous comprendrez clairement comment réaliser cette tâche grâce aux instructions étape par étape et au code Java qui l'accompagne.

## Conditions préalables

Avant de nous lancer dans la mise en œuvre, assurez-vous que les conditions préalables suivantes sont en place :

1.  Aspose.Slides pour Java : la bibliothèque Aspose.Slides pour Java doit être installée. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/slides/java/).

2. Environnement de développement Java : assurez-vous d'avoir configuré un environnement de développement Java sur votre système.

## Étape 1 : Créer une nouvelle présentation

Pour commencer, créons une nouvelle présentation PowerPoint à l'aide d'Aspose.Slides pour Java. Voici le code Java pour faire cela :

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Étape 2 : ajouter un graphique

Maintenant, ajoutons un graphique à notre présentation. Nous allons créer un diagramme circulaire dans cet exemple :

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
```

## Étape 3 : Définir un classeur externe

C'est ici que nous définissons le classeur externe comme source de données pour notre graphique. Vous devez fournir l'URL du classeur externe, même s'il n'existe pas pour l'instant :

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook("http://chemin/n'existe pas", false);
```

## Étape 4 : Enregistrez la présentation

Enfin, enregistrez la présentation avec les données du graphique mises à jour :

```java
pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
```

## Code source complet pour définir un classeur externe avec mettre à jour les données du graphique dans les diapositives Java

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook("http://chemin/n'existe pas", false);
	pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusion

Toutes nos félicitations! Vous avez appris à définir un classeur externe avec des données de graphique mises à jour dans Java Slides à l'aide d'Aspose.Slides pour Java. Cela peut être extrêmement utile pour mettre à jour dynamiquement les graphiques de vos présentations PowerPoint à partir de sources de données externes.

## FAQ

### Comment puis-je mettre à jour les données du classeur externe pour le graphique ?

Pour mettre à jour les données du classeur externe pour le graphique, il vous suffit de modifier les données du classeur externe à l'URL spécifiée. La prochaine fois que vous ouvrirez la présentation, Aspose.Slides pour Java récupérera les données mises à jour du classeur externe et mettra à jour le graphique en conséquence.

### Puis-je utiliser un fichier local comme classeur externe ?

Oui, vous pouvez utiliser un fichier local comme classeur externe en fournissant le chemin du fichier au lieu d'une URL. Assurez-vous simplement que le chemin du fichier est correct et accessible depuis votre application Java.

### Existe-t-il des limites à l’utilisation de classeurs externes avec Aspose.Slides pour Java ?

Bien que l'utilisation de classeurs externes soit une fonctionnalité puissante, gardez à l'esprit que la disponibilité des données du classeur externe dépend de son accessibilité à l'URL ou au chemin de fichier fourni. Assurez-vous que la source de données externe est disponible lorsque vous ouvrez la présentation pour éviter les problèmes de récupération des données.

### Puis-je personnaliser l’apparence du graphique après avoir configuré le classeur externe ?

Oui, vous pouvez personnaliser l'apparence du graphique, y compris son titre, ses étiquettes, ses couleurs, etc., même après avoir configuré le classeur externe. Aspose.Slides pour Java fournit de nombreuses options de formatage de graphiques pour répondre à vos besoins.

### Où puis-je trouver plus de documentation et de ressources pour Aspose.Slides pour Java ?

 Pour une documentation détaillée et des ressources supplémentaires, visitez la documentation Aspose.Slides pour Java à l'adresse[ici](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
