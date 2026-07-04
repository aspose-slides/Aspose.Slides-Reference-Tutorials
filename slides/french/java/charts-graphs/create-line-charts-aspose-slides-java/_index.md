---
date: '2026-03-23'
description: Apprenez à utiliser Aspose.Slides pour Java afin de créer des graphiques
  en courbes avec des marqueurs, d’ajouter une deuxième série et de gérer les données
  nulles dans les présentations PowerPoint.
keywords:
- Aspose.Slides for Java
- line charts with markers in Java
- creating presentations programmatically
title: 'Comment utiliser Aspose.Slides pour Java : créer des graphiques en courbes
  avec des marqueurs par défaut'
url: /fr/java/charts-graphs/create-line-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Créer des graphiques en courbes avec des marqueurs par défaut à l'aide d'Aspose.Slides pour Java

## Introduction
Si vous vous demandez **comment utiliser Aspose** pour automatiser la création de PowerPoint, vous êtes au bon endroit. Dans ce tutoriel, nous allons vous guider à travers la création d'un **graphique en courbes avec des marqueurs**, l'ajout d'une deuxième série et la gestion des données nulles — le tout avec Aspose.Slides pour Java. À la fin, vous disposerez d'un extrait prêt à l'exécution qui génère un graphique à l'aspect professionnel sans jamais ouvrir PowerPoint manuellement.

### Réponses rapides
- **Quelle bibliothèque dois-je utiliser ?** Aspose.Slides for Java (dernière version recommandée)  
- **Puis-je ajouter une deuxième série ?** Oui – l'API vous permet d'ajouter plusieurs séries facilement.  
- **Comment les points de données nuls sont-ils gérés ?** Utilisez `null` comme valeur de cellule ; le graphique ignorera le point.  
- **Ai-je besoin de Maven ?** Maven ou Gradle fonctionnent ; voir la section *aspose slides maven* ci‑dessous.  
- **Une licence est‑elle requise ?** Un essai gratuit suffit pour le développement ; une licence commerciale est nécessaire pour la production.

## Comment utiliser Aspose.Slides pour Java afin de créer des graphiques en courbes
Créer des graphiques de manière programmatique vous fait gagner des heures de mise en forme manuelle et garantit la cohérence entre les présentations. Que vous construisiez une fonctionnalité **create powerpoint chart** dans un outil de reporting ou que vous génériez des diaporamas à la volée, Aspose.Slides vous offre un contrôle total depuis le code Java.

## Prérequis
Avant de commencer, assurez-vous que votre environnement de développement est prêt :

1. **Bibliothèques et dépendances**  
   - Bibliothèque Aspose.Slides pour Java (version 25.4 recommandée) – cela couvre le scénario *aspose slides maven*.  
   - Java Development Kit (JDK) version 16 ou supérieure.
2. **Configuration de l'environnement**  
   - IDE avec prise en charge de Maven ou Gradle.  
   - Un fichier de licence Aspose valide si vous prévoyez d'exécuter le code en dehors d'un essai.
3. **Prérequis de connaissances**  
   - Programmation Java de base.  
   - Familiarité avec les fichiers de construction Maven ou Gradle.

## Configuration d'Aspose.Slides pour Java
### Maven
Ajoutez la dépendance suivante à votre fichier `pom.xml` :
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
### Gradle
Incluez ceci dans votre fichier `build.gradle` :
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
### Téléchargement direct
Vous pouvez également télécharger la dernière version depuis [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**Étapes d'obtention de licence :**
- Pour un essai gratuit, visitez la [page d'essai gratuit](https://releases.aspose.com/slides/java/).
- Pour obtenir une licence temporaire, accédez à la [page de licence temporaire](https://purchase.aspose.com/temporary-license/).
- Achetez une licence complète via leur [portail d'achat](https://purchase.aspose.com/buy).

**Initialisation de base :**
Voici comment vous pouvez initialiser Aspose.Slides dans votre application Java :
```java
import com.aspose.slides.Presentation;
// Initialize a new presentation object
Presentation pres = new Presentation();
```

Passons maintenant à la création de graphiques !

## Guide d'implémentation
### Fonctionnalité 1 : Création de graphique avec des marqueurs par défaut
Cette section montre comment créer un **graphique en courbes avec des marqueurs**, idéal pour mettre en évidence des points de données individuels sur une ligne de tendance.

#### Ajout d'un graphique en courbes
Pour ajouter un graphique en courbes avec des marqueurs :
```java
import com.aspose.slides.*;
// Access the first slide
ISlide slide = pres.getSlides().get_Item(0);
// Add a line chart with markers to the slide at position (10, 10) with size (400, 400)
IChart chart = slide.getShapes().addChart(
    ChartType.LineWithMarkers, 10, 10, 400, 400);
```

#### Effacement des séries et des catégories
Pour repartir de zéro :
```java
// Clear existing series and categories to ensure a clean slate
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Obtain the chart's data workbook for further manipulation
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

### Fonctionnalité 2 : Ajout de séries et de catégories
L'ajout de séries et de catégories est essentiel pour alimenter vos graphiques avec des données pertinentes.

#### Création d'une nouvelle série
Pour ajouter une nouvelle série nommée "Series 1" :
```java
// Add a new series to the chart
chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// Access the first series for data population
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
```

#### Remplissage des catégories et des points de données
Pour ajouter des catégories et les points de données correspondants :
```java
// Add category names and their respective data points
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));

chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));

chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));

// Handling null data points gracefully
chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));
```

### Fonctionnalité 3 : Ajout d'une deuxième série et remplissage des points de données
L'ajout de séries supplémentaires apporte plus de profondeur à votre analyse visuelle.

#### Création et remplissage d'une deuxième série
Pour ajouter "Series 2" :
```java
// Add another series named 'Series 2'
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"), chart.getType());

// Access the second series for data population
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// Add data points for 'Series 2'
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```

### Fonctionnalité 4 : Configuration de la légende du graphique
Configurer la légende améliore la lisibilité du graphique, surtout lorsque vous **ajoutez une deuxième série**.

#### Ajustement des paramètres de la légende
Pour configurer :
```java
// Enable the legend and set it not to overlay on data points
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

### Fonctionnalité 5 : Enregistrement de la présentation
Une fois votre graphique prêt, vous voudrez **create powerpoint chart** des fichiers qui peuvent être partagés ou modifiés davantage.
```java
try {
    // Save the modified presentation to a specified directory
    pres.save("YOUR_DOCUMENT_DIRECTORY/DefaultMarkersInChart.pptx");
} finally {
    if (pres != null) pres.dispose();
}
```

## Applications pratiques
1. **Reporting d'entreprise :** Utilisez un graphique en courbes avec des marqueurs pour illustrer les tendances financières sur les trimestres.  
2. **Analyse de données :** Visualisez des données expérimentales où chaque marqueur met en évidence un point de mesure.  
3. **Matériel éducatif :** Créez des diapositives de cours montrant les changements étape par étape d'un processus.  
4. **Gestion de projet :** Suivez les jalons sur une chronologie avec des marqueurs distincts pour les dates clés.  
5. **Présentations marketing :** Montrez les pics de performance d'une campagne avec des symboles de marqueurs clairs.

## Problèmes courants et solutions
- **Les points de données nuls provoquent des erreurs :** Passez `null` comme valeur de cellule (comme indiqué) – Aspose omettra simplement le point.  
- **Le graphique apparaît sans marqueurs :** Assurez‑vous d'utiliser `ChartType.LineWithMarkers` plutôt que `ChartType.Line`.  
- **La légende chevauche les données :** Définissez `chart.getLegend().setOverlay(false)` pour garder la légende séparée.  

## Foire aux questions

**Q : Puis‑je utiliser cette approche pour générer des graphiques dans un service web ?**  
R : Absolument. La bibliothèque fonctionne dans n'importe quel environnement Java, y compris les applications côté serveur.

**Q : Ai‑je besoin d'une licence pour les builds de développement ?**  
R : Un essai gratuit suffit pour le développement et les tests. Une licence commerciale est requise pour une utilisation en production.

**Q : Comment Aspose gère‑t‑il les grands ensembles de données ?**  
R : L'API diffuse les données efficacement ; toutefois, gardez le nombre de points de données raisonnable afin d'éviter des tailles de fichier trop importantes.

**Q : Existe‑t‑il une prise en charge d'autres types de graphiques ?**  
R : Oui – Aspose.Slides prend en charge les graphiques à barres, secteurs, nuages de points et bien d'autres types.

**Q : Puis‑je personnaliser les formes et les couleurs des marqueurs ?**  
R : Vous pouvez modifier le format du marqueur via la propriété `Marker` de chaque point de données.

## Conclusion
Vous savez maintenant **comment utiliser Aspose** pour créer un graphique en courbes avec des marqueurs par défaut, ajouter une deuxième série, gérer les données nulles et enregistrer le résultat sous forme de fichier PowerPoint. Ces techniques vous permettent d'automatiser la génération de rapports, d'améliorer la narration des données et de garder vos présentations cohérentes.

Pour aller plus loin, explorez la [documentation officielle](https://docs.aspose.com/slides/java/) ou rejoignez les forums communautaires comme Stack Overflow.

---

**Dernière mise à jour :** 2026-03-23  
**Testé avec :** Aspose.Slides for Java 25.4 (jdk16)  
**Auteur :** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}