---
title: Modifier les données du graphique dans un classeur externe dans Java Slides
linktitle: Modifier les données du graphique dans un classeur externe dans Java Slides
second_title: API de traitement Java PowerPoint d'Aspose.Slides
description: Découvrez comment modifier les données d'un graphique dans un classeur externe à l'aide d'Aspose.Slides pour Java. Guide étape par étape avec le code source.
weight: 17
url: /fr/java/chart-data-manipulation/edit-chart-data-external-workbook-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introduction à la modification des données de graphique dans un classeur externe dans Java Slides

Dans ce guide, nous montrerons comment modifier les données d'un graphique dans un classeur externe à l'aide d'Aspose.Slides pour Java. Vous apprendrez à modifier par programmation les données d’un graphique dans une présentation PowerPoint. Assurez-vous que la bibliothèque Aspose.Slides pour Java est installée et configurée dans votre projet.

## Conditions préalables

- Aspose.Slides pour Java
- Environnement de développement Java

## Étape 1 : Charger la présentation

 Tout d’abord, nous devons charger la présentation PowerPoint contenant le graphique dont nous souhaitons modifier les données. Remplacer`"Your Document Directory"` avec le chemin réel vers votre fichier de présentation.

```java
// Le chemin d'accès au répertoire des documents.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "presentation.pptx");
```

## Étape 2 : accéder au graphique

Une fois la présentation chargée, nous devons accéder au graphique dans la présentation. Dans cet exemple, nous supposons que le graphique se trouve sur la première diapositive et constitue la première forme de cette diapositive.

```java
IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
```

## Étape 3 : Modifier les données du graphique

Maintenant, modifions les données du graphique. Nous nous concentrerons sur la modification d’un point de données spécifique dans le graphique. Dans cet exemple, nous définissons la valeur du premier point de données de la première série sur 100. Vous pouvez ajuster cette valeur si nécessaire.

```java
ChartData chartData = (ChartData) chart.getChartData();
chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
```

## Étape 4 : Enregistrez la présentation

Après avoir apporté les modifications nécessaires aux données du graphique, enregistrez la présentation modifiée dans un nouveau fichier. Vous pouvez spécifier le chemin et le format du fichier de sortie en fonction de vos besoins.

```java
pres.save("output.pptx", SaveFormat.Pptx);
```

## Étape 5 : Nettoyage

N'oubliez pas de supprimer l'objet de présentation pour libérer les ressources.

```java
if (pres != null) pres.dispose();
```

Vous avez maintenant modifié avec succès les données du graphique dans un classeur externe dans votre présentation PowerPoint à l'aide d'Aspose.Slides pour Java. Vous pouvez personnaliser ce code en fonction de vos besoins spécifiques et l'intégrer dans vos applications Java.

## Code source complet

```java
        // Faites attention, le chemin vers le classeur externe n'est guère enregistré dans la présentation
        // veuillez donc copier le fichier externalWorkbook.xlsx du répertoire Data/Chart D:\Aspose.Slides\Aspose.Slides-for-.NET-master\Examples\Data\Charts\ avant d'exécuter l'exemple
        // Le chemin d'accès au répertoire des documents.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation(dataDir + "presentation.pptx");
        try
        {
            IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
            ChartData chartData = (ChartData) chart.getChartData();
            chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
            pres.save("Your Output Directory" + "presentation_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## Conclusion

Dans ce guide complet, nous avons exploré comment modifier les données d'un graphique dans des classeurs externes dans des présentations PowerPoint à l'aide d'Aspose.Slides pour Java. En suivant les instructions étape par étape et les exemples de code source, vous avez acquis les connaissances et les compétences nécessaires pour modifier facilement les données des graphiques par programmation.

## FAQ

### Comment puis-je spécifier un autre graphique ou une autre diapositive ?

 Pour accéder à un autre graphique ou diapositive, modifiez l'index approprié dans le`getSlides().get_Item()` et`getShapes().get_Item()`méthodes. N'oubliez pas que l'indexation commence à 0.

### Puis-je modifier les données de plusieurs graphiques au sein de la même présentation ?

Oui, vous pouvez modifier les données de plusieurs graphiques au sein de la même présentation en répétant les étapes de modification des données du graphique pour chaque graphique.

### Que faire si je souhaite modifier des données dans un classeur externe avec un format différent ?

Vous pouvez adapter le code pour gérer différents formats de classeurs externes en utilisant les classes et méthodes Aspose.Cells appropriées pour lire et écrire des données dans ce format.

### Comment puis-je automatiser ce processus pour plusieurs présentations ?

Vous pouvez créer une boucle pour traiter plusieurs présentations, en chargeant chacune d'elles, en apportant les modifications souhaitées et en enregistrant les présentations modifiées une par une.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
