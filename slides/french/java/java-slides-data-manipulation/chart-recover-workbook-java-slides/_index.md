---
"description": "Découvrez comment récupérer des classeurs à partir de graphiques dans Java Slides avec Aspose.Slides. Guide étape par étape pour l'automatisation de PowerPoint."
"linktitle": "Classeur de récupération de graphiques dans les diapositives Java"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Classeur de récupération de graphiques dans les diapositives Java"
"url": "/fr/java/data-manipulation/chart-recover-workbook-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Classeur de récupération de graphiques dans les diapositives Java


## Introduction au classeur Chart Recover en Java (diapositives)

Lorsque vous travaillez avec des présentations PowerPoint en Java, vous pourriez être confronté à des situations où vous devez récupérer les données d'un classeur à partir d'un graphique. Cette tâche peut s'avérer cruciale, notamment pour les présentations basées sur les données. Aspose.Slides pour Java simplifie ce processus et, dans ce guide, nous vous expliquerons comment procéder.

## Prérequis

Avant de commencer, assurez-vous que les conditions préalables suivantes sont remplies :

- Java Development Kit (JDK) installé sur votre système.
- Bibliothèque Aspose.Slides pour Java. Vous pouvez la télécharger ici. [ici](https://releases.aspose.com/slides/java/).

## Étape 1 : Configuration de votre projet

Créez un nouveau projet Java dans votre environnement de développement intégré (IDE) préféré et ajoutez la bibliothèque Aspose.Slides pour Java aux dépendances de votre projet.

## Étape 2 : Importer les classes nécessaires

Dans votre code Java, importez les classes requises depuis Aspose.Slides pour Java :

```java
import com.aspose.slides.*;
```

## Étape 3 : Chargement de la présentation

Chargez la présentation PowerPoint qui contient le graphique à partir duquel vous souhaitez récupérer les données du classeur :

```java
String dataDir = "Your Document Directory";
String pptxFile = dataDir + "ExternalWB.pptx";
String outPptxFile = "Path to Output File";
LoadOptions lo = new LoadOptions();
lo.getSpreadsheetOptions().setRecoverWorkbookFromChartCache(true);
Presentation pres = new Presentation(pptxFile, lo);
```

## Étape 4 : Accès aux données du graphique

Vous pouvez désormais accéder aux données du graphique et récupérer le classeur :

```java
try
{
    IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    // Effectuer des opérations sur les données du classeur ici
    pres.save(outPptxFile, SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

## Code source complet du classeur de récupération de graphiques en Java

```java
// Le chemin vers le répertoire des documents.
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

Dans ce guide, nous avons expliqué comment récupérer un classeur à partir d'un graphique dans Java Slides à l'aide d'Aspose.Slides pour Java. Cette bibliothèque simplifie la tâche et permet aux développeurs de travailler plus facilement avec des présentations PowerPoint par programmation. Vous pouvez désormais gérer en toute confiance des présentations basées sur les données et extraire les informations du classeur selon vos besoins.

## FAQ

### Comment installer Aspose.Slides pour Java ?

Aspose.Slides pour Java peut être facilement installé en téléchargeant la bibliothèque à partir du site Web à l'adresse [ici](https://releases.aspose.com/slides/java/). Suivez les instructions d'installation fournies pour l'intégrer dans votre projet Java.

### Puis-je récupérer les données d’un classeur à partir de n’importe quel graphique dans une présentation PowerPoint ?

Oui, vous pouvez récupérer les données d'un classeur à partir de n'importe quel graphique d'une présentation PowerPoint, à condition de disposer de la bibliothèque Aspose.Slides pour Java et que le graphique soit accessible dans la présentation. L'extrait de code fourni montre comment procéder.

### Existe-t-il des options supplémentaires pour travailler avec des données de graphique à l’aide d’Aspose.Slides pour Java ?

Oui, Aspose.Slides pour Java offre un large éventail d'options pour travailler avec les données des graphiques. Vous pouvez manipuler les propriétés des graphiques, récupérer des points de données et effectuer diverses opérations sur les graphiques pour répondre à vos besoins spécifiques.

### Aspose.Slides pour Java est-il adapté à l'automatisation professionnelle de PowerPoint ?

Absolument ! Aspose.Slides pour Java est une bibliothèque puissante pour automatiser les tâches PowerPoint, adaptée aux cas d'utilisation professionnels simples et avancés. Elle offre des fonctionnalités complètes pour créer, modifier et gérer des présentations PowerPoint par programmation.

### Comment puis-je accéder à une documentation supplémentaire pour Aspose.Slides pour Java ?

Pour une documentation détaillée et des références sur Aspose.Slides pour Java, visitez la page de documentation à l'adresse [ici](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}