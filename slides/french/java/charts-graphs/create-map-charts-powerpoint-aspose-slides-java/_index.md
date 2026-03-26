---
date: '2026-03-26'
description: Apprenez à créer un graphique cartographique Java dans PowerPoint à l'aide
  d'Aspose.Slides. Ce guide vous montre comment ajouter un graphique cartographique
  dans PowerPoint, configurer l'environnement et personnaliser l'apparence des graphiques.
keywords:
- create map charts in PowerPoint
- Aspose.Slides for Java
- Java PowerPoint presentation
title: Créer un diagramme cartographique Java dans PowerPoint avec Aspose.Slides
url: /fr/java/charts-graphs/create-map-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Comment créer des graphiques cartographiques dans PowerPoint avec Aspose.Slides pour Java

## Introduction

Vous souhaitez représenter visuellement des données géographiques dans vos présentations PowerPoint en Java ? **Create map chart java** est la solution idéale pour transformer des chiffres bruts en une histoire visuelle attrayante. Dans ce tutoriel, vous apprendrez comment ajouter un graphique cartographique à une diapositive PowerPoint, le remplir avec des données au niveau des pays et affiner son apparence — le tout avec l’API Aspose.Slides pour Java.

Commençons !

## Quick Answers
- **Que puis‑je visualiser ?** Toute donnée géographique telle que les ventes par pays, le PIB ou les indicateurs environnementaux.  
- **Quelle bibliothèque est requise ?** Aspose.Slides pour Java (dernière version).  
- **Ai‑je besoin d’une licence ?** Un essai gratuit suffit pour le développement ; une licence permanente est nécessaire pour la production.  
- **Combien de lignes de code ?** Environ 30 lignes pour créer et enregistrer un graphique cartographique de base.  
- **Puis‑je personnaliser les couleurs ?** Oui – vous pouvez définir les couleurs de remplissage pour chaque point de données.

## Qu’est‑ce qu’un graphique cartographique dans PowerPoint ?
Un graphique cartographique affiche les valeurs de données sur une carte géographique, permettant aux spectateurs de comparer rapidement les régions. Avec Aspose.Slides, vous pouvez générer ces graphiques de manière programmatique, ce qui est idéal pour les rapports automatisés ou les présentations basées sur les données.

## Pourquoi ajouter un graphique cartographique PowerPoint avec Aspose.Slides ?
- **Automatisation** – générez des dizaines de diapositives sans effort manuel.  
- **Précision** – contrôle exact des données, des couleurs et de la mise en page.  
- **Multiplateforme** – fonctionne sur tout système d’exploitation supportant Java.  

## Prérequis

Avant de commencer, assurez‑vous que vous disposez de ce qui suit :

### Bibliothèques requises et versions
- **Aspose.Slides pour Java** : nous utiliserons la dernière version (actuellement 25.4).

### Exigences de configuration de l’environnement
- Un kit de développement Java (JDK) installé et configuré.  
- Un IDE tel qu’IntelliJ IDEA, Eclipse ou NetBeans.

### Prérequis de connaissances
- Programmation Java de base.  
- La familiarité avec Maven ou Gradle est utile mais pas obligatoire.

## Configuration d’Aspose.Slides pour Java

Pour commencer, vous devez inclure la bibliothèque Aspose.Slides dans votre projet. Selon votre outil de construction préféré, voici comment faire :

### Utilisation de Maven
Incluez cette dépendance dans votre fichier `pom.xml` :
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Utilisation de Gradle
Ajoutez cette ligne à votre fichier `build.gradle` :
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Téléchargement direct
Sinon, vous pouvez télécharger la dernière version directement depuis [versions d'Aspose.Slides pour Java](https://releases.aspose.com/slides/java/).

#### Étapes d’obtention de licence
- **Essai gratuit** : Aspose propose une licence d’essai gratuite pour tester leur API avec des limitations.  
- **Licence temporaire** : vous pouvez demander une licence temporaire de 30 jours pour un accès complet sans limitations d’évaluation sur le [site Aspose](https://purchase.aspose.com/temporary-license/).  
- **Achat** : pour une utilisation continue, achetez un abonnement. Visitez [cette page](https://purchase.aspose.com/buy) pour acheter.

#### Initialisation et configuration de base
Une fois Aspose.Slides pour Java configuré dans votre projet, initialisez‑le comme indiqué ci‑dessous :
```java
// Initialize the Presentation class object
tPresentation presentation = new Presentation();
```

## Guide de mise en œuvre

Dans cette section, nous parcourrons chaque étape nécessaire pour **create map chart java** dans PowerPoint en utilisant Aspose.Slides pour Java.

### Étape 1 : créer une nouvelle présentation
Commencez par initialiser une nouvelle instance de la classe `Presentation`. Elle servira de canevas pour créer des diapositives et des graphiques.
```java
// Initialize a new presentation
tPresentation presentation = new Presentation();
```

### Étape 2 : ajouter un graphique cartographique à la diapositive
Ajoutez un graphique cartographique vide à la première diapositive à une position spécifiée avec des dimensions définies.

#### Vue d’ensemble
Nous ajouterons un graphique cartographique pour visualiser des données géographiques, comme des comparaisons de pays ou des statistiques régionales.
```java
// Add an empty map chart to the first slide at position (50, 50) with width 500 and height 400
tIChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Map, 50, 50, 500, 400, false);
```

**Paramètres expliqués :**
- `ChartType.Map` : indique que le type de graphique est une carte.  
- Position `(50, 50)` : coordonnées X et Y sur la diapositive où le graphique apparaîtra.  
- Dimensions `500x400` : largeur et hauteur du graphique en points.

### Étape 3 : configurer les données du graphique cartographique
#### Vue d’ensemble
Nous ajouterons des séries de données et des catégories (représentant des pays) à notre graphique cartographique. Cette étape consiste à remplir le graphique avec des points de données pertinents.
```java
// Access the data workbook associated with the chart
tIChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

// Add a series and some data points to it
tIChartSeries series = chart.getChartData().getSeries().add(ChartType.Map);
series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B2", 5));
series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B3", 1));
series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B4", 10));

// Add categories (representing countries) for the map chart
chart.getChartData().getCategories().add(wb.getCell(0, "A2", "United States"));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Mexico"));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Brazil"));
```

**Options de configuration clés :**
- `IChartDataWorkbook` : fournit l’accès aux cellules de données du graphique.  
- Les points de données sont ajoutés à l’aide de références de cellules (`wb.getCell()`), ce qui facilite la gestion et la mise à jour des données.

### Étape 4 : personnaliser l’apparence du graphique cartographique
#### Vue d’ensemble
Personnalisez l’apparence de votre graphique cartographique, par exemple en modifiant la couleur de points de données spécifiques.
```java
// Change the value of a data point
tIChartDataPoint dataPoint = series.getDataPoints().get_Item(1);
dataPoint.getColorValue().getAsCell().setValue("15");

// Set the appearance of the data point (fill color)
dataPoint.getFormat().getFill().setFillType(FillType.Solid);
dataPoint.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

**Pourquoi c’est important :**
- Personnaliser les couleurs et les valeurs aide à mettre en évidence des points de données spécifiques, rendant votre présentation plus attrayante.

### Étape 5 : enregistrer la présentation
Après avoir configuré votre graphique cartographique, enregistrez la présentation dans un fichier.
```java
// Save the presentation with the map chart
presentation.save(resultPath, SaveFormat.Pptx);
```

**Conseils de dépannage :**
- Assurez‑vous que le répertoire indiqué dans `resultPath` existe et est accessible en écriture.  
- Si l’enregistrement échoue, vérifiez les exceptions pouvant indiquer des problèmes d’autorisations ou des formats de chemin incorrects.

## Applications pratiques

Les graphiques cartographiques peuvent être utilisés dans divers scénarios réels :

1. **Rapports économiques** – afficher le PIB, les taux de chômage ou les balances commerciales par pays.  
2. **Visualisation des données de ventes** – montrer la performance des ventes régionales sur une carte du monde.  
3. **Études environnementales** – illustrer les niveaux de pollution, les taux de déforestation ou les données climatiques géographiquement.

### Possibilités d’intégration
Les graphiques cartographiques créés avec Aspose.Slides peuvent être intégrés aux outils de reporting, aux tableaux de bord ou aux pipelines de présentation automatisés pour un récit plus riche basé sur les données.

## Considérations de performance

Lorsque vous travaillez avec Aspose.Slides pour Java, gardez ces conseils à l’esprit pour optimiser les performances :

- **Gestion de la mémoire** – libérez l’objet `Presentation` (`presentation.dispose()`) lorsque vous avez terminé.  
- **Gestion optimisée des données** – utilisez des structures de données légères pour les grands ensembles de données.  
- **Restez à jour** – mettez régulièrement à jour vers la dernière version d’Aspose.Slides pour bénéficier des améliorations de performance et des corrections de bugs.

## Conclusion

Créer un graphique cartographique dans PowerPoint avec Aspose.Slides pour Java est simple une fois l’environnement configuré. En suivant ce guide, vous pouvez **create map chart java** des solutions qui transforment des données géographiques brutes en visuels percutants. Expérimentez avec des options de personnalisation supplémentaires, explorez d’autres types de graphiques et intégrez le résultat dans vos flux de reporting automatisés.

**Prochaines étapes**
- Essayez différents thèmes de carte et palettes de couleurs.  
- Combinez plusieurs graphiques sur une même diapositive pour une analyse comparative.  
- Explorez l’API Aspose.Slides pour les animations et l’interactivité.

**Appel à l’action :** Implémentez cette solution dans votre prochain projet pour améliorer votre visualisation de données !

## Section FAQ

### Comment installer Aspose.Slides pour un nouveau projet ?
Suivez les étapes de configuration sous « Configuration d’Aspose.Slides pour Java » et assurez‑vous que toutes les conditions préalables sont remplies.

**Q : Puis‑je ajouter plusieurs graphiques cartographiques à la même diapositive ?**  
R : Oui, répétez simplement le code d’ajout du graphique avec des positions et des ensembles de données différents.

**Q : Est‑il possible de changer la projection de la carte (par ex., Mercator vs. Robinson) ?**  
R : Aspose.Slides prend en charge plusieurs projections cartographiques ; vous pouvez définir la propriété `MapProjection` sur l’objet graphique.

**Q : Que faire si je dois charger des données depuis un fichier CSV ?**  
R : Lisez le CSV dans une collection Java, puis remplissez les cellules du classeur de données du graphique de manière programmatique.

**Q : La bibliothèque fonctionne‑t‑elle sur Java 11 et versions supérieures ?**  
R : Absolument – le classificateur `jdk16` fonctionne sur Java 11+, 16 et les versions ultérieures.

**Q : Comment protéger le PPTX généré avec un mot de passe ?**  
R : Utilisez `presentation.getProtectionManager().setPassword("yourPassword");` avant l’enregistrement.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Dernière mise à jour :** 2026-03-26  
**Testé avec :** Aspose.Slides for Java 25.4  
**Auteur :** Aspose