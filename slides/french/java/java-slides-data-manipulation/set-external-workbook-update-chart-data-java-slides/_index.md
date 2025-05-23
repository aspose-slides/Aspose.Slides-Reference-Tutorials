---
"description": "Apprenez à configurer des classeurs externes et à mettre à jour les données des graphiques dans Java Slides avec Aspose.Slides pour Java. Améliorez vos compétences en automatisation PowerPoint."
"linktitle": "Définir un classeur externe avec des données de graphique de mise à jour dans les diapositives Java"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Définir un classeur externe avec des données de graphique de mise à jour dans les diapositives Java"
"url": "/fr/java/data-manipulation/set-external-workbook-update-chart-data-java-slides/"
"weight": 20
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Définir un classeur externe avec des données de graphique de mise à jour dans les diapositives Java


## Introduction à la définition d'un classeur externe avec mise à jour des données de graphique en Java (diapositives)

Dans ce guide complet, nous vous expliquerons comment configurer un classeur externe avec des données graphiques mises à jour dans Java Slides à l'aide de l'API Aspose.Slides pour Java. Cette puissante bibliothèque vous permet de manipuler des présentations PowerPoint par programmation, facilitant ainsi l'automatisation de tâches telles que la mise à jour de données graphiques depuis une source externe. À la fin de ce tutoriel, vous maîtriserez parfaitement la procédure grâce aux instructions étape par étape et au code Java associé.

## Prérequis

Avant de nous plonger dans la mise en œuvre, assurez-vous que les conditions préalables suivantes sont en place :

1. Aspose.Slides pour Java : la bibliothèque Aspose.Slides pour Java doit être installée. Vous pouvez la télécharger ici. [ici](https://releases.aspose.com/slides/java/).

2. Environnement de développement Java : assurez-vous qu’un environnement de développement Java est configuré sur votre système.

## Étape 1 : Créer une nouvelle présentation

Pour commencer, créons une présentation PowerPoint avec Aspose.Slides pour Java. Voici le code Java pour cela :

```java
// Le chemin vers le répertoire des documents.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Étape 2 : Ajouter un graphique

Ajoutons maintenant un graphique à notre présentation. Dans cet exemple, nous allons créer un graphique à secteurs :

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
```

## Étape 3 : Définir un classeur externe

C'est ici que nous définissons le classeur externe comme source de données pour notre graphique. Vous devez fournir l'URL du classeur externe, même s'il n'existe pas encore :

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook("http://chemin/n'existe/pas", false);
```

## Étape 4 : Enregistrer la présentation

Enfin, enregistrez la présentation avec les données du graphique mises à jour :

```java
pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
```

## Code source complet pour définir un classeur externe avec mise à jour des données de graphique dans les diapositives Java

```java
// Le chemin vers le répertoire des documents.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook("http://chemin/n'existe/pas", false);
	pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusion

Félicitations ! Vous avez appris à configurer un classeur externe avec des données graphiques mises à jour dans Java Slides grâce à Aspose.Slides pour Java. Cela peut s'avérer très utile pour mettre à jour dynamiquement les graphiques de vos présentations PowerPoint à partir de sources de données externes.

## FAQ

### Comment puis-je mettre à jour les données du classeur externe pour le graphique ?

Pour mettre à jour les données du classeur externe pour le graphique, il vous suffit de modifier les données du classeur externe à l'URL spécifiée. À la prochaine ouverture de la présentation, Aspose.Slides pour Java récupérera les données mises à jour du classeur externe et mettra à jour le graphique en conséquence.

### Puis-je utiliser un fichier local comme classeur externe ?

Oui, vous pouvez utiliser un fichier local comme classeur externe en indiquant le chemin d'accès au fichier plutôt qu'une URL. Assurez-vous simplement que le chemin d'accès est correct et accessible depuis votre application Java.

### Existe-t-il des limitations à l’utilisation de classeurs externes avec Aspose.Slides pour Java ?

Bien que l'utilisation de classeurs externes soit une fonctionnalité puissante, gardez à l'esprit que la disponibilité des données du classeur externe dépend de leur accessibilité via l'URL ou le chemin d'accès fourni. Assurez-vous que la source de données externe est disponible à l'ouverture de la présentation pour éviter tout problème de récupération des données.

### Puis-je personnaliser l'apparence du graphique après avoir défini le classeur externe ?

Oui, vous pouvez personnaliser l'apparence du graphique, y compris son titre, ses étiquettes, ses couleurs, etc., même après avoir configuré le classeur externe. Aspose.Slides pour Java offre de nombreuses options de mise en forme pour répondre à vos besoins.

### Où puis-je trouver plus de documentation et de ressources pour Aspose.Slides pour Java ?

Pour une documentation détaillée et des ressources supplémentaires, visitez la documentation Aspose.Slides pour Java à l'adresse [ici](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}