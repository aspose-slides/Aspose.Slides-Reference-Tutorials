---
"description": "Apprenez à modifier les données d'un graphique dans un classeur externe avec Aspose.Slides pour Java. Guide étape par étape avec code source."
"linktitle": "Modifier les données du graphique dans un classeur externe dans Java Slides"
"second_title": "API de traitement Java PowerPoint Aspose.Slides"
"title": "Modifier les données du graphique dans un classeur externe dans Java Slides"
"url": "/fr/java/chart-data-manipulation/edit-chart-data-external-workbook-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Modifier les données du graphique dans un classeur externe dans Java Slides


## Introduction à la modification des données d'un graphique dans un classeur externe en Java (diapositives)

Dans ce guide, nous vous montrerons comment modifier les données d'un graphique dans un classeur externe avec Aspose.Slides pour Java. Vous apprendrez à modifier les données d'un graphique dans une présentation PowerPoint par programmation. Assurez-vous que la bibliothèque Aspose.Slides pour Java est installée et configurée dans votre projet.

## Prérequis

- Aspose.Slides pour Java
- Environnement de développement Java

## Étape 1 : Charger la présentation

Tout d'abord, nous devons charger la présentation PowerPoint contenant le graphique dont nous souhaitons modifier les données. Remplacer `"Your Document Directory"` avec le chemin réel vers votre fichier de présentation.

```java
// Le chemin vers le répertoire des documents.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "presentation.pptx");
```

## Étape 2 : Accéder au graphique

Une fois la présentation chargée, nous devons accéder au graphique. Dans cet exemple, nous supposons que le graphique se trouve sur la première diapositive et qu'il s'agit de la première forme de cette diapositive.

```java
IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
```

## Étape 3 : Modifier les données du graphique

Modifions maintenant les données du graphique. Nous allons nous concentrer sur la modification d'un point de données spécifique. Dans cet exemple, nous avons défini la valeur du premier point de données de la première série à 100. Vous pouvez ajuster cette valeur selon vos besoins.

```java
ChartData chartData = (ChartData) chart.getChartData();
chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
```

## Étape 4 : Enregistrer la présentation

Après avoir apporté les modifications nécessaires aux données du graphique, enregistrez la présentation modifiée dans un nouveau fichier. Vous pouvez spécifier le chemin d'accès et le format du fichier de sortie selon vos besoins.

```java
pres.save("output.pptx", SaveFormat.Pptx);
```

## Étape 5 : Nettoyage

N'oubliez pas de supprimer l'objet de présentation pour libérer toutes les ressources.

```java
if (pres != null) pres.dispose();
```

Vous avez maintenant modifié les données du graphique dans un classeur externe de votre présentation PowerPoint avec Aspose.Slides pour Java. Vous pouvez personnaliser ce code selon vos besoins et l'intégrer à vos applications Java.

## Code source complet

```java
        // Faites attention, le chemin vers le classeur externe est à peine enregistré dans la présentation
        // Veuillez donc copier le fichier externalWorkbook.xlsx depuis le répertoire Data/Chart D:\Aspose.Slides\Aspose.Slides-for-.NET-master\Examples\Data\Charts\ avant d'exécuter l'exemple
        // Le chemin vers le répertoire des documents.
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

Dans ce guide complet, nous avons découvert comment modifier les données des graphiques dans des classeurs externes au sein de présentations PowerPoint avec Aspose.Slides pour Java. En suivant les instructions étape par étape et les exemples de code source, vous avez acquis les connaissances et les compétences nécessaires pour modifier facilement les données des graphiques par programmation.

## FAQ

### Comment spécifier un graphique ou une diapositive différent ?

Pour accéder à un autre graphique ou à une autre diapositive, modifiez l'index approprié dans le `getSlides().get_Item()` et `getShapes().get_Item()` méthodes. N'oubliez pas que l'indexation commence à 0.

### Puis-je modifier les données de plusieurs graphiques dans la même présentation ?

Oui, vous pouvez modifier les données de plusieurs graphiques dans la même présentation en répétant les étapes de modification des données du graphique pour chaque graphique.

### Que faire si je souhaite modifier des données dans un classeur externe avec un format différent ?

Vous pouvez adapter le code pour gérer différents formats de classeur externes en utilisant les classes et méthodes Aspose.Cells appropriées pour lire et écrire des données dans ce format.

### Comment puis-je automatiser ce processus pour plusieurs présentations ?

Vous pouvez créer une boucle pour traiter plusieurs présentations, charger chacune d'elles, apporter les modifications souhaitées et enregistrer les présentations modifiées une par une.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}