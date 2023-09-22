---
title: Classeur de récupération de graphique dans les diapositives Java
linktitle: Classeur de récupération de graphique dans les diapositives Java
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment récupérer des classeurs à partir de graphiques dans Java Slides avec Aspose.Slides. Guide étape par étape pour l’automatisation de PowerPoint.
type: docs
weight: 17
url: /fr/java/data-manipulation/chart-recover-workbook-java-slides/
---

## Introduction au classeur de récupération de graphiques dans Java Slides

Lorsque vous travaillez avec des présentations PowerPoint en Java, vous pouvez rencontrer des scénarios dans lesquels vous devez récupérer les données d'un classeur à partir d'un graphique. Cela peut s'avérer une tâche cruciale, en particulier lorsqu'il s'agit de présentations basées sur des données. Aspose.Slides pour Java simplifie ce processus et dans ce guide, nous vous montrerons comment procéder.

## Conditions préalables

Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :

- Kit de développement Java (JDK) installé sur votre système.
-  Aspose.Slides pour la bibliothèque Java. Vous pouvez le télécharger depuis[ici](https://releases.aspose.com/slides/java/).

## Étape 1 : Configuration de votre projet

Créez un nouveau projet Java dans votre environnement de développement intégré (IDE) préféré et ajoutez la bibliothèque Aspose.Slides for Java aux dépendances de votre projet.

## Étape 2 : Importer les classes nécessaires

Dans votre code Java, importez les classes requises depuis Aspose.Slides for Java :

```java
import com.aspose.slides.*;
```

## Étape 3 : Chargement de la présentation

Chargez la présentation PowerPoint contenant le graphique à partir duquel vous souhaitez récupérer les données du classeur :

```java
String dataDir = "Your Document Directory";
String pptxFile = dataDir + "ExternalWB.pptx";
String outPptxFile = "Path to Output File";
LoadOptions lo = new LoadOptions();
lo.getSpreadsheetOptions().setRecoverWorkbookFromChartCache(true);
Presentation pres = new Presentation(pptxFile, lo);
```

## Étape 4 : Accéder aux données du graphique

Vous pouvez désormais accéder aux données du graphique et récupérer le classeur :

```java
try
{
    IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    // Effectuez des opérations sur les données du classeur ici
    pres.save(outPptxFile, SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

## Code source complet pour le classeur de récupération de graphiques dans les diapositives Java

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
String pptxFile = dataDir + "ExternalWB.pptx";
String outPptxFile = RunExamples.OutPath + "ExternalWB_out.pptx";
LoadOptions lo = new LoadOptions();
lo.getSpreadsheetOptions().setRecoverWorkbookFromChartCache(true);
Presentation pres = new Presentation(pptxFile, lo);
try
{
	IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	pres.save(outPptxFile, SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusion

Dans ce guide, nous avons parcouru le processus de récupération d'un classeur à partir d'un graphique dans Java Slides à l'aide d'Aspose.Slides pour Java. Cette bibliothèque simplifie la tâche, permettant aux développeurs de travailler plus facilement avec des présentations PowerPoint par programme. Vous pouvez désormais gérer en toute confiance des présentations basées sur des données et extraire les informations du classeur selon vos besoins.

## FAQ

### Comment installer Aspose.Slides pour Java ?

 Aspose.Slides pour Java peut être facilement installé en téléchargeant la bibliothèque à partir du site Web à l'adresse[ici](https://releases.aspose.com/slides/java/)Suivez les instructions d'installation fournies pour l'intégrer dans votre projet Java.

### Puis-je récupérer les données d'un classeur à partir de n'importe quel graphique dans une présentation PowerPoint ?

Oui, vous pouvez récupérer les données d'un classeur à partir de n'importe quel graphique dans une présentation PowerPoint à condition que vous disposiez de la bibliothèque Aspose.Slides pour Java et que le graphique soit accessible dans la présentation. L'extrait de code fourni montre comment y parvenir.

### Existe-t-il des options supplémentaires pour travailler avec des données graphiques à l’aide d’Aspose.Slides pour Java ?

Oui, Aspose.Slides pour Java offre un large éventail d'options pour travailler avec des données graphiques. Vous pouvez manipuler les propriétés des graphiques, récupérer des points de données et effectuer diverses opérations sur les graphiques pour répondre à vos besoins spécifiques.

### Aspose.Slides for Java est-il adapté à l’automatisation professionnelle de PowerPoint ?

Absolument! Aspose.Slides pour Java est une bibliothèque puissante pour automatiser les tâches PowerPoint, ce qui la rend adaptée aux cas d'utilisation professionnelle de base et avancée. Il fournit des fonctionnalités étendues pour créer, modifier et gérer des présentations PowerPoint par programmation.

### Comment puis-je accéder à une documentation supplémentaire sur Aspose.Slides pour Java ?

 Pour une documentation détaillée et des références sur Aspose.Slides pour Java, visitez la page de documentation à l'adresse[ici](https://reference.aspose.com/slides/java/).